# Pruebas Unitarias

## Al Iniciar

Para hacer las pruebas unitarias, antes que nada, se debe instalar Jest:
```
npm install --save-dev jest
```

## Prerequisitos

Necesitas tener instalado NPM y Node

## Instalando

Descarga el repositorio de * [marketplace](http://10.230.8.194:8080/gitblit/log/marketplace)desde nuestro Git interno

## Ejecución
Para revisar la cobertura (coverage) de las pruebas generales se usa el comando:

```
npm run test
```
Y para revisar una prueba individual:

```
npm run test_watch
```

### Archivo package.json

Ahora tu archivo ```package.json``` debería tener incluidas las siguientes líneas:

```javascript

{
  "name": "MarketPlace",
  "version": "1.0.0",
  "description": "Environment to develop marketplace web.",
  "main": "index.js",
  "scripts": {
    "test": "jest --no-cache ",
    "test_watch": "jest --no-cache --watchAll --coverage false",
    "dev": "NODE_ENV=development webpack-dev-server",
    "prod": "npm run clean && NODE_ENV=production webpack -p",
    "clean": "rimraf ./dist/css/* ./dist/js/* ./dist/fonts/* ./dist/marketplace.html "
  },
  "keywords": [
    "jquery",
    "bootstrap",
    "webpack"
  ],
  "author": "Alejandro Rodriguez Vazquez",
  "license": "ISC",
  "devDependencies": {
    "babel": "^6.23.0",
    "babel-core": "^6.24.1",
    "babel-jest": "^20.0.3",
    "babel-loader": "^7.0.0",
    "babel-preset-es2015": "^6.24.1",
    "babel-preset-react": "^6.24.1",
    "bootstrap-loader": "^2.1.0",
    "bootstrap-sass": "^3.3.7",
    "css-loader": "^0.28.1",
    "cssom": "^0.3.2",
    "enzyme": "^2.8.2",
    "eslint": "^3.19.0",
    "eslint-config-airbnb": "^14.1.0",
    "eslint-plugin-import": "^2.2.0",
    "eslint-plugin-jest": "^20.0.3",
    "eslint-plugin-jsx-a11y": "^5.0.1",
    "eslint-plugin-react": "^7.0.0",
    "extract-text-webpack-plugin": "^2.1.0",
    "file-loader": "^0.11.1",
    "history": "^4.6.1",
    "html-webpack-plugin": "^2.28.0",
    "image-webpack-loader": "^3.3.0",
    "imports-loader": "^0.7.1",
    "jest": "^20.0.4",
    "jest-cli": "^20.0.4",
    "jest-resolve": "^20.0.4",
    "jest-resolve-dependencies": "^20.0.3",
    "jquery": "^1.8.2",
    "jquery-router-plugin": "^1.0.0",
    "jsdom": "^9.12.0",
    "node-sass": "^4.5.2",
    "prop-types": "^15.5.10",
    "react": "^15.5.4",
    "react-addons-test-utils": "^15.5.1",
    "react-dom": "^15.5.4",
    "react-router": "^3.0.0",
    "react-router-dom": "^4.1.1",
    "react-test-renderer": "^15.5.4",
    "request": "^2.81.0",
    "resolve-url-loader": "^2.0.2",
    "rimraf": "^2.6.1",
    "sass-loader": "^6.0.3",
    "style-loader": "^0.17.0",
    "url-loader": "^0.5.8",
    "webpack": "^2.4.1",
    "webpack-babel-jest": "^1.0.4",
    "webpack-dev-server": "^2.4.5",
    "webpack-war-archiver-plugin": "0.0.1"
  },
  "eslintConfig": {
    "env": {
      "browser": true
    }
  },
  "jest": {
    "verbose": true,
    "setupFiles": [
      "<rootDir>/__test__/setup.js"
    ],
    "moduleNameMapper": {
      "^.+\\.(css|scss)$": "<rootDir>/__mocks__/sass.js"
    },
    "bail": true,
    "browser": true,
    "collectCoverage": true,
    "collectCoverageFrom": [
      "**/*.{js,jsx}",
      "!**/node_modules/**",
      "!**/dist/**"
    ],
    "coverageDirectory": "./__test__/report/",
    "coveragePathIgnorePatterns": [
      "/node_modules/",
      "/dist/",
      "/__test__/",
      "/src/app-routes.js",
      "/src/app.js",
      "webpack.bootstrap.config.js",
      "webpack.config.js",
      "index.js",
      "./.eslintrc.js"
    ],
    "coverageThreshold": {
      "global": {
        "branches": 80,
        "functions": 80
      }
    }
  }
}


```

### Archivos

 * _mocks_ : En esta carpeta se colocan los archivos auxiliares para correr las pruebas
