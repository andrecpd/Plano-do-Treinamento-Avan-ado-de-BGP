# Validação — checklist operacional

Para cada sessão eBGP/iBGP, confirme:

- [ ] Interfaces e endereços corretos.
- [ ] Conectividade IP e VRF corretas.
- [ ] Sessão BGP no estado esperado.
- [ ] ASN remoto e parâmetros de sessão conferidos.
- [ ] Prefixos recebidos revisados.
- [ ] Prefixos aceitos/rejeitados coerentes com a política.
- [ ] Best path e next-hop explicados.
- [ ] Rotas instaladas na RIB/FIB conforme esperado.
- [ ] Anúncios de saída limitados ao autorizado.
- [ ] Failover e retorno testados.
- [ ] Evidências e rollback documentados.

## Comandos comuns Cisco IOS/IOS XE
```text
show ip bgp summary
show ip bgp
show ip route bgp
show ip bgp neighbors
show ip bgp neighbors <IP-DO-PEER> advertised-routes
show ip bgp neighbors <IP-DO-PEER> routes
```

A disponibilidade e a sintaxe dos comandos variam. Em algumas versões, use a família `show bgp ipv4 unicast`. Consulte o guia da plataforma.
