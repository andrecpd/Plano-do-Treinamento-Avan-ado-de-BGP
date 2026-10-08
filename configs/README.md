# Configurações de laboratório

Armazene uma pasta por LAB, com um arquivo por roteador e anotações sobre plataforma/versão.

Estrutura sugerida:
```text
configs/
  lab-01/
    R1.cfg
    R2.cfg
    README.md
```

## Boas práticas
- Identifique claramente comandos específicos da plataforma.
- Use comentários para explicar intenção da política.
- Nunca versionar credenciais, chaves privadas ou configurações reais sensíveis.
- Faça diff antes/depois de mudanças.
- Indique os pré-requisitos de rotas estáticas ou conectividade necessários para originar prefixos.
- Não considerar um comando aceito como prova de que a política está funcionando; valide o plano de controle e o encaminhamento.
