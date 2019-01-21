# Guia de Estilos Vue/Quasar

> Guia feito para padronizar e aplicar boas práticas nos projetos em Vue/Quasar da Legal Labs.
> Guia feito para padronizar e aplicar boas práticas nos projetos em Vue/Quasar da Legal Labs.
> Guia feito para padronizar e aplicar boas práticas nos projetos em Vue/Quasar da Legal Labs.

## Nomenclatura
___

### Nome de componentes

Com exceção de um componente raiz presente no diretório `pages`, o nome dos componentes deve ser escritos com, no mínimo, duas palavras, para ser mais descritivo. O Vue em sua documentação recomenda a utilização das práticas __PascalCase__ ou __kebab-case__, mas para padronização dos projetos Legal Labs, será utilizado o padrão __PascalCase__.


#### Exemplos Ruins
```javascript
// components/login.vue
export default {
  name: 'login' // Nome com apenas uma palavra
}
```
```javascript
// components/loginCard.vue
export default {
  name: 'login-card' // Nome do componente fora do padrão PascalCase
}
```

#### Exemplo Bom

```javascript
// components/LoginCard.vue
export default {
  name: 'LoginCard'
}
```

Referência: [Multi-word component names - Vue.js](https://vuejs.org/v2/style-guide/#Multi-word-component-names-essential)

### Nome de componentes relacionados

Componentes que são altamente acoplados, como por exemplo filhos de um componente base, devem ter sua relação explicita em seu nome. Como convenção de boa prática do Vue, apenas deve-se criar pastas para organizar os componentes em aplicações grandes (à partir de 100 componentes). Visto isso, a maneira correta de organizar os componentes é utilizar nomes auto-explicativos e relacionados com o componente pai.

#### Exemplo Ruim
```
components/
|- Register/
   |- content/
      |- labels.vue
      |- buttons.vue
```

#### Exemplo Bom
```
components/
|- Register.vue
|- RegisterContent.vue
|- RegisterContentLabels.vue
|- RegisterContentButtons.vue
```

Referência: [Tightly coupled component names - Vue.js](https://vuejs.org/v2/style-guide/#Tightly-coupled-component-names-strongly-recommended)

### Nome de pastas

Como dito anteriormente, o Vue recomenda que apenas utilize pastas em aplicações grandes, pois, com a nomenclatura auto explicativa dos componentes, elas não são se fazem necessárias. Apesar disso, os projetos da Legal Labs culturamente costumam ter pastas para organizar os components, e para nomeá-las, deve-se utilizar o padrão __kebab-case__. Além disso, o nome da pasta deve ter o mesmo nome do componente raiz presente no diretório `pages`. Por exemplo, o componente `pages/ProcessPage.vue` deve ter sua pasta correspondente e de mesmo nome `components/process-page/`.

#### Exemplo Ruim
```
components/
|- ProcessPage/
  |- ProcessContent.vue
  |- ProcessFields.vue
|- ResultPage/
  |- Pagination.vue
  |- ProcessDetail.vue
  |- Results.vue
```

#### Exemplo Bom
```
components/
|- process-page/
  |- ProcessPageContent.vue
  |- ProcessPageFields.vue
|- result-page/
  |- ResultPagePagination.vue
  |- ResultPageProcessDetail.vue
  |- ResultPageList.vue
```

Vale ressaltar que em projetos novos a adoção ou não de pastas para os componentes deve ser um consenso entre a equipe. Caso esteja desenvolvendo em um projeto já em andamento, deve-se seguir o padrão já estipulado no mesmo.

<!-- Referência: []() -->

### Case no nome dos componentes (DOM)

Diferente do nome do componente (que deve ser escrito em PascalCase), ao ser escrito em templates DOM, o case usado deve ser o __kebab-case__. Por exemplo, a tag `<ProcessPage>` visualmente é mais distinta que a tag `process-page`, relacionado ao padrão do HTML, e, ao usar o kebab-case, este padrão visual é mantido.

#### Exemplo Ruim
```html
<template lang="pug">
  div.process-page
    ProcessContent.process-page__content
</template>
```

#### Exemplo Bom
```html
<template lang="pug">
  div.process-page
    process-content.process-page__content
</template>
```
Referência: [Component name casing in templates - Vue.js](https://vuejs.org/v2/style-guide/#Component-name-casing-in-templates-strongly-recommended)

<!-- ### 1.4) Padrão BEM para CSS

O padrão de nomenclatura BEM (block, element, modifier) tem o objetivo de  -->