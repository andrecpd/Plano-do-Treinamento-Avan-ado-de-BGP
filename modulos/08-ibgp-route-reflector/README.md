# Módulo 08 — iBGP, next-hop e route reflector

## Objetivos
Entender a distribuição iBGP, a regra clássica de não reanunciar rotas iBGP a outro peer iBGP e como route reflectors reduzem a necessidade de malha completa.

## Atividades
1. Configure três roteadores no mesmo AS.
2. Teste uma topologia full-mesh e registre a distribuição de rotas.
3. Converta um nó em route reflector e configure clientes.
4. Valide NEXT_HOP, alcançabilidade via IGP e best path.
5. Induza next-hop inalcançável e observe os sintomas.

## Cuidados
Documente cluster ID, redundância de route reflectors, políticas e desenho de falha. Route reflection altera a distribuição de caminhos; valide possíveis efeitos sobre diversidade de rotas e seleção.
