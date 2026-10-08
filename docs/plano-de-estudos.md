# Plano de estudos — BGP avançado

## Perfil e carga horária sugerida

Trilha intermediária/avançada para redes ISP, com foco em prática no EVE-NG/GNS3. Sugestão: 30–40 horas para a trilha guiada, ampliável conforme o tempo dedicado a troubleshooting e ao projeto final.

## Método de cada sessão

- 20%: teoria e leitura de documentação.
- 50%: configuração e validação do laboratório.
- 20%: falhas induzidas e análise de causa-raiz.
- 10%: registro no GitHub e revisão do gabarito.

## Sequência recomendada

1. Fundamentos e seleção de rotas.
2. eBGP com um provedor.
3. Dois provedores, failover e engenharia de tráfego.
4. Peering, trânsito e IX.
5. Filtros, políticas de importação/exportação e RPKI/ROV.
6. Expressões AS_PATH e políticas escaláveis.
7. Prepend e anúncios seletivos.
8. iBGP, next-hop e route reflector.
9. Communities.
10. Múltiplos IX e clientes multihomed.
11. Operação e troubleshooting.
12. Segurança e IPv6.
13. Projeto integrador de ISP.

## Critério de conclusão por laboratório

- [ ] Topologia e endereçamento documentados.
- [ ] Adjacências atingem o estado esperado.
- [ ] Prefixos recebidos e anunciados conferidos.
- [ ] Tabela BGP e tabela de roteamento verificadas.
- [ ] Falha injetada e recuperação comprovada.
- [ ] Evidências salvas sem segredos.
- [ ] Gabarito consultado somente após tentativa própria.

## Regras de segurança

Use prefixos de documentação em laboratórios isolados. Não aplique políticas experimentais em redes de produção. Antes de qualquer mudança real, defina escopo, impacto, janela, plano de rollback e critério de sucesso.
