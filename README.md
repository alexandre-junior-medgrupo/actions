<p align="center">
  <img src=".github/assets/templarios.svg?raw=true" alt="Templarios Design System logo" width="150" height="150">
</p>

<p align="center">
  <b>Templarios Design System</b>
  <br>
  <a href="http://desenv.ordomederi.com/templarios/"><strong>Website</strong></a>
  <br>
  <a href="http://desenv.ordomederi.com/templarios-7/"><strong>Storybook Release 7</strong></a> |
  <a href="http://desenv.ordomederi.com/templarios-6/"><strong>Storybook Release 6</strong></a>
  <br>
  <br>
</p>

<p align="center">
  <a href="https://github.com/alexbjr369/test-2/blob/main/LICENSE">
    <img src="https://img.shields.io/badge/license-MIT-blue.svg" alt="Hive UI Framework is released under the MIT license." />
  </a>
  <a href="http://commitizen.github.io/cz-cli/">
    <img src="https://img.shields.io/badge/commitizen-friendly-brightgreen.svg" alt="Commitizen friendly" />
  </a>
</p>

# Table of contents

- [Applications usage](#templarios-usage)
- [Monorepo usage](#monorepo-usage)
- [Templarios usage](#templarios-usage)

# Applications usage

> Aplicações onde **Templarios Release 7** está sendo utilizado:

- **[`Inscrições Cardapio`](https://github.com/MEDGRUPOGIT/site-inscricoes-cardapio)**

> Aplicações onde **Templarios Release 6** está sendo utilizado:

# Monorepo usage

## Templarios

```bash
# ionic 7
npm run start:7

# ionic 6
npm run start:6
```

## Templarios website

```bash
# development
npm run website:start

# production
npm run website:build
```

## Processos website

```bash
# development
npm run processos:start

# production
npm run processos:build
```

# Templarios usage

<details>
<summary><h2 style="display:inline-block; width: calc(100% - 15px)">Angular</h2></summary>

### || Installation

```bash
npm i templarios@github:MEDGRUPOGIT/templarios.git#1.0.0
```

#### || Release 7

```bash
npm install @ionic/core@latest @ionic/angular@latest
```

#### || Release 6

```bash
npm install @ionic/core@v6-lts @ionic/angular@v6-lts
```

### || Configuration

```ts
// src/main.ts

import { defineCustomElements } from 'templarios/release-{7,6}/core/loader';
defineCustomElements();
```

```scss
// src/styles.scss

/* ionic */
@import '@ionic/angular/css/core.css';
@import '@ionic/angular/css/normalize.css';
@import '@ionic/angular/css/structure.css';
@import '@ionic/angular/css/typography.css';
@import '@ionic/angular/css/display.css';
@import '@ionic/angular/css/padding.css';
@import '@ionic/angular/css/float-elements.css';
@import '@ionic/angular/css/text-alignment.css';
@import '@ionic/angular/css/text-transformation.css';
@import '@ionic/angular/css/flex-utils.css';

/* templarios */
@import 'templarios/release-{7,6}/angular/styles/css/templarios.css';
```

```ts
// src/app/app.module.ts

import { CUSTOM_ELEMENTS_SCHEMA } from '@angular/core';
import { TemplariosModule } from 'templarios/release-{7,6}/angular';
import { RouteReuseStrategy } from '@angular/router';
import { IonicModule, IonicRouteStrategy } from '@ionic/angular';

@NgModule({
  schemas: [CUSTOM_ELEMENTS_SCHEMA],
  imports: [IonicModule.forRoot(), TemplariosModule],
  providers: [{ provide: RouteReuseStrategy, useClass: IonicRouteStrategy }],
})
export class AppModule {}
```

```json
// tsconfig.json

{
  "compilerOptions": {
    "types": [
      "./node_modules/templarios/release-{7,6}/core/dist/types/interfaces.d.ts"
    ]
  }
}
```

```json
// angular.json

{
  "projects": {
    "app-angular": {
      "architect": {
        "build": {
          "options": {
            "assets": [
              {
                "glob": "**/*.svg",
                "input": "node_modules/templarios/release-{7,6}/angular/assets",
                "output": "./assets"
              }
            ],
            "stylePreprocessorOptions": {
              "includePaths": ["node_modules"]
            }
          }
        },
        "test": {
          "options": {
            "assets": [
              {
                "glob": "**/*.svg",
                "input": "node_modules/templarios/release-{7,6}/angular/assets",
                "output": "./assets"
              }
            ]
          }
        }
      }
    }
  }
}
```

</details>

<details>
<summary><h2 style="display:inline-block; width: calc(100% - 15px)">Ionic Angular</h2></summary>

### || Installation

```bash
npm i templarios@github:MEDGRUPOGIT/templarios.git#1.0.0
```

#### || Release 7

```bash
npm uninstall @ionic/core @ionic/angular
```

```bash
npm install @ionic/core@latest @ionic/angular@latest
```

#### || Release 6

```bash
npm uninstall @ionic/core @ionic/angular
```

```bash
npm install @ionic/core@v6-lts @ionic/angular@v6-lts
```

### || Configuration

```ts
// src/main.ts

import { defineCustomElements } from 'templarios/release-{7,6}/core/loader';
defineCustomElements();
```

```scss
// src/global.scss

/* templarios */
@import 'templarios/release-{7,6}/angular/styles/css/templarios.css';
```

```ts
// src/app/app.module.ts

import { CUSTOM_ELEMENTS_SCHEMA } from '@angular/core';
import { TemplariosModule } from 'templarios/release-{7,6}/angular';

@NgModule({
  schemas: [CUSTOM_ELEMENTS_SCHEMA],
  imports: [TemplariosModule],
})
export class AppModule {}
```

```json
// tsconfig.json

{
  "compilerOptions": {
    "types": [
      "./node_modules/templarios/release-{7,6}/core/dist/types/interfaces.d.ts"
    ]
  }
}
```

```json
// angular.json

{
  "projects": {
    "app-angular": {
      "architect": {
        "build": {
          "options": {
            "assets": [
              {
                "glob": "**/*.svg",
                "input": "node_modules/templarios/release-{7,6}/angular/assets",
                "output": "./assets"
              }
            ],
            "stylePreprocessorOptions": {
              "includePaths": ["node_modules"]
            }
          }
        },
        "test": {
          "options": {
            "assets": [
              {
                "glob": "**/*.svg",
                "input": "node_modules/templarios/release-{7,6}/angular/assets",
                "output": "./assets"
              }
            ]
          }
        }
      }
    }
  }
}
```

</details>

</details>
