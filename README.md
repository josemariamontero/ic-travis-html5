# Integración continúa: Comprobación de html5 válido y Despliegue en surge.sh 

[![Build Status](https://travis-ci.org/josemariamontero/ic-travis-html5.svg?branch=master)](https://travis-ci.org/josemariamontero/ic-travis-html5)

name: Integration

on:
  push:
    branches:
    - master

jobs:
  build:
    runs-on: ubuntu-latest
    steps:
    - uses: actions/checkout@master
    - name: Tests Integration with Github Actions.
      uses: Cyb3r-Jak3/html5validator-action@master
      with:
        root: tests/valid/
        log_level: INFO

Integración continúa con travis que realiza dos operaciones:

* test: Comprueba que el html5 es válido. Para ello vamos a utilizar (https://github.com/svenkreiss/html5validator)
* deploy: Si la prueba ha sido exitosa se sube al servicio surge.sh (http://surge.sh/)


