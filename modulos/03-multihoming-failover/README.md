# Módulo 03 — Multihoming, failover e engenharia de tráfego

## Objetivos
Desenhar conectividade com dois upstreams, diferenciar controle de tráfego de entrada e saída e provar convergência em falhas.

## Cenário
AS65010 conecta-se a AS65020 e AS65030. O prefixo de laboratório do cliente é 198.51.100.0/24. Use links e endereços de documentação conforme o diagrama criado para o lab.

## Técnicas
- **Saída**: LOCAL_PREF para política do AS; WEIGHT é local ao roteador Cisco.
- **Entrada**: anúncios seletivos, AS_PATH prepend e comunidades aceitas pelo provedor.
- **Failover**: perda de interface, queda de sessão BGP, perda de next-hop ou falha parcial do upstream.
- **BFD**: pode acelerar detecção se suportado e configurado nas duas pontas; validar impacto e temporizadores.

## Exercícios
1. Faça o upstream A preferido para saída e B como contingência.
2. Simule a falha de A e meça a convergência.
3. Faça prepend seletivo para influenciar a preferência de entrada.
4. Explique por que prepend não garante o caminho de entrada.
5. Documente risco, monitoramento e rollback.
