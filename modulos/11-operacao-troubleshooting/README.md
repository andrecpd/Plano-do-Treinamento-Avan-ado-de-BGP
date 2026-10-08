# Módulo 11 — Operação e troubleshooting

## Fluxo de diagnóstico
1. Delimitar escopo, horário de início e impacto.
2. Conferir interface, camada física e contadores.
3. Verificar conectividade IP entre vizinhos.
4. Verificar TCP/179, ACLs, VRF e endereços de origem.
5. Inspecionar estado BGP, logs, timers e parâmetros de sessão.
6. Verificar prefixos recebidos, filtros, best path, next-hop e instalação na RIB/FIB.
7. Comparar Looking Glass/telemetria externa quando disponível.
8. Aplicar correção controlada, confirmar recuperação e documentar causa-raiz.

## Evidências mínimas
- Horários e mudanças recentes.
- Saída de resumo BGP e detalhe do neighbor.
- Rotas recebidas/anunciadas quando a plataforma permite.
- Tabela BGP, tabela de roteamento e next-hop.
- Resultado antes/depois e rollback.

## Exercícios
Diagnostique: sessão Active, sessão Established sem prefixos, rota recebida mas não instalada, retorno assimétrico e anúncio ausente no upstream.
