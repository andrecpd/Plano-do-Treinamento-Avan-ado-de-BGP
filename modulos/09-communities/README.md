# Módulo 09 — BGP communities

## Tipos
- **Standard communities**: etiquetas de 32 bits, frequentemente usadas para políticas.
- **Extended communities**: formato estendido utilizado em diversos cenários.
- **Large Communities**: formato escalável definido pela RFC 8092, útil para ASN de 32 bits e políticas modernas.

## Laboratório
Crie comunidades internas para classificar rotas de cliente, peer e trânsito. Aplique ações distintas de LOCAL_PREF ou exportação. Teste que comunidades não reconhecidas não produzam efeitos inesperados.

## Provedores
Comunidades operacionais são específicas de cada rede. Nunca invente ou presuma seu significado: consulte a documentação do upstream e confirme escopo, suporte e comportamento.
