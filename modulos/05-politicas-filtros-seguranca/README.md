# Módulo 05 — Políticas, filtros e segurança de rotas

## Objetivos
Criar políticas de entrada e saída com princípio do menor privilégio e validar anúncios contra o plano de endereçamento autorizado.

## Controles para estudar
- Prefix-lists para limitar prefixos e comprimentos.
- Route-maps/policies para combinar filtros e ações.
- Bloqueio de prefixos privados, bogons e endereços especiais conforme a política.
- Validação de AS_PATH e proteção contra seu próprio ASN no caminho.
- Limites de prefixos recebidos (max-prefix), com limiar e ação definidos cuidadosamente.
- IRR/RPKI e RPKI Route Origin Validation (ROV).
- Política eBGP explícita, incluindo a referência [RFC 8212](https://www.rfc-editor.org/rfc/rfc8212).

## Laboratório
Configure listas permitidas distintas para cliente, peer e trânsito. Teste prefixo autorizado, prefixo não autorizado, prefixo mais específico indevido e origem inconsistente com ROA. Registre o resultado esperado e observado.

## Cuidado
ROV valida a origem do prefixo em relação ao ROA; não autentica todo o AS_PATH nem substitui filtros, IRR, monitoramento ou acordos operacionais.
