<div align="center">
<h1>React+TypeScript Cheatsheets em Português</h1>

<a href="https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/81">
  <img
    height="80"
    width="80"
    alt="react + ts logo"
    src="https://user-images.githubusercontent.com/6764957/53868378-2b51fc80-3fb3-11e9-9cee-0277efe8a927.png"
    align="left"
  />
</a>

<p>Cheatsheets para desenvolvedores com experiência em React que estão iniciando com TypeScript</p>

[**Web docs**](https://react-typescript-cheatsheet.netlify.app/docs/basic/setup) |
[中文翻译](https://github.com/fi3ework/blog/tree/master/react-typescript-cheatsheet-cn) |
[**Español**](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet-es) |
[Contribute!](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/blob/master/CONTRIBUTING.md) |
[Ask!](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new/choose)

</div>

---

<div align="center">

:wave: Este repositório é mantido por [@giseladifini](https://twitter.com/GiselaDifini) e [@swyx](https://twitter.com/swyx). Estamos muito felizes que você quer experimentar React com Typescript!
Se você perceber algo de errado ou faltando, por favor abra uma [issue](https://github.com/typescript-cheatsheets/react-pt/issues/new)! :+1:

</div>

---

## Todas as dicas de React + TypeScript

- **Cheatsheet Básico** ([`/README.md`](/README.md#basic-cheatsheet-table-of-contents)) é focado em ajudar desenvolvedores React a começar a usar TS com React **apps**
  - Foco nas melhores práticas com exemplos para copiar e colar.
  - Explica alguns tipos básicos de uso de TS e configuração ao longo do caminho.
  - Responde às perguntas mais frequentes.
  - Não cobre a lógica de tipo genérico em detalhes. Em vez disso, preferimos ensinar técnicas de solução de problemas simples para iniciantes.
  - O objetivo é se familiarizar com TS sem precisar aprender _muito_ sobre TS.
- **Cheatsheet Avançado** ([`/AVANÇADO.md`](https://react-typescript-cheatsheet.netlify.app/docs/advanced/intro)) ajuda a mostrar e explicar o uso avançado de tipos genéricos para pessoas que escrevem utilitários/funções/props de renderização/componentes de ordem superior (HOCs) reutilizáveis ​​e **bibliotecas** TS+React.
  - Possui dicas e truques diversos para usuários profissionais.
  - Conselhos para contribuir com DefinitelyTyped.
  - O Objetivo é tirar _total vantagem_ sobre o TypeScript.
- **Cheatsheet de migração** ([`/MIGRANDO.md`](https://react-typescript-cheatsheet.netlify.app/docs/migration/intro)) ajuda a reunir conselhos para a migração incremental de grandes bases de código de JS ou Flow, **de pessoas que já fizeram isso**.
  - Nós não tentamos convencer as pessoas a mudar, apenas ajudar as pessoas que já decidiram isso.
  - ⚠️ Esta é uma nova cheatsheet, toda ajuda é bem-vinda.
- **Cheatsheet de HOCs** ([`/HOC.md`](https://react-typescript-cheatsheet.netlify.app/docs/hoc/intro)) especificamente ensina as pessoas a escrever HOCs com a ajuda de exemplos.
  - Familiaridade com [Genéricos](https://www.typescriptlang.org/docs/handbook/generics.html) é necessário.
  - ⚠️ Esta é uma nova cheatsheet, toda a assistência é bem-vinda.

---

### Tabela de conteúdos da Cheatsheet básica

<details>

<summary><b>Expandir Tabela de Conteúdo</b></summary>

<!--START-SECTION:setup-toc-->

- [Seção 1: Configuração](#seção-1-configuração)
- [Pré-requisitos](#pré-requisitos)
- [Ferramentas iniciais de React + TypeScript](#ferramentas-iniciais-de-react--typeScript)
- [Importar React](#importar-react)
<!--END-SECTION:setup-toc-->
- [Seção 2: Primeiros Passos](#seção-2-primeiros-passos)
  - [Componente de Função](#componente-de-função)
  - [Hooks](#hooks)
  - [useState](#usestate)
  - [useReducer](#usereducer)
  - [useEffect](#useeffect)
  - [useRef](#useref)
  - [useImperativeHandle](#useimperativehandle)
  - [Hooks Customizados](#custom-hooks)
  - [Componentes de Classe](#class-components)
  - [Talvez você não precise do `defaultProps`](#you-may-not-need-defaultprops)
  - ["Tipando" `defaultProps`](#typing-defaultprops)
  - [Consumindo Props de um Componente com defaultProps](#consuming-props-of-a-component-with-defaultprops)
    - [Declaração do Problema](#problem-statement)
    - [Solução](#solution)
  - [Discussões e Conhecimentos Diversos](#misc-discussions-and-knowledge)
  - [Tipos ou Interfaces?](#types-or-interfaces)
  - [Exemplos básicos do tipo Prop](#basic-prop-types-examples)
  - [Exemplos úteis do tipo React Prop](#useful-react-prop-type-examples)
  - [getDerivedStateFromProps](#getDerivedStateFromProps)
  - [Formulários e Eventos](#forms-and-events)
  - [Context](#context)
  - [Exemplo Básico](#basic-example)
  - [Exemplo Extendido](#extended-example)
  - [forwardRef/createRef](#forwardrefcreateref)
  - [Portais](#portals)
  - [Limites de erros](#error-boundaries)
    - [Opção 1: Usando react-error-boundary](#option-1-using-react-error-boundary)
    - [Opção 2: Criando um componente "error boundary" personalizado](#options-2-writing-your-custom-error-boundary-component)
  - [Concurrent React/React Suspense](#concurrent-reactreact-suspense)
  <!--START-SECTION:types-toc-->
- [Manual de resolução de problemas: Tipos](#troubleshooting-handbook-types)
  - [Tipos de União e Tipos de Proteção](#union-types-and-type-guarding)
  - [Tipos Opcionais](#optional-types)
  - [Tipos de Enum](#enum-types)
  - [Tipos de Asserção](#type-assertion)
  - [Simulando Tipos Nominais](#simulating-nominal-types)
  - [Tipos de Interseção](#intersection-types)
  - [Tipos de União](#union-types)
  - [Sobrecarregando Tipos de Função](#overloading-function-types)
  - [Usando Tipos Inferidos](#using-inferred-types)
  - [Usando Tipos Parciais](#using-partial-types)
  - [Os Tipos de que preciso não foram exportados!](#the-types-i-need-werent-exported)
  - [Os Tipos de que preciso não existem!](#the-types-i-need-dont-exist)
    - [Exagerando com `any` em tudo](#slapping-any-on-everything)
    - [Autogerando tipos](#autogenerate-types)
    - [Tipando Hooks Exportados](#typing-exported-hooks)
    - [Tipando Componentes Exportados](#typing-exported-components)
    <!--END-SECTION:types-toc-->
- [Manual de resolução de problemas: Operadores](#troubleshooting-handbook-operators)
- [Manual de resolução de problemas: Utilitários](#troubleshooting-handbook-utilities)
- [Manual de resolução de problemas: tsconfig.json](#troubleshooting-handbook-tsconfigjson)
- [Manual de resolução de problemas: Erros en tipos oficiais](#troubleshooting-handbook-bugs-in-official-typings)
- [Bases de código de React + TypeScript recomendadas para aprender](#recommended-react--typescript-codebases-to-learn-from)
- [Ferramentas e integração em editores](#editor-tooling-and-integration)
- [Linting](#linting)
- [Outros recursos sobre React + TypeScript](#other-react--typescript-resources)
- [Discussões recomendadas sobre React + TypeScript](#recommended-react--typescript-talks)
- [Hora de realmente aprender TypeScript](#time-to-really-learn-typescript)
- [Aplicação de Exemplo](#example-app)
- [Minha pergunta não foi respondida aqui!](#my-question-isnt-answered-here)
  - [Contribuidores](#contributors)

</details>

<!--START-SECTION:setup-->

# Seção 1: Configuração

## Pré-requisitos

1. Uma boa compreensão de [React](https://reactjs.org).
2. Familiaridade com os tipos básicos de [TypeScript](https://www.typescriptlang.org/docs/handbook/basic-types.html) ( [O guia de 2ality](http://2ality.com/2018/04/type-notation-typescript.html) é de grande ajuda. Se você é completamente novato em TypeScript, dê uma olhada no [tutorial de chibicode](https://ts.chibicode.com/todo/) ).
3. Ter lido [a seção de TypeScript na documentação oficial do React](https://reactjs.org/docs/static-type-checking.html#typescript).
4. Ter lido [a seção do React do novo playground de TypeScript](http://www.typescriptlang.org/play/index.html?jsx=2&esModuleInterop=true&e=181#example/typescript-with-react) ( Opcional: também acompanhar os mais de 40 exemplos na seção de exemplos do [playground](http://www.typescriptlang.org/play/index.html) ).

Este guia sempre assumirá que você está usando a última versão de Typescript. Notas para versões mais antigas usarão a etiqueta `<details>`.

## Ferramentas iniciais de React + TypeScript

Configurações na nuvem:

- [Playground do TypeScript com React](https://www.typescriptlang.org/play?#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcA5FDvmQNwCwAUKJLHAN5wCuqWAyjMhhYANFx4BRAgSz44AXzhES5Snhi1GjLAA8W8XBAB2qeAGEInQ0KjjtycABsscALxwAFAEpXAPnaM4OANjeABtA0sYUR4Yc0iAXVcxPgEhdwAGT3oGAOTJaXx3L19-BkDAgBMIXE4QLCsAOhhgGCckgAMATQsgh2BcAGssCrgAEjYIqwVmutR27MC5LM0yuEoYTihDD1zAgB4K4AA3H13yvbAfbs5e-qGRiYspuBmsVD2Aekuz-YAjThgMCMcCMpj6gxcbGKLj8MTiVnck3gAGo4ABGTxyU6rcrlMF3OB1H5wT7-QFGbG4z6HE65ZYMOSMIA) apenas se você estiver depurando tipos (e relatando problemas), não para executar código.
- [CodeSandbox](http://ts.react.new) - IDE na nuvem, inicializa super rápido.
- [Stackblitz](https://stackblitz.com/edit/react-typescript-base) - IDE na nuvem, inicializa super rápido.

Configurações de desenvolvimento local:

- [Next.js](https://nextjs.org/docs/basic-features/typescript): `npx create-next-app -e with-typescript` irá criar no seu diretório atual.
- [Create React App](https://facebook.github.io/create-react-app/docs/adding-typescript): `npx create-react-app name-of-app --template typescript` irá criar em um novo diretório.
- [Meteor](https://guide.meteor.com/build-tool.html#typescript): `meteor create --typescript name-of-my-new-typescript-app`
- [Ignite](https://github.com/infinitered/ignite#use-ignite-andross-infinite-red-andross-boilerplate) para React Native: `ignite new myapp`
- [TSDX](https://tsdx.io/): `npx tsdx create mylib` para Creating React+TS _libraries_

<details>
<summary>
Outras ferramentas
</summary>

Ferramentas menos maduras mas que vale a pena conferir:

- [Vite](https://twitter.com/swyx/status/1282727239230996480?lang=en): `npm init vite-app my-react-project --template react-ts` (nota - ainda não está na versão v1.0, mas é muito rápida).
- [Snowpack](<https://www.snowpack.dev/#create-snowpack-app-(csa)>): `npx create-snowpack-app my-app --template app-template-react-typescript`
- [Docusaurus v2](https://v2.docusaurus.io/docs/installation) com [suporte a TypeScript](https://v2.docusaurus.io/docs/typescript-support)
- [Parcel](https://v2.parceljs.org/languages/typescript/)
- [JP Morgan's `modular`](https://github.com/jpmorganchase/modular): CRA + TS + Yarn Workspaces toolkit. `yarn create modular-react-app <project-name>`

Manual de configuração:

- [O guia de Basarat](https://github.com/basarat/typescript-react/tree/master/01%20bootstrap) para uma **configuração manual** de React + TypeScript + Webpack + Babel.
- Em particular, certifique-se de ter instalado `@types/react` e `@types/react-dom` .( [Leia mais sobre o projeto DefinitelyTyped caso você não esteja familiarizado](https://definitelytyped.org/) ).
- Existem também muitos _boilerplates_ de React + Typescript. Por favor consulte [nossa lista de outros recursos](https://react-typescript-cheatsheet.netlify.app/docs/basic/recommended/resources/).

</details>

## Import React

```tsx
import * as React from 'react';
import * as ReactDOM from 'react-dom';
```

Este é o [caminho mais seguro no futuro](https://www.reddit.com/r/reactjs/comments/iyehol/import_react_from_react_will_go_away_in_distant/) para importar React. Se você definir `--allowSyntheticDefaultImports` (ou adicionar` "allowSyntheticDefaultImports": true`) em seu `tsconfig.json`, você poderá importar como se faz normalmente em jsx:

```tsx
import React from 'react';
import ReactDOM from 'react-dom';
```

<details>

<summary>Explicação</summary>

Por que usar `allowSyntheticDefaultImports` ao invés de `esModuleInterop`? [Daniel Rosenwasser](https://twitter.com/drosenwasser/status/1003097042653073408) comentou que é melhor para webpack/parcel. Para consultar mais argumentos dessa discussão <https://github.com/wmonk/create-react-app-typescript/issues/214>

Você também deveria verificar [a nova documentação do TypeScript para descrições oficiais entre cada _flag_ do compilador](https://www.typescriptlang.org/tsconfig#allowSyntheticDefaultImports)!

</details>

<!--END-SECTION:setup-->

<!--START-SECTION:function-components-->

# Seção 2: Primeiros Passos

## Componente de Função

Podem ser escritos como funções normais que recebem `props` como argumento e retornam um elemento JSX.

```tsx
type AppProps = { message: string }; /* também se pode usar uma interface */
const App = ({ message }: AppProps) => <div>{message}</div>;
```

<details>

<summary><b>Por que `React.FC` é desencorajado? E sobre `React.FunctionComponent` / `React.VoidFunctionComponent`?</b></summary>

Você pode ver isso em muitas bases de código React + TypeScript:

```tsx
const App: React.FunctionComponent<{ message: string }> = ({ message }) => (
  <div>{message}</div>
);
```

No entanto, o consenso geral hoje é que o uso de `React.FunctionComponent` (ou a abreviação` React.FC`) é [desencorajado] (https://github.com/facebook/create-react-app/pull/8177). Isto é um ponto de vista, é claro, mas se você concorda e deseja remover `React.FC` da sua base de código, você pode usar [este jscodeshift codemod] (https://github.com/gndelia/codemod-replace-react- fc-typescript).

Algumas diferenças da versão de "função normal":

- `React.FunctionComponent` é explícito sobre o tipo de retorno, enquanto a versão normal da função é implícita (ou então precisa de anotações adicionais).

- Fornece verificação de tipos e preenchimento automático para propriedades estáticas como `displayName`,` propTypes` e `defaultProps`.

  - Observe que existem alguns problemas conhecidos usando `defaultProps` com` React.FunctionComponent`. Consulte [este problema para obter detalhes] (https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/87). Nós mantemos uma seção `defaultProps` separada para que você também possa consultar.

- Fornece uma definição implícita de `children` (veja abaixo) - no entanto, há alguns problemas com o tipo `children` implícito (por exemplo, DefinitelyTyped#33006), e é melhor ser explícito sobre os componentes que consomem `children`, de qualquer maneira.

```tsx
const Title: React.FunctionComponent<{ title: string }> = ({
  children,
  title,
}) => <div title={title}>{children}</div>;
```

<details>
<summary>
Usando `React.VoidFunctionComponent` ou` React.VFC` como alternativa
</summary>

A partir da versão [@types/react 16.9.48] (https://github.com/DefinitelyTyped/DefinitelyTyped/pull/46643), você também poderá usar o tipo `React.VoidFunctionComponent` ou `React.VFC` se quiser tipar `children` explicitamente. Esta é uma solução provisória até que `FunctionComponent` não aceite nenhum `children` por padrão (planejado para `@types/react@^18.0.0`).

```ts
type Props = { foo: string };

// OK agora mas futuramente causará erro
const FunctionComponent: React.FunctionComponent<Props> = ({
  foo,
  children,
}: Props) => {
  return (
    <div>
      {foo} {children}
    </div>
  ); // OK
};

// OK agora mas futuramente se tornará obsoleto
const VoidFunctionComponent: React.VoidFunctionComponent<Props> = ({
  foo,
  children,
}) => {
  return (
    <div>
      {foo}
      {children}
    </div>
  );
};
```

</details>
- _No futuro_, ele poderá marcar automaticamente os `props` como `readonly` (somente leitura), embora isso seja um ponto discutível se o objeto `props` for desestruturado na lista de parâmetros.

Na maioria dos casos, faz pouca diferença qual sintaxe é usada, mas você pode preferir a natureza mais explícita de `React.FunctionComponent`.

</details>

<details>
<summary><b>Problemas menores</b></summary>

Esses padrões não são suportados:

** Renderização condicional **

```tsx
const MyConditionalComponent = ({ shouldRender = false }) =>
  shouldRender ? <div /> : false; // tampouco faça isso em JS
const el = <MyConditionalComponent />; // gera um erro
```

Isso ocorre porque, devido às limitações do compilador, os componentes de função não podem retornar nada além de uma expressão JSX ou `null`, caso contrário, ele reclama com uma mensagem de erro enigmática dizendo que outro tipo não pode ser atribuído ao Elemento.

```tsx
const MyArrayComponent = () => Array(5).fill(<div />);
const el2 = <MyArrayComponent />; // gera um erro
```

**Array.fill**

Infelizmente, apenas anotar o tipo de função não vai ajudar, então se você realmente precisar retornar outros tipos exóticos que o React suporta, será necessário executar uma declaração de tipo:

```tsx
const MyArrayComponent = () => (Array(5).fill(<div />) as any) as JSX.Element;
```

[Veja o comentário de @ferdaber aqui] (https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/57).

</details>

<!--END-SECTION:function-components-->

<!--START-SECTION:hooks-->

## Hooks
