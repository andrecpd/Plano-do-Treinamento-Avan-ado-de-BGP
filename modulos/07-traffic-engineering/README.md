# Módulo 07 — AS_PATH prepend e anúncios seletivos

## Objetivos
Influenciar, sem garantia absoluta, o caminho de entrada usando políticas de anúncio.

## Conceitos
O prepend repete o ASN local no AS_PATH anunciado para tornar o caminho aparentemente mais longo para algumas redes remotas. A decisão final pertence à política dos AS remotos; LOCAL_PREF, communities do provedor, políticas comerciais e outros critérios podem superar o comprimento do AS_PATH.

## Laboratório
- Anuncie o mesmo prefixo a dois upstreams.
- Aplique prepend somente em um anúncio.
- Confira o AS_PATH visto do outro lado.
- Compare resultado antes/depois.
- Retire o prepend e valide rollback.

## Alternativas e limites
Investigue communities documentadas pelo provedor, anúncios seletivos e políticas específicas. Evite anunciar prefixos mais específicos apenas para engenharia de tráfego sem entender impacto global, filtros e acordos.
