# Treinamento Avançado de BGP — Cisco e ISP

> Trilha prática de estudo e laboratório para engenharia de redes, operação de ISP e preparação técnica. Conteúdo organizado a partir do curso de referência **Curso Avançado de BGP Design com Roteadores Cisco (versão 1.1, 2012)**, com uma camada de atualização técnica identificada separadamente.

## Objetivos

- Projetar e operar eBGP com um ou mais provedores.
- Entender seleção de rotas, atributos BGP e políticas de importação/exportação.
- Implementar multihoming, failover, engenharia de tráfego e peering.
- Construir filtros escaláveis e reduzir risco de route leak e anúncio indevido.
- Praticar iBGP, route reflectors, communities, IPv4 e IPv6.
- Diagnosticar falhas usando comandos, evidências e procedimentos operacionais.
- Montar um projeto final de ISP com documentação e plano de rollback.

## Como estudar cada módulo

1. Leia a teoria e os objetivos.
2. Monte a topologia no EVE-NG ou GNS3.
3. Aplique as configurações em cópias dos arquivos-base.
4. Execute todos os comandos de validação.
5. Injete a falha descrita e registre os sintomas.
6. Responda aos exercícios antes de consultar o gabarito.
7. Salve evidências, resultados e lições aprendidas em `evidencias/`.

## Trilha do curso

| Etapa | Conteúdo | Material |
|---|---|---|
| 00 | Plano, ambiente e convenções | [Plano de estudos](docs/plano-de-estudos.md) |
| 01 | Fundamentos, ASN, FSM, RIB/FIB e seleção de rotas | [Módulo 01](modulos/01-fundamentos-bgp/README.md) |
| 02 | eBGP básico com provedor | [Módulo 02](modulos/02-ebgp-basico/README.md) |
| 03 | Multihoming, failover e engenharia de tráfego | [Módulo 03](modulos/03-multihoming-failover/README.md) |
| 04 | Peering, trânsito e IX.br | [Módulo 04](modulos/04-peering-transito-ix/README.md) |
| 05 | Políticas, filtros, IRR e RPKI/ROV | [Módulo 05](modulos/05-politicas-filtros-seguranca/README.md) |
| 06 | AS_PATH regex, prefix-list e route-map | [Módulo 06](modulos/06-as-path-regex-route-map/README.md) |
| 07 | AS_PATH prepend e controle de anúncios | [Módulo 07](modulos/07-traffic-engineering/README.md) |
| 08 | iBGP, next-hop e route reflector | [Módulo 08](modulos/08-ibgp-route-reflector/README.md) |
| 09 | BGP communities | [Módulo 09](modulos/09-communities/README.md) |
| 10 | IX múltiplos, trânsito e clientes multihomed | [Módulo 10](modulos/10-ix-multihoming-avancado/README.md) |
| 11 | Operação, observabilidade e troubleshooting | [Módulo 11](modulos/11-operacao-troubleshooting/README.md) |
| 12 | Segurança, IPv6 e práticas atuais | [Módulo 12](modulos/12-seguranca-ipv6-atualizacoes/README.md) |
| 13 | Projeto final de desenho de ISP | [Módulo 13](modulos/13-projeto-final-isp/README.md) |

## Laboratórios

Os laboratórios serão numerados e independentes, com topologia, plano de endereçamento, configurações por roteador, testes esperados, falhas induzidas e gabarito comentado.

- [Catálogo de laboratórios](labs/README.md)
- [Modelos de configuração](configs/README.md)
- [Procedimentos de validação](validacao/README.md)
- [Troubleshooting](troubleshooting/README.md)
- [Gabaritos comentados](gabaritos/README.md)

## Ambiente recomendado

- **EVE-NG ou GNS3**.
- Imagens Cisco IOS/IOS XE/IOS XR obtidas e licenciadas conforme os termos aplicáveis, ou FRRouting para laboratórios de conceitos.
- Console por roteador e possibilidade de capturar pacotes.
- Git para versionar configurações e registrar alterações.

> Os comandos variam entre Cisco IOS, IOS XE, IOS XR e FRRouting. Cada laboratório deve declarar a plataforma e a versão usada. Não copie uma configuração de produção sem revisão, validação e plano de rollback.

## Estrutura do repositório

```text
.
├── README.md
├── docs/
│   ├── plano-de-estudos.md
│   └── referencias-tecnicas.md
├── modulos/
│   ├── 01-fundamentos-bgp/
│   ├── 02-ebgp-basico/
│   ├── 03-multihoming-failover/
│   ├── 04-peering-transito-ix/
│   ├── 05-politicas-filtros-seguranca/
│   ├── 06-as-path-regex-route-map/
│   ├── 07-traffic-engineering/
│   ├── 08-ibgp-route-reflector/
│   ├── 09-communities/
│   ├── 10-ix-multihoming-avancado/
│   ├── 11-operacao-troubleshooting/
│   ├── 12-seguranca-ipv6-atualizacoes/
│   └── 13-projeto-final-isp/
├── labs/
├── configs/
├── validacao/
├── troubleshooting/
├── gabaritos/
└── evidencias/
```

## Princípios de atualização

O curso-base foi publicado em 2012. Este repositório mantém os temas clássicos do material, mas separa as práticas atuais para revisão explícita: política eBGP segura, RPKI Route Origin Validation, IRR, ASN de 4 bytes, proteção de sessão, comunidades Large, IPv6 e procedimentos operacionais atuais. A disponibilidade e a sintaxe de cada recurso devem ser confirmadas na documentação da plataforma.

## Referências iniciais

- [RFC 4271 — A Border Gateway Protocol 4 (BGP-4)](https://www.rfc-editor.org/rfc/rfc4271)
- [RFC 6793 — BGP Support for Four-Octet AS Number Space](https://www.rfc-editor.org/rfc/rfc6793)
- [RFC 7454 — BGP Operations and Security](https://www.rfc-editor.org/rfc/rfc7454)
- [RFC 8212 — Default EBGP Route Propagation Behavior Without Policies](https://www.rfc-editor.org/rfc/rfc8212)
- [RFC 6811 — BGP Prefix Origin Validation](https://www.rfc-editor.org/rfc/rfc6811)
- [Documentação Cisco](https://www.cisco.com/c/en/us/support/ios-nx-os-software/ios-xe/products-installation-and-configuration-guides-list.html)
- [IX.br](https://ix.br/)
- [Registro.br](https://registro.br/)

## Como contribuir com seus estudos

Para cada laboratório, registre: objetivo, topologia, plataforma/versão, configuração inicial, comandos executados, resultado esperado, resultado observado, causa-raiz, correção e rollback. Nunca inclua senhas, chaves privadas, IPs públicos sensíveis ou dados de clientes reais.
