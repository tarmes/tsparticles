[![banner](https://cdn.matteobruni.it/images/particles/banner2.png)](https://particles.matteobruni.it)

# tsParticles - Partículas TypeScript

**Uma biblioteca TypeScript leve para criação de partículas. Livre de dependências (\*) e pronto para o navegador!**

_[Particles.js](https://github.com/VincentGarreau/particles.js) convertida em TypeScript, livre de dependências (\*), melhorada com novas features legais 😎 e correção de vários bugs e **é ativamente mantida**!_

[![jsDelivr](https://data.jsdelivr.com/v1/package/npm/tsparticles/badge?style=rounded)](https://www.jsdelivr.com/package/npm/tsparticles) [![Cdnjs](https://img.shields.io/cdnjs/v/tsparticles)](https://cdnjs.com/libraries/tsparticles) [![npmjs](https://badge.fury.io/js/tsparticles.svg)](https://www.npmjs.com/package/tsparticles) [![npm](https://img.shields.io/npm/dm/tsparticles)](https://www.npmjs.com/package/tsparticles) [![lerna](https://img.shields.io/badge/maintained%20with-lerna-cc00ff.svg)](https://lerna.js.org/) [![CodeFactor](https://www.codefactor.io/repository/github/matteobruni/tsparticles/badge)](https://www.codefactor.io/repository/github/matteobruni/tsparticles) [![Codacy Badge](https://api.codacy.com/project/badge/Grade/b983aaf3461a4c48b1e2eecce1ff1d74)](https://www.codacy.com/manual/ar3s/tsparticles?utm_source=github.com&utm_medium=referral&utm_content=matteobruni/tsparticles&utm_campaign=Badge_Grade) [![Gitpod Ready-to-Code](https://img.shields.io/badge/Gitpod-ready--to--code-blue?logo=gitpod)](https://gitpod.io/#https://github.com/matteobruni/tsparticles)

## Você quer usá-la no seu website?

**Essa biblioteca está disponível em dois dos CDNs mais populares e é fácil e está pronta para usar, se você estava usando particle.js é ainda mais fácil**.

Você encontrará as instruções [abaixo](https://github.com/matteobruni/tsparticles/blob/master/README.md#library-installation), com todos os links que você precisa, e _não se assuste com o **TypeScript**, é apenas a linguagem base_.

**Os output files são apenas JavaScript**. 🤩

CDNs e `npm` tem todas as fontes que você precisa em **Javascript**, um bundle browser pronto (tsparticles.min.js) e todos os arquivos divididos pela sintaxe `import`.

**Se você ainda está interessado** algumas linhas abaixo tem algumas instruções para a migrar da antiga biblioteca particles.js

## **_Instalação da Biblioteca_**

### **_Hosting / CDN_**

**_Por favor use esse hosts ou o seu próprio para carregar tsParticles nos seus projetos_**

#### jsDelivr

[![jsDelivr](https://data.jsdelivr.com/v1/package/npm/tsparticles/badge)](https://www.jsdelivr.com/package/npm/tsparticles)

#### cdnjs

[![Cdnjs](https://img.shields.io/cdnjs/v/tsparticles)](https://cdnjs.com/libraries/tsparticles)

#### unpkg

<https://unpkg.com/tsparticles/>

---

### **_npm_**

[![npmjs](https://badge.fury.io/js/tsparticles.svg)](https://www.npmjs.com/package/tsparticles) [![npmjs](https://img.shields.io/npm/dt/tsparticles)](https://www.npmjs.com/package/tsparticles)

```shell
npm install tsparticles
```

### **_yarn_**

```shell
yarn add tsparticles
```

#### Import e require

A partir da versão 1.12.11 `import` e `require` podem ser usados para importar `tsParticles` .

Agora você pode escrever algo tipo

```javascript
const tsParticles = require("tsparticles");

// or

import { tsParticles } from "tsparticles";
```

O `tsParticles` importado é a mesma instância que você tem quando está incluindo o script.

---

### **_NuGet_**

[![Nuget](https://img.shields.io/nuget/v/tsParticles)](https://www.nuget.org/packages/tsParticles/)

---

### **_Uso_**

Carregue tsParticles e configure as partículas:

[![tsParticles demo](https://media.giphy.com/media/ftHwBpp3b0qNyCXRuu/giphy.gif)](https://particles.matteobruni.it)

**index.html**

```html
<div id="tsparticles"></div>

<script src="tsparticles.min.js"></script>
```

**app.js**

```javascript
// @path-json pode ser um objeto ou um array, o primeiro vai ser carregado diretamente, o objeto do array vai ser aleatóriamente selecionado
/* tsParticles.loadJSON(@dom-id, @path-json, @callback (opcional)); */

tsParticles
  .loadJSON("tsparticles", "presets/default.json")
  .then((container) => {
    console.log("callback - tsparticles config carregada");
  })
  .catch((error) => {
    console.error(error);
  });

//ou

/* tsParticles.load(@dom-id, @options); */

tsParticles.load("tsparticles", {
  /* options aqui */
});

//ou

/* tsParticles.loadFromArray(@dom-id, @options, @index (opcional)); */

tsParticles.loadFromArray("tsparticles", [
  {
    /* options aqui */
  },
  {
    /* outras options aqui */
  },
]);
//objeto aleatório

tsParticles.loadFromArray(
  "tsparticles",
  [
    {
      /* options aqui */
    },
    {
      /* outras options aqui */
    },
  ],
  1
); //o segundo
// Importante! Se o index não está em range 0...<array.length, o index vai ser ignorado.

// depois da inicialização isso pode ser usado.

/* tsParticles.setOnClickHandler(@callback); */

/* isso vai ser ativado por todas as partículas carregadas */

tsParticles.setOnClickHandler((event, particles) => {
  /* customizado no click handler */
});

// agora você pode controlar as animações também, é possível pausar e resumir as animações
// esses métodos não alteram a config então você está seguro com todas as suas configurações
// domItem(0) retorna a primeira instância tsParticles carregada no dom
const particles = tsParticles.domItem(0);

// play vai começar as animações, se o move não está habilitado ele não será, ele apenas atualiza o frame
particles.play();

// pause vai parar as animações
particles.pause();
```

---

## Componentes oficias para alguns dos frameworks mais usados

### Angular

#### `ng-particles`

[![npm](https://img.shields.io/npm/v/ng-particles)](https://www.npmjs.com/package/ng-particles) [![npm](https://img.shields.io/npm/dm/ng-particles)](https://www.npmjs.com/package/ng-particles)

Você pode encontrar as instruções [aqui](https://github.com/matteobruni/tsparticles/blob/master/components/angular/README.md)

### Inferno

#### `inferno-particles`

[![npm](https://img.shields.io/npm/v/inferno-particles)](https://www.npmjs.com/package/inferno-particles) [![npm](https://img.shields.io/npm/dm/inferno-particles)](https://www.npmjs.com/package/inferno-particles)

Você pode encontrar as instruções [aqui](https://github.com/matteobruni/tsparticles/blob/master/components/inferno/README.md)

### jQuery

#### `jquery-particles`

[![npm](https://img.shields.io/npm/v/jquery-particles)](https://www.npmjs.com/package/jquery-particles) [![npm](https://img.shields.io/npm/dm/jquery-particles)](https://www.npmjs.com/package/jquery-particles)

Você pode encontrar as instruções [aqui](https://github.com/matteobruni/tsparticles/blob/master/components/jquery/README.md)

### Preact

#### `preact-particles`

[![npm](https://img.shields.io/npm/v/preact-particles)](https://www.npmjs.com/package/preact-particles) [![npm](https://img.shields.io/npm/dm/preact-particles)](https://www.npmjs.com/package/preact-particles)

Você pode encontrar as instruções [aqui](https://github.com/matteobruni/tsparticles/blob/master/components/preact/README.md)

### ReactJS

#### `react-tsparticles`

[![npm](https://img.shields.io/npm/v/react-tsparticles)](https://www.npmjs.com/package/react-tsparticles) [![npm](https://img.shields.io/npm/dm/react-tsparticles)](https://www.npmjs.com/package/react-tsparticles)

Você pode encontrar as instruções [aqui](https://github.com/matteobruni/tsparticles/blob/master/components/react/README.md)

### Svelte

#### `svelte-particles`

[![npm](https://img.shields.io/npm/v/svelte-particles)](https://www.npmjs.com/package/svelte-particles) [![npm downloads](https://img.shields.io/npm/dm/svelte-particles)](https://www.npmjs.com/package/svelte-particles)

Você pode encontrar as instruções [aqui](https://github.com/matteobruni/tsparticles/blob/master/components/svelte/README.md)

### VueJS

#### `particles.vue`

[![npm](https://img.shields.io/npm/v/particles.vue)](https://www.npmjs.com/package/particles.vue) [![npm](https://img.shields.io/npm/dm/particles.vue)](https://www.npmjs.com/package/particles.vue)

Você pode encontrar as instruções [aqui](https://github.com/matteobruni/tsparticles/blob/master/components/vue/README.md)

---

## Templates e Resources

Você pode encontar alguns templates relacionados a tsParticles [aqui](https://github.com/tsparticles/templates). Os templates são criados para *Vanilla Javascript*, *ReactJS*, *VueJS*, *Angular*, *SvelteJS* e outros frameworks.

Os templates podem variar, novos podem ser criados ou antigos atualizados com as últimas features ou modificados para um estilo melhor. Dê uma olhada neles de vez em quando.

Se você criou um bom design com *tsParticles* sinta-se livre para enviar um pull request com seu template legal, você será creditado como autor do template!

<https://github.com/tsparticles/templates>

---

## **_Demo / Gerador_**

<https://particles.matteobruni.it/Samples>

[![Particles demo](https://particles.matteobruni.it/images/demo.png?v=1.8.1)](https://particles.matteobruni.it/Samples)

---

### Caracteres como partículas

[![Particles chars demo](https://media.giphy.com/media/JsssOXz72bM6jGEZ0s/giphy.gif)](https://particles.matteobruni.it/Samples#chars)

---

### Conexões com mouse hover

[![Particles mouse connections demo](https://media.giphy.com/media/XzvZThpVbxHxMYz5xt/giphy.gif)](https://particles.matteobruni.it/Samples#connect)

---

### Máscara poligonal

[![tsParticles Polygon Mask demo](https://media.giphy.com/media/lNRfiSgaMFbL4FMhW6/giphy.gif)](https://particles.matteobruni.it/Samples#polygonMask)

---

### Estrelas animadas

[![Particles NASA demo](https://media.giphy.com/media/cLqGsnh7FKRVMgPIWE/giphy.gif)](https://particles.matteobruni.it/Samples#nasa)

---

### Nyan cat voando em estrelas rolando

[![Particles Nyan Cat demo](https://media.giphy.com/media/LpX2oNc9ZMgIhIXQL9/giphy.gif)](https://particles.matteobruni.it/Samples#nyancat2)

---

### Partículas de neve

[![tsParticles Snow demo](https://media.giphy.com/media/gihwUFbmiubbkdzEMX/giphy.gif)](https://particles.matteobruni.it/Samples#snow)

---

### Background Mask particles
### Partículas de Máscara de Background

[![tsParticles Background Mask demo](https://media.giphy.com/media/dWraWgqInWFGWiOyRu/giphy.gif)](https://particles.matteobruni.it/Samples#background)

---

#### Partículas COVID-19 SARS-CoV-2

[![tsParticles COVID-19 demo](https://media.giphy.com/media/fsVN1ZHksgBIXNIbr1/giphy.gif)](https://particles.matteobruni.it/Samples#virus)

_Não clique! Não clique! OH NÃO ESTÁ SE ESPALHANDO!!!!_

**COVID-19 é uma doença séria. Por favor fique em casa, coloque máscara e se cuide!**

---

**particles.json**

Você pode encontrar uma sample config [aqui](https://github.com/matteobruni/tsparticles/wiki/tsParticles-Sample-Config) 📖

---

## **_Opções_**

Você pode encontrar todas as opções disponíveis [aqui](https://particles.js.org/interfaces/_options_interfaces_ioptions_.ioptions.html) 📖

## Quer ver em ação e testar?

Eu criei uma coleção do tsParticles no [CodePen](https://codepen.io/collection/DPOage) 😮 ou você pode conferir no meu [perfil](https://codepen.io/matteobruni)

De outra maneira tem o link da página da demo abaixo. Apenas clique/toque o Coronavirus abaixo, não tenha medo. **É seguro** 😷.

[![tsParticles demo](https://media.giphy.com/media/fsVN1ZHksgBIXNIbr1/giphy.gif)](https://particles.matteobruni.it/#virus)

Quer ver mais demos? Clone o repositório no seu computador e siga essas instruções

```shell
yarn install && yarn start
```

**Boom! 💥** <http://localhost:3000> e você pode conferir outras demos.

_Se você é valente o suficiente_ você pode trocar para a branch `dev` para tentar usar as features ainda em development.

## Dependências

Você deve ter repadado o \* perto de "livre de dependências". Bem quase todas features funcionam sem nenhuma dependência, mas... Bem tem um pequeno porém. A feature **Máscara Poligonal** exige `[pathseg](https://github.com/progers/pathseg)` para alguns navegadores para funcionar corretamente, e obviamente o Icon Fonts (tipo `FontAwesome` ) tem que ser incluído na sua página.

---

## Migrando do Particles.js

A biblioteca **tsParticles** é totalmente compatível com a configuração do _particles.js_.

Sério, você só precisa mudar o script source et-voilà, **você está pronto** 🧙!

Você pode ler mais **[aqui](https://dev.to/matteobruni/migrating-from-particles-js-to-tsparticles-2a6m)**

Quer saber 5 razões para fazer a troca? [Leia aqui](https://dev.to/matteobruni/5-reasons-to-use-tsparticles-and-not-particles-js-1gbe)

_Abaixo você pode encontrar toda informação que precisa para instalar tsParticles e sua nova sintaxe._

---

## Plugins/Customizações

tsParticles agora tem suporte a algumas customizações 🥳.

**Você pode criar seus próprios plugins**

_Leia mais [aqui](https://particles.js.org/modules/_core_interfaces_iplugin_.html)..._

---

### API Docs

Documentação e referências de Desenvolvimento [aqui](https://particles.matteobruni.it/docs/) 📖

---

[![Slack](https://cdn.matteobruni.it/images/slack.png)](https://join.slack.com/t/tsparticles/shared_invite/enQtOTcxNTQxNjQ4NzkxLWE2MTZhZWExMWRmOWI5MTMxNjczOGE1Yjk0MjViYjdkYTUzODM3OTc5MGQ5MjFlODc4MzE0N2Q1OWQxZDc1YzI) [![tsParticles Product Hunt](https://api.producthunt.com/widgets/embed-image/v1/featured.svg?post_id=186113&theme=light)](https://www.producthunt.com/posts/tsparticles?utm_source=badge-featured&utm_medium=badge&utm_souce=badge-tsparticles")

---

<p>  
    <a href="https://www.jetbrains.com/?from=tsParticles">  
        <img src="https://cdn.matteobruni.it/images/jetbrains-logos/jetbrains-variant-4.png" height="150" alt="JetBrains" />  
    </a>  
    <a href="https://www.jetbrains.com/webstorm/?from=tsParticles">  
        <img src="https://cdn.matteobruni.it/images/jetbrains-logos/webstorm_logos/logo.png" height="150" alt="JetBrains" />  
    </a>  
</p>

### Muito obrigado [JetBrains](https://www.jetbrains.com/?from=tsParticles) pela Licença 2020 Open Source!

[JetBrains WebStorm](https://www.jetbrains.com/webstorm/?from=tsParticles) costuma manter esse projeto.

### Muito obrigado [SauceLabs](https://saucelabs.com) pela Licença Open Source!

<img alt="Testing Powered By SauceLabs" src="https://raw.githubusercontent.com/saucelabs/saucelabs.github.io/publish/images/opensauce/powered-by-saucelabs-badge-red.svg" width="250" />