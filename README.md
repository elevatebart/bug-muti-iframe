# Reproduce the multi-iframe bug

This repo reproduces this issue [cypress-io/cypress#16458](https://github.com/cypress-io/cypress/issues/16458)

```sh
yarn install
DEBUG=cypress:server:browsers:electron yarn cypress run-ct
```

See the console log:

```log

cypress:server:browsers:electron console message: { column: 9, level: 'log', line: 65, source: 'console-api', text: 'http://localhost:60562/__cypress/iframes//Users/bart/Documents/exp/bug-muti-iframe/src/test1.spec.js', url: 'http://localhost:60562/__cypress/src/static/js/0.chunk.js' } +96ms

...

cypress:server:browsers:electron console message: { column: 9, level: 'log', line: 65, source: 'console-api', text: 'http://localhost:60562/__cypress/iframes//Users/bart/Documents/exp/bug-muti-iframe/src/test1.spec.js', url: 'http://localhost:60562/__cypress/src/static/js/0.chunk.js' } +2s
cypress:server:browsers:electron console message: { column: 9, level: 'log', line: 65, source: 'console-api', text: 'http://localhost:60562/__cypress/iframes//Users/bart/Documents/exp/bug-muti-iframe/src/test2.spec.js', url: 'http://localhost:60562/__cypress/src/static/js/0.chunk.js' } +24ms

...

cypress:server:browsers:electron console message: { column: 9, level: 'log', line: 65, source: 'console-api', text: 'http://localhost:60562/__cypress/iframes//Users/bart/Documents/exp/bug-muti-iframe/src/test1.spec.js', url: 'http://localhost:60562/__cypress/src/static/js/0.chunk.js' } +2s
cypress:server:browsers:electron console message: { column: 9, level: 'log', line: 65, source: 'console-api', text: 'http://localhost:60562/__cypress/iframes//Users/bart/Documents/exp/bug-muti-iframe/src/test2.spec.js', url: 'http://localhost:60562/__cypress/src/static/js/0.chunk.js' } +0ms
cypress:server:browsers:electron console message: { column: 9, level: 'log', line: 65, source: 'console-api', text: 'http://localhost:60562/__cypress/iframes//Users/bart/Documents/exp/bug-muti-iframe/src/test3.spec.js', url: 'http://localhost:60562/__cypress/src/static/js/0.chunk.js' } +23ms

...
```
