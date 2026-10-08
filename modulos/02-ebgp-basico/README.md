# Módulo 02 — eBGP básico com provedor

## Objetivos
Configurar uma sessão eBGP, anunciar somente prefixos autorizados e validar o que entra e sai da sessão.

## Roteiro
1. Documente ASN local/remoto, endereços, prefixos autorizados e responsabilidades.
2. Configure interfaces e teste ping entre os endereços de vizinhança.
3. Configure o neighbor e política explícita de importação/exportação.
4. Verifique Established, contadores, prefixos recebidos e anúncios enviados.
5. Simule remote-as incorreto, ACL bloqueando TCP/179 e prefixo não existente na RIB.

## Checklist de validação
- [ ] Sessão Established.
- [ ] Prefixos recebidos conferidos.
- [ ] Prefixos anunciados conferidos com comando equivalente a `advertised-routes`.
- [ ] Filtros aplicados nos dois sentidos.
- [ ] Registro do resultado e rollback.

## Perguntas
Por que não basta observar o estado Established? Como provar que um prefixo está sendo anunciado ao peer? Qual é o risco de uma política de exportação permissiva?

## Nota de plataforma
Use a sintaxe de IOS/IOS XE/IOS XR/FRR correspondente à imagem do laboratório. Prefira políticas explícitas; confirme a semântica de filtros e route refresh na versão usada.
