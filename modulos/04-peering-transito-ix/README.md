# Módulo 04 — Peering, trânsito e IX

## Conceitos
- **Trânsito IP**: um provedor oferece alcance a destinos além de sua própria rede.
- **Peering**: duas redes trocam tráfego para destinos acordados, normalmente sem oferecer trânsito global uma à outra.
- **IX / ponto de troca**: infraestrutura que facilita interconexão entre redes participantes.
- **Route server**: facilita a troca de rotas no IX; em geral, não fica no caminho de dados do tráfego trocado entre participantes.

## Prática
Desenhe um AS conectado a um upstream e a um IX. Separe a política para rotas de trânsito, rotas de peering e rotas de clientes. Valide o conjunto de prefixos recebidos e anunciados por cada sessão.

## Atualização
Procedimentos, formulários, portais, políticas de participantes e serviços do IX.br mudam ao longo do tempo. Consulte a documentação oficial atual do [IX.br](https://ix.br/) e não reutilize instruções administrativas de 2012 sem confirmação.

## Exercícios
Explique por que uma rota aprendida de um peer não deve ser exportada indiscriminadamente para outro peer; documente filtros de importação e exportação para cada classe de sessão.
