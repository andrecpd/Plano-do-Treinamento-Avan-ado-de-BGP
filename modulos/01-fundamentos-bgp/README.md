# Módulo 01 — Fundamentos de BGP

## Objetivos

Ao terminar, você deverá explicar a função do BGP, distinguir eBGP de iBGP, interpretar os estados da sessão, entender os atributos básicos e acompanhar a diferença entre tabela BGP, tabela de roteamento e FIB.

## 1. Conceitos essenciais

BGP é um protocolo de roteamento interdomínio do tipo path-vector. A sessão BGP utiliza TCP/179. O BGP troca informações de alcançabilidade de prefixos e atributos usados na aplicação de políticas e na seleção de caminhos. Ele não substitui automaticamente o IGP interno: em redes de operadoras, o IGP normalmente oferece alcançabilidade interna e o BGP distribui rotas externas e serviços.

- **eBGP**: sessão entre sistemas autônomos diferentes.
- **iBGP**: sessão entre roteadores do mesmo AS.
- **ASN**: identificador do sistema autônomo.
- **NLRI**: prefixos anunciados.
- **RIB**: estruturas de informação de roteamento.
- **FIB**: estrutura usada para encaminhar pacotes.

## 2. Mensagens e estados

Mensagens clássicas: OPEN, UPDATE, KEEPALIVE e NOTIFICATION. A máquina de estados inclui Idle, Connect, Active, OpenSent, OpenConfirm e Established. Uma sessão Established indica que a vizinhança foi estabelecida; não prova, sozinha, que os prefixos corretos estão sendo aceitos, instalados ou anunciados.

## 3. Atributos que você deve reconhecer

- **LOCAL_PREF**: preferência dentro do AS; maior valor é preferido. Normalmente propagado por iBGP, não enviado a vizinhos eBGP.
- **AS_PATH**: sequência de ASNs percorridos; políticas podem preferir caminhos mais curtos, mas a decisão depende dos critérios anteriores e da política da plataforma.
- **ORIGIN**: indica a origem da informação de rota (IGP, EGP histórico ou incomplete).
- **MED**: sinal opcional usado para sugerir preferência entre entradas vindas do mesmo AS vizinho, sujeito às regras e políticas implementadas.
- **NEXT_HOP**: próximo salto para alcançar o prefixo.
- **WEIGHT**: atributo proprietário da Cisco, local ao roteador e não propagado aos pares.
- **COMMUNITY**: etiqueta para aplicar políticas.

A ordem exata de decisão varia conforme fabricante, versão e configuração. Consulte o guia da plataforma usada no laboratório.

## 4. Topologia LAB-01

Use três roteadores:
- R1 — AS 65001, endereço de enlace 192.0.2.1/30.
- R2 — AS 65002, endereço de enlace 192.0.2.2/30.
- R1 anuncia a rede de laboratório 198.51.100.0/24.
- R2 origina ou aprende 203.0.113.0/24 para os testes.

Os ASNs e prefixos são reservados para documentação e devem permanecer em laboratório.

## 5. Configuração-base Cisco IOS/IOS XE

**R1**
```text
hostname R1
interface GigabitEthernet0/0
 description eBGP-to-R2
 ip address 192.0.2.1 255.255.255.252
 no shutdown
!
router bgp 65001
 bgp log-neighbor-changes
 neighbor 192.0.2.2 remote-as 65002
 network 198.51.100.0 mask 255.255.255.0
```

**R2**
```text
hostname R2
interface GigabitEthernet0/0
 description eBGP-to-R1
 ip address 192.0.2.2 255.255.255.252
 no shutdown
!
router bgp 65002
 bgp log-neighbor-changes
 neighbor 192.0.2.1 remote-as 65001
 network 203.0.113.0 mask 255.255.255.0
```

**Importante:** o comando BGP `network` geralmente exige que o prefixo exato exista na tabela de roteamento, conforme a máscara configurada. Para um laboratório isolado, crie a rota de origem apropriada ou ajuste o método de originação à plataforma. Não assuma que o anúncio ocorreu só porque o comando foi aceito.

## 6. Validação

Execute conforme a plataforma:
```text
show ip bgp summary
show ip bgp
show ip route bgp
show ip route 198.51.100.0
show ip route 203.0.113.0
show ip bgp neighbors 192.0.2.2
```

Em versões recentes, alguns comandos usam `show bgp ipv4 unicast` ou sintaxe equivalente.

## 7. Exercícios

1. Qual diferença operacional existe entre eBGP e iBGP?
2. O que significa uma sessão em Active? Cite pelo menos três hipóteses a investigar.
3. Por que a sessão pode estar Established sem que uma rota específica esteja instalada?
4. Explique a diferença entre tabela BGP, RIB principal e FIB.
5. Que efeito pode ter LOCAL_PREF 200 versus LOCAL_PREF 100 dentro do mesmo AS?
6. Por que o comando `network` pode não anunciar o prefixo esperado?

## 8. Falhas para induzir

- Desligar a interface do enlace.
- Configurar o remote-as incorreto.
- Usar endereço de vizinho inalcançável.
- Remover a rota exata que sustenta o comando `network`.
- Aplicar um filtro que bloqueie o prefixo.

## 9. Gabarito resumido

1. eBGP conecta AS diferentes; iBGP distribui rotas BGP dentro do mesmo AS.
2. Active é uma tentativa de estabelecer TCP/sessão; investigar conectividade IP, ACL/firewall, TCP/179, endereço do neighbor, ASN remoto e parâmetros de sessão.
3. Pode não ter sido recebida, pode ser filtrada, não ser best path, ter next-hop inalcançável ou não ser instalada por política/limitação.
4. A tabela BGP guarda caminhos BGP; a RIB principal escolhe rotas para uso do sistema; a FIB é usada no encaminhamento.
5. Em geral, maior LOCAL_PREF vence entre caminhos elegíveis comparados pelo processo de decisão.
6. O prefixo exato pode não estar na tabela de roteamento ou a máscara não corresponder.

## Entrega

Salve a topologia, as configurações e as saídas dos comandos em `evidencias/lab-01/`. Não inclua senhas nem dados de produção.
