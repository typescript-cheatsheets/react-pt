# Então você quer contribuir!

Obrigado por ajudar a comunidade! Nós estamos constantemente buscando por contribuidores e mantenedores então você é mais do que bem-vindo.

Eu pensei em estipular alguns princípios básicos que nós iremos seguir para evitar que este repositório se torne muito confuso e perca seu valor.

1. **Nós somos uma CHEATSHEET antes de tudo**: Todos os exemplos devem ser o mais simples possível, fáceis de encontrar, e apresentáveis para copiar-e-colar.
2. **Explicações claras**: Nada além de 1 ou 2 sentenças de explicação, mais do que isso incluímos a tag `detalhes`.
3. **SOMENTE React + TypeScript**: React possui um imenso ecossistema e é impossível cobri-lo completamente. Isto inclui Redux. Sugiro ás pessoas a manter listas separadas para coisas como React + Apollo Graphql, por exemplo. Nós também não tentamos convencer ninguém a usar TypeScript, estamos aqui para ajudar as pessoas que já decidiram experimentá-lo.
4. **Inclua links para o sandbox do Typescript**: Sempre que adicionar um exemplo de código com mais de quatro linhas, adicione um link para o sandbox com o código em Typescript. Use as opções padrão do compilador.

E é isso! Outra vez, estamos muito felizes que você esteja pensando em ajudar e, quem sabe, a pessoa que você está ajudando pode ser você mesma no futuro!

## Estrutura do projeto

- O conteúdo completo está em `/docs`
  - O `/docs/basic` é compilado no `README.md` para preservar a legibilidade do GitHub por meio de GitHub actions, obrigado
- `/website` consome o conteúdo de `/docs`, que é um site [Docusaurus 2](https://docusaurus.io/), que possui o sistema de [busca Algolia](https://www.algolia.com/) (obrigado a ambas as equipes pelo apoio!)

O site está hospedado no Netlify, na conta pessoal do swyx.

Para rodar o docsite localmente:

```bash
yarn # instala as dependências
## garanta que as dependências também sejam instaladas em /website
cd website && yarn start
```

exemplo de instalação bem-sucedida

```
yarn run v1.22.4
warning package.json: No license field
$ docusaurus start
Starting the development server...

✔ Client
  Compiled successfully in 9.61s

ℹ ｢wds｣: Project is running at http://localhost:3000/
ℹ ｢wds｣: webpack output is served from /
ℹ ｢wds｣: Content not from webpack is served from /Users/wanshawn/Work/react-typescript-cheatsheet/website
ℹ ｢wds｣: 404s will fallback to /index.html

✔ Client
  Compiled successfully in 116.41ms
```
