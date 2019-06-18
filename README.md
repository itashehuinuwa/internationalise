# Internationalise

This project was generated with [Angular CLI](https://github.com/angular/angular-cli) version 7.2.3.

## About

This project is easy understand project on house internationalise and localise an Angular Project. The instruction are thus:

## Instructions

* Add the `i18n` at and the `@@PLACEHOLDER` to the tag for the text you wish to change. e.g.

```html
    <legend i18n="@@customHeading">CUSTOMISATION</legend>
```

* Once that is done, run `ng xI18n` to generate a file `messages.xlf` in the `src` folder. I created `src/locale` and moved `messages.xlf` to it.

* Duplicate `src/locale/messages.xlf` and name it `src/locale/messages.es.xlf` . In this `es` is the language you wish to translate to. `es` is **spanish**.

* Under the `source` tag a translate tag and the current translation you wish to make. e.g

```xml
    <source>Internationalisation for Spanish Speakers testing</source>
    <target>Internacionalización para pruebas de hispanohablantes.</target>
```

* Do it for all the the source tag, you added an `i18n` identifier to.

* In `angular.json` make changes to the configuration file.

    * Firstly to under `projects > architect > build > configurations`, duplicate the `production` object and rename it to `production-es` and add the following lines:

    ```json
        "production-es": {
            //-- shortened for brevity
            "baseHref": "/es/",
            "i18nFile": "src/locale/messages.es.xlf",
            "i18nFormat": "xlf",
            "i18nLocale": "es",
            "i18nMissingTranslation": "error",
            "outputPath": "dist/browser/es/"
        }
    ```

    * Then make changes to the `projects > architect > serve > configurations` object

    ```json
        "es": {
            "browserTarget": "internationalise:build:production-es"
        }
    ```

* Finally to see your changes run `ng serve --configuration=es`

The full tutorial is: [angular-internationalization](https://angular-templates.io/tutorials/about/angular-internationalization-i18n-multi-language-app)

## Development server

Run `ng serve` for a dev server. Navigate to `http://localhost:4200/`. The app will automatically reload if you change any of the source files.

## Code scaffolding

Run `ng generate component component-name` to generate a new component. You can also use `ng generate directive|pipe|service|class|guard|interface|enum|module`.

## Build

Run `ng build` to build the project. The build artifacts will be stored in the `dist/` directory. Use the `--prod` flag for a production build.

## Running unit tests

Run `ng test` to execute the unit tests via [Karma](https://karma-runner.github.io).

## Running end-to-end tests

Run `ng e2e` to execute the end-to-end tests via [Protractor](http://www.protractortest.org/).

## Further help

To get more help on the Angular CLI use `ng help` or go check out the [Angular CLI README](https://github.com/angular/angular-cli/blob/master/README.md).
