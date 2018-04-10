# Pull requests

Para acelerar o processo de revisão da solicitação pull, verifique se seu PR segue as dicas abaixo:
- Se for uma correção de bug, implemente pelo menos um caso de teste que exiba o comportamento errado que você está corrigindo
- Se for um novo recurso tente implementar testes que cubram pelo menos as partes mais importantes do seu código
- Verifique se a cobertura do código não está sendo reduzida
- Squash seus commits em um único commit

# Bug reporting

Por favor, inclua no seu relatório de erros as seguintes informações:
- uma breve descrição do bug no título (evite escrever títulos genéricos)
- qual versão de máscaras de entrada angular e angular foi usada
- em quais navegadores (e suas versões) o bug foi observado
- opcional: puxe o pedido com um caso de teste que reproduz o erro.

# Implementing tests

Este projeto implementa dois tipos de testes:
- testes unitários: usando [Karma] (http://karma-runner.github.io) + [Jasmine] (http://jasmine.github.io/) (Arquivos: src / ** / *. test.js )
- testes e2e: usando [Protractor] (https://github.com/angular/protractor) + Jasmine (Arquivos: src / ** / *. spec.js)

Apenas implemente um teste e2e com você não pode reproduzi-lo com um teste de unidade.

# Where this project need more love

- Documentação
- Reduza o tamanho da lib sem ofuscar o código
- Internacionalização
- Construir opções
- Testes unitários
- Incluir mais navegadores na configuração de teste
- E novas máscaras de entrada
