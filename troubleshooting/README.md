# Troubleshooting BGP — matriz inicial

| Sintoma | Hipóteses | Próxima verificação |
|---|---|---|
| Idle/Active | Alcance IP, TCP/179, ACL, neighbor ou ASN incorreto | Ping, rota ao peer, logs, estado TCP e configuração |
| Established sem rotas | Nenhum anúncio, família desativada, filtro, política | Prefixos recebidos, políticas e capacidades negociadas |
| Rota recebida não instalada | Não é best path, next-hop inalcançável, filtro ou RIB concorrente | Tabela BGP, next-hop, RIB e motivo de seleção |
| Prefixo não anunciado | Prefixo ausente da RIB, máscara errada, filtro de saída | Rota de origem e advertised-routes |
| Tráfego assimétrico | Políticas diferentes nos sentidos, upstream ou aplicação | Traceroute, Looking Glass e anúncio visto externamente |
| Failover não ocorre | Sessão permanece ativa apesar de falha de caminho, timers, rota alternativa ausente | Detectores de falha, tracking, BFD quando suportado, best path |

## Registro de incidente
- Impacto:
- Início/fim:
- Mudança recente:
- Sintoma:
- Evidências:
- Causa-raiz:
- Mitigação:
- Correção definitiva:
- Validação:
- Rollback:
- Ação preventiva:
