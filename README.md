# angular-input-masks [![Build Status](https://travis-ci.org/assisrafael/angular-input-masks.svg?branch=master)](https://travis-ci.org/assisrafael/angular-input-masks) [![Coverage Status](https://coveralls.io/repos/assisrafael/angular-input-masks/badge.svg?branch=master)](https://coveralls.io/r/assisrafael/angular-input-masks?branch=master) [![Standard Version](https://img.shields.io/badge/release-standard%20version-brightgreen.svg)](https://github.com/conventional-changelog/standard-version)

[![NPM](https://nodei.co/npm/angular-input-masks.png?downloads=true&downloadRank=true&stars=true)](https://nodei.co/npm/angular-input-masks/)

[![Join the chat at https://gitter.im/assisrafael/angular-input-masks](https://badges.gitter.im/Join%20Chat.svg)](https://gitter.im/assisrafael/angular-input-masks?utm_source=badge&utm_medium=badge&utm_campaign=pr-badge&utm_content=badge) [![Bountysource](https://www.bountysource.com/badge/team?team_id=60791&style=bounties_posted)](https://www.bountysource.com/teams/angular-input-masks/bounties?utm_source=angular-input-masks&utm_medium=shield&utm_campaign=bounties_posted)

Máscaras de entrada angular com opinião. Fornece pronto para usar máscaras com pouco (br / inscricao-estadual) sem configuração (number, cnpj, etc).

### Compatibilidade

- angular-input-masks@~2: angular@^1.3 (however is only tested with 1.3) and [ECMAScript 5 compliant browsers](http://kangax.github.io/compat-table/es5/) (however CI only tests chrome and firefox).
- angular-input-masks@~1: angular@~1.2


## Instalação

Com Bower:

```
bower install --save angular-input-masks
```

Com npm:

```
npm install --save angular-input-masks
```

## Configuração

### Com bower ou npm (sem navegador):

1. Importar o ```angular-input-masks-standalone.min.js``` script na sua página. Por exemplo:

```
<script src="angular-input-masks-standalone.min.js"></script>
```

Obs: para npm os scripts de construção estão disponíveis dentro ```releases``` pasta.

2. Inclua o nome do módulo ```ui.utils.masks``` no seu aplicativo angular. Por exemplo:

```
angular.module('app', ['ui.utils.masks']);
```

### Com npm e browserify:

```
angular.module('demo', [require('angular-input-masks')]);
```

## Internacionalização

Algumas máscaras são internacionalizadas, portanto, é necessário incluir o local de funcionamento correto em seu aplicativo (consulte: https://docs.angularjs.org/guide/i18n).

## Como usar

### ui-number-mask ###

 - Exemplo:

```html
<input type="text" name="field" ng-model="number" ui-number-mask>
```

- Defina o número de decimais (o padrão é 2):

```html
<input type="text" name="field" ng-model="number" ui-number-mask="3">
```

- Permitir números negativos usando o ```ui-negative-number``` atributo:

```html
<input type="text" name="field" ng-model="number" ui-number-mask="4" ui-negative-number>
```

- Suporte ao ```min```, ```max``` e ```ui-hide-group-sep``` atributos.

```html
<input type="text" name="field" ng-model="number" ui-number-mask min="10.1" max="100.9">
```

```html
<!- Use o atributo 'ui-hide-group-sep' se você não quiser mostrar os separadores de milhares ->
<input type="text" name="field" ng-model="number" ui-number-mask ui-hide-group-sep>
```

- Internacionalizado: Usou o separador decimal e o separador de milhares definidos na configuração do navegador do cliente.

### ui-percentage-mask ###

 - Exemplo:

```html
<input type="text" name="field" ng-model="percentage" ui-percentage-mask>
```

- Você pode definir o número de decimais (o padrão é 2):

```html
<input type="text" name="field" ng-model="percentage" ui-percentage-mask="4">
```

- O $modelValue é o $viewValue / 100, portanto $viewValue - 100% = $modelValue - 1

- Você pode usar o mesmo valor em $modelValue e $viewValue usando ```ui-percentage-value```:

```html
<input type="text" name="field" ng-model="percentage" ui-percentage-mask ui-percentage-value>
```

- Support to the ```min```, ```max``` and ```ui-hide-group-sep``` attributes.

- Internacionalizado: Usou o separador decimal e o separador de milhares definidos na configuração do navegador do cliente.

- O $modelValue é o $viewValue / 100, portanto $viewValue - 100% = $modelValue - 1

- Você pode adicionar ```ui-hide-space``` atributo para esconder o espaço entre [NUMBER] e %

### ui-money-mask ###

 - Exemplo:

```html
<input type="text" name="field" ng-model="money" ui-money-mask>
```

- Defina o número de decimais (o padrão é 2):

```html
<input type="text" name="field" ng-model="money" ui-money-mask="3">
```

- Suporte aos atributos ```min```,``` max``` e ```ui-hide-group-sep```.

- Internacionalizado: Usou o símbolo da moeda, o separador decimal e o separador de milhares definidos na configuração do navegador do cliente.

- Você pode adicionar o atributo `` `ui-hide-space``` para ocultar o espaço entre [Símbolo de moeda] e [NÚMERO]

### ui-br-phone-number ###
```html
<input type="text" name="field" ng-model="phoneNumber" ui-br-phone-number>
```

### ui-br-cep-mask ###
```html
<input type="text" name="field" ng-model="cep" ui-br-cep-mask>
```

### ui-br-cpf-mask ###

 - Exemplo:

```html
<input type="text" name="field" ng-model="initializedCpf" ui-br-cpf-mask>
```

### ui-br-cnpj-mask ###

 - Exemplo:

```html
<input type="text" name="field" ng-model="initializedCnpj" ui-br-cnpj-mask>
```

### ui-br-cpfcnpj-mask ###

 - Exemplo:

```html
<input type="text" name="field" ng-model="initializedCpfCnpj1" ui-br-cpfcnpj-mask>
```

### ui-br-ie-mask ###
```html
<select ng-init="ufs=['AC','AL','AM','TO']" ng-model="selectedUF" ng-options="uf for uf in ufs"></select>
<input type="text" name="field19" ng-model="ieField" ui-br-ie-mask='selectedUF'>
```
- Suporta máscaras para todos os 27 estados brasileiros.

- Validações de acordo com a especificação [Sintegra](http://www.sintegra.gov.br/insc_est.html).

### ui-time-mask ###
-Exemplo:

```html
<input type="text" name="field" ng-model="initializeTime" ui-time-mask>
```
- Suporte para os atributos ```short```.
```html
<input type="text" name="field" ng-model="initializeTime" ui-time-mask="short">
```

### ui-date-mask ###
-Exemplo:

```html
<input type="text" name="field" ng-model="birthDate" ui-date-mask>
```
- Suporte para as máscaras de data personalizadas (consulte os formatos de data do moment.js).
```html
<input type="text" name="field" ng-model="birthDate" ui-date-mask="DD-MM-YYYY">
```
- Suporte para o atributo `` `parse```. Quando o atributo é definido como ```false```, o valor introduzido será passado para o modelo como uma string. O valor padrão do atributo é ```true```. 
```html
<input type="text" name="field" ng-model="birthDate" ui-date-mask parse="false">
```
### Mais exemplos ###

- Veja mais usos Exemplos na [página Demo](http://assisrafael.github.io/angular-input-masks/)_


### Máscaras sem documentação (ajuda desejada!)

- ui-nfe-access-key-mask
- ui-time-mask
- ui-date-mask
- ui-br-boleto-bancario-mask
- ui-br-car-plate-mask
- ui-scientific-notation-mask
- ui-us-phone-number

## Outras opções de construção


Se você estiver usando o bower ou npm (sem navegador):

- angular-input-masks-dependencies.js: fornece todas as dependências externas (string-mask, br-validações, momentjs)
- angular-input-masks-br.js: fornece apenas diretivas globais e BR, e não inclui dependências externas (string-mask, br-validações, momentjs)
- angular-input-masks-us.js: fornece apenas diretivas globais e norte-americanas e não inclui dependências externas (string-mask, br-validações, momentjs)
- angular-input-masks.js: fornece todas as diretivas e não inclui dependências externas (string-mask, br-validações, momentjs)

Se você estiver usando o npm com o browserify:

- ```require('angular-input-masks')```: fornece todas as diretivas
- ```require('angular-input-masks/br')```: apenas diretivas globais e BR
- ```require('angular-input-masks/us')```: apenas diretivas globais e norte-americanas

## Filtros
Procurando por filtros relacionados? Dê uma olhada em [angular-br-filters], https://github.com/the-darc/angular-br-filters

## Construir

```
npm install
gulp build
```

### Testes

 - Unit:
 - Usos [Karma](http://karma-runner.github.io) + [Jasmine](http://jasmine.github.io/)
 - Arquivos: `src/**/*.test.js`

```
npm run test:unit
```

 - e2e:
 - Usos [Protractor](https://github.com/angular/protractor) + Jasmine
 - Arquivos: `src/**/*.spec.js`


```
npm run test:e2e
```

- Para executar os dois testes:

```
npm test
```
