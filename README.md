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

### Tabela de conteúdo da Cheatsheet básica

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

# Seção 1: Configuração

## Pré-requisitos

1. Uma boa compreensão de [React](https://reactjs.org).
2. Familiaridade com os tipos básicos de [TypeScript](https://www.typescriptlang.org/docs/handbook/basic-types.html) ( [O guia de 2ality](http://2ality.com/2018/04/type-notation-typescript.html) é de grande ajuda. Se você é completamente novato em TypeScript, dê uma olhada no [tutorial de chibicode](https://ts.chibicode.com/todo/) ).
3. Ter lido [a seção de TypeScript na documentação oficial do React](https://reactjs.org/docs/static-type-checking.html#typescript).
4. Ter lido [a seção do React do novo playground de TypeScript](http://www.typescriptlang.org/play/index.html?jsx=2&esModuleInterop=true&e=181#example/typescript-with-react) ( Opcional: também acompanhar os mais de 40 exemplos na seção de exemplos do [playground](http://www.typescriptlang.org/play/index.html) ).

Este guia sempre assumirá que você está usando a última versão de Typescript. Notas para versões mais antigas usarão a etiqueta `<details>`.

## Ferramentas iniciais de React + TypeScript

1. [Create React App v2.1+ com Typescript](https://facebook.github.io/create-react-app/docs/adding-typescript): `npx create-react-app my-app --template typescript`

- Costumávamos recomendar `create-react-app-typescript` mas agora o seu uso é [desencorajado](https://www.reddit.com/r/reactjs/comments/a5919a/createreactapptypescript_has_been_archived_rip/). [Consulte as instruções de migração](https://vincenttunru.com/migrate-create-react-app-typescript-to-create-react-app/).

2. [O guia de Basarat](https://github.com/basarat/typescript-react/tree/master/01%20bootstrap) para uma **configuração manual** de React + TypeScript + Webpack + Babel.

- Em particular, certifique-se de ter instalado `@types/react` e `@types/react-dom` .( [Leia mais sobre o projeto DefinitelyTyped caso você não esteja familiarizado](https://definitelytyped.org/) ).
- Existem também muitos _boilerplates_ de React + Typescript. Por favor consulte [nossa lista de recursos](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet#recommended-react--typescript-codebases-to-learn-from).

## Importar React

```tsx
import * as React from 'react';
import * as ReactDOM from 'react-dom';
```

Na versões de [TypeScript superiores á 2.7](https://www.typescriptlang.org/docs/handbook/release-notes/typescript-2-7.html), você pode rodar TypeScript com `--allowSyntheticDefaultImports` (ou adicionar `"allowSyntheticDefaultImports": true` na tsconfig) para importar como se faz normalmente em jsx:

```tsx
import React from 'react';
import ReactDOM from 'react-dom';
```

<details>

<summary>Explicação</summary>

Por que usar `allowSyntheticDefaultImports` ao invés de `esModuleInterop`? [Daniel Rosenwasser](https://twitter.com/drosenwasser/status/1003097042653073408) comentou que é melhor para webpack/parcel. Para consultar mais argumentos dessa discussão <https://github.com/wmonk/create-react-app-typescript/issues/214>

Por favor, faça um _PR_ ou [abra uma _issue_](https://github.com/typescript-cheatsheets/react-typescript-cheatsheet/issues/new) com tuas sugestões.

</details>

# Seção 2: Primeiros Passos

## Componente de Função
