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
- [Pré-requisitos](#prerequisites)
- [Ferramentas iniciais de React + TypeScript](#react--typescript-starter-kits)
- [Importar React](#import-react)
<!--END-SECTION:setup-toc-->
- [Seção 2: Primeiros Passos](#section-2-getting-started)
  - [Componente de Função](#function-components)
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
