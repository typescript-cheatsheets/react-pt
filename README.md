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

Há suporte para Hooks em [`@types/react` a partir da versão v16.8](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/a05cc538a42243c632f054e42eab483ebf1560ab/types/react/index.d.ts#L800-L1031).

## useState

Inferência automática de tipos funciona bem com valores simples

```tsx
const [val, toggle] = React.useState(false);
//  infere-se que `val` é do tipo boolean
// `toggle` aceita apenas booleans
```

Veja também no artigo em inglês (utilizando [Using Inferred Types](https://react-typescript-cheatsheet.netlify.app/docs/basic/troubleshooting/types/#using-inferred-types) se precisar usar um tipo complexo para o qual você depende da inferência.

No entanto, muitos hooks são inicializados com valores nulos e você pode se perguntar como deve fazer para definir o tipo. Declare explicitamente o tipo e use um tipo de união (union type):

```tsx
const [user, setUser] = React.useState<IUser | null>(null);

// mais tarde...
setUser(newUser);
```

Você também pode usar asserções de tipo (type assertions) se um estado for inicializado logo após o setup e sempre tiver um valor definido após o setup:

```tsx
const [user, setUser] = React.useState<IUser>({} as IUser);

// mais tarde...
setUser(newUser);
```

"Metimos" temporariamente para o compilador de Typesctipr que `{}` é do tipo `IUser`. Você deve então configurar o estado de `user` — se não o fizer, o resto do seu código pode depender do fato de que `user` é do tipo `IUser` e isso pode levar a erros em tempo de execução (runtime errors).

## useReducer

Você pode utilizar Uniões de tipos com propriedades definidas ([Discriminated Unions](https://www.typescriptlang.org/docs/handbook/typescript-in-5-minutes-func.html#discriminated-unions)) para actions da função reducer. Não esqueça de definir o tipo de retorno, caso contário, o compilador irá inferir o tipo.

```tsx
const initialState = { count: 0 };

type ACTIONTYPE =
  | { type: "increment"; payload: number }
  | { type: "decrement"; payload: string };

function reducer(state: typeof initialState, action: ACTIONTYPE) {
  switch (action.type) {
    case "increment":
      return { count: state.count + action.payload };
    case "decrement":
      return { count: state.count - Number(action.payload) };
    default:
      throw new Error();
  }
}

function Counter() {
  const [state, dispatch] = React.useReducer(reducer, initialState);
  return (
    <>
      Count: {state.count}
      <button onClick={() => dispatch({ type: "decrement", payload: "5" })}>
        -
      </button>
      <button onClick={() => dispatch({ type: "increment", payload: 5 })}>
        +
      </button>
    </>
  );
}
```

[Veja no TypeScript Playground](https://www.typescriptlang.org/play?#code/LAKFEsFsAcHsCcAuACAVMghgZ2QJQKYYDGKAZvLJMgOTyEnUDcooRsAdliuO+IuBgA2AZUQZE+ZAF5kAbzYBXdogBcyAAwBfZmBCIAntEkBBAMIAVAJIB5AHLmAmgAUAotOShkyAD5zkBozVqHiI6SHxlagAaZGgMfUFYDAATNXYFSAAjfHhNDxAvX1l-Q3wg5PxQ-HDImLiEpNTkLngeAHM8ll1SJRJwDmQ6ZIUiHIAKLnEykqNYUmQePgERMQkY4n4ONTMrO0dXAEo5T2aAdz4iAAtkMY3+9gA6APwj2ROvImxJYPYqmsRqCp3l5BvhEAp4Ow5IplGpJhIHjCUABqTB9DgPeqJFLaYGfLDfCp-CIAoEFEFeOjgyHQ2BKVTNVb4RF05TIAC0yFsGWy8Fu6MeWMaB1x5K8FVIGAUglUwK8iEuFFOyHY+GVLngFD5Bx0Xk0oH13V6myhplZEm1x3JbE4KAA2vD8DFkuAsHFEFcALruAgbB4KAkEYajPlDEY5GKLfhCURTHUnKkQqFjYEAHgAfHLkGb6WpZI6WfTDRSvKnMgpEIgBhxTIJwEQANZSWRjI5SdPIF1u8RXMayZ7lSphEnRWLxbFNagAVmomhF6fZqYA9OXKxxM2KQWWK1WoTW643m63pB2u+7e-3SkEQsPamOGik1FO55p08jl6vdxuKcvv8h4yAmhAA)

<details>

<summary><b>Uso do tipo `Reducer` da biblioteca `redux`</b></summary>

Caso você use a biblioteca [redux](https://github.com/reduxjs/redux) para escrever a reducer function, ela fornece um helper conveniente do formato `Reducer<State, Action>` que cuida do tipo do retorno para você.

Assim, o exemplo de reducer acima se torna:

```tsx
import { Reducer } from 'redux';

export function reducer: Reducer<AppState, Action>() {}
```

</details>

## useEffect / useLayoutEffect

Ambos `useEffect` e `useLayoutEffect` são usados para executar <b>efeitos colaterais</b> e retornam uma função de limpeza opcional, o que significa que se eles não lidam com retorn de valores, nenhum tipo é necessário. Ao usar `useEffect`, tome cuidado para não retornar nada além de uma função ou `undefined`, caso contrário, tanto o TypeScript quanto o React apresentarão error. Isso pode ser sutil ao usar arrow functions:

```ts
function DelayedEffect(props: { timerMs: number }) {
  const { timerMs } = props;

  useEffect(
    () =>
      setTimeout(() => {
        /* faça coisas aqui */
      }, timerMs),
    [timerMs]
  );
  // um exemplo ruim! setTimeout implicitamente retorna número (tipo number)
  // porque o corpo da arrow function não está entre chaves
  return null;
}
```

<details>
<summary>
Solução para o exemplo acima
</summary>

```tsx
function DelayedEffect(props: { timerMs: number }) {
  const { timerMs } = props;

  useEffect(() => {
    setTimeout(() => {
      /* faça coisas aqui */
    }, timerMs);
  }, [timerMs]);
  // melhor; utilize a keyword void para ter certeza de que retornará undefined
  return null;
}
```

</details>

## useRef

Em TypeScript, `useRef` retorn uma referência que pode ser [somente leitura](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/abd69803c1b710db58d511f4544ec1b70bc9077c/types/react/v16/index.d.ts#L1025-L1039) ou [mutável](https://github.com/DefinitelyTyped/DefinitelyTyped/blob/abd69803c1b710db58d511f4544ec1b70bc9077c/types/react/v16/index.d.ts#L1012-L1023), a depender se o tipo fornecido cobre totalmente o valor inicial ou não. Escolha um que se adapte ao seu caso de uso.
### Opção um 1: ref de um elemento da DOM

**[Para acessar um elemento da DOM](https://reactjs.org/docs/refs-and-the-dom.html):** forneça apenas o tipo de elemento como argumento e use `null` como valor inicial. Neste caso, a referência retornada terá um `.current` somente leitura que é gerenciado pelo React. O TypeScript espera que você dê esta referência à prop `ref` de um elemento:

```tsx
function Foo() {
  // - Se possível, seja o mais específico possível. Por exemplo, HTMLDivElement
  // é melhor que HTMLElement e muito melhor que Element.
  // - Em termos técnicos, isso retorna RefObject<HTMLDivElement>
  const divRef = useRef<HTMLDivElement>(null);

  useEffect(() => {
    // Observe que ref.current pode ser null. Isso é esperado, porque você pode
    // renderizar condicionalmente o elemento da ref, ou você poderia esquecer de atribuí-lo a um elemento
    if (!divRef.current) throw Error("divRef is not assigned");

    // Agora você tem certeza que divRef.current é um HTMLDivElement
    doSomethingWith(divRef.current);
  });

  // Atribua a ref a um elemento para que o React possa gerenciar-lo pra você
  return <div ref={divRef}>etc</div>;
}
```

Se você tem certeza de que `divRef.current` nunca será nulo, também é possível usar o operador de asserção não nulo `!`:

```tsx
const divRef = useRef<HTMLDivElement>(null!);
// Mais tarde... não precisa checar se o elemento é nulo
doSomethingWith(divRef.current);
```

Observe que você está desativando a segurança de tipo aqui - você terá um erro de tempo de execução se esquecer de atribuir a referência a um elemento na renderização ou se o elemento com ref for renderizado condicionalmente.

<details>
<summary>
  
  Dica: Escolhendo qual `HTMLElement` usar
  
</summary>

Refs demandam especificidade - não é suficiente apenas especificar qualquer `HTMLElement` antigo. Se você não souber o nome do tipo de elemento necessário, verifique [lib.dom.ts](https://github.com/microsoft/TypeScript/blob/v3.9.5/lib/lib.dom. d.ts#L19224-L19343) ou cometa um erro de tipo intencional e deixe o compilador lhe dizer o tipo correto:

![image](https://user-images.githubusercontent.com/6764957/116914284-1c436380-ac7d-11eb-9150-f52c571c5f07.png)

</details>

### Opção 2: Valor ref mutável

**[Para ter um valor mutável](https://reactjs.org/docs/hooks-faq.html#is-there-something-like-instance-variables):** forneça o tipo desejado e verifique se o valor inicial pertence totalmente a esse tipo:

```tsx
function Foo() {
  // Tecnicamente, isto retorna MutableRefObject<number | null>
  const intervalRef = useRef<number | null>(null);

  // Você mesmo genrencia a ref (por isso se chama MutableRefObject!)
  useEffect(() => {
    intervalRef.current = setInterval(...);
    return () => clearInterval(intervalRef.current);
  }, []);

  // A ref (intervalRef) não é passado para a prop "ref" de nenhum elemento
  return <button onClick={/* clearInterval the ref */}>Cancel timer</button>;
}
```

### Veja também (conteúdo em inglês)

- [Issue relacionada por @rajivpunjabi](https://github.com/typescript-cheatsheets/react/issues/388) - [Playground](https://www.typescriptlang.org/play#code/JYWwDg9gTgLgBAKjgQwM5wEoFNkGN4BmUEIcARFDvmQNwCwAUI7hAHarwCCYYcAvHAAUASn4A+OAG9GjOHAD0CBLLnKGcxHABiwKBzgQwMYGxS4WUACbBWAczgwIcSxFwBXEFlYxkxtgDoVTQBJVmBjZAAbOAA3KLcsOAB3YEjogCNE1jc0-zgAGQBPG3tHOAAVQrAsAGVcKGAjOHTCuDdUErhWNgBabLSUVFQsWBNWA2qoX2hA9VU4AGFKXyx0AFk3H3TIxOwCOAB5dIArLHwgpHcoSm84MGJJmFbgdG74ZcsDVkjC2Y01f7yFQsdjvLAEACM-EwVBg-naWD2AB4ABLlNb5GpgZCsACiO083jEgn6kQAhMJ6HMQfpKJCFpE2IkBNg8HCEci0RisTj8VhCTBiaSKVSVIoAaoLnBQuFgFFYvFEikBpkujkMps4FgAB7VfCdLmY7F4gleOFwAByEHg7U63VYfXVg2Go1MhhG0ygf3mAHVUtF6jgYLtwUdTvguta4Bstjs9mGznCpVcbvB7u7YM90B8vj9vYgLkDqWxaeCAEzQ1n4eHDTnoo2801EknqykyObii5SmpnNifA5GMZmCzWOwOJwudwC3xjKUyiLROKRBLJf3NLJO9KanV64xj0koVifQ08k38s1Sv0DJZBxIx5DbRGhk6J5Nua5mu4PEZPOAvSNgsgnxsHmXZzIgRZyDSYIEAAzJWsI1k+BCovWp58gKcAAD5qmkQqtqKHbyCexoYRecw7IQugcAs76ptCdIQv4KZmoRcjyMRaGkU28A4aSKiUXAwwgpYtEfrcAh0mWzF0ax7bsZx3Lceetx8eqAlYPAMAABa6KJskSXAdKwTJ4kwGxCjyKy-bfK05SrDA8mWVagHAbZeScOY0CjqUE6uOgqDaRAOSfKqOYgb8KiMaZ9GSeCEIMkyMVyUwRHWYc7nSvAgUQEk6AjMQXpReWyWGdFLHeBZHEuTCQEZT8xVwaV8BxZCzUWZQMDvuMghBHASJVnCWhTLYApiH1chIqgxpGeCfCSIxAC+Yj3o+8YvvgSLyNNOLjeBGhTTNdLzVJy3reGMBbTtrB7RoB3XbNBAneCsHLatcbPhdV3GrdB1WYhw3IKNZq-W2DCLYRO7QPAljgsgORcDwVJAA)
- [Exemplo de Stefan Baumgartner](https://fettblog.eu/typescript-react/hooks/#useref) - [Playground](https://www.typescriptlang.org/play/?jsx=2#code/JYWwDg9gTgLgBAJQKYEMDG8BmUIjgIilQ3wFgAoCzAVwDsNgJa4AVJADxgElaxqYA6sBgALAGIQ01AM4AhfjCYAKAJRwA3hThwA9DrjBaw4CgA2waUjgB3YSLi1qp0wBo4AI35wYSZ6wCeYEgAymhQwGDw1lYoRHCmEBAA1oYA5nCY0HAozAASLACyADI8fDAAoqZIIEi0MFpwaEzS8IZllXAAvIjEMAB0MkjImAA8+cWl-JXVtTAAfEqOzioA3A1NtC1wTPIwirQAwuZoSV1wql1zGg3aenAt4RgOTqaNIkgn0g5ISAAmcDJvBA3h9TsBMAZeFNXjl-lIoEQ6nAOBZ+jddPpPPAmGgrPDEfAUS1pG5hAYvhAITBAlZxiUoRUqjU6m5RIDhOi7iIUF9RFYaqIIP9MlJpABCOCAUHJ0eDzm1oXAAGSKyHtUx9fGzNSacjaPWq6Ea6gI2Z9EUyVRrXV6gC+DRtVu0RBgxuYSnRIzm6O06h0ACpIdlfr9jExSQyOkxTP5GjkPFZBv9bKIDYSmbNpH04ABNFD+CV+nR2636kby+BETCddTlyo27w0zr4HycfC6L0lvUjLH7baHY5Jas7BRMI7AE42uYSUXed6pkY6HtMDulnQruCrCg2oA)