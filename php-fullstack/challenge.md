# PHP Challenge
Este é um desafio para testar seus conhecimentos em PHP, Javascript, HTML 5 e CSS 3.

Neste teste existem várias respostas corretas, pois o objetivo é avaliar a sua forma de codificação, e suas habilidades usando as tecnologias propostas.

## Cadastro e Pagamento
Seu objetivo é desenvolver uma aplicação web contendo fluxo de cadastro de usuário com tela de checkout para assinatura de um plano e uma API para processar o pagamento da assinatura.
 
### Aplicação Web
O cadastro de usuários deve ter os seguintes campos devidamente validados:
-   Nome completo
-   E-mail
-   CPF
-   Endereço completo
-   Telefones (deve ser possível cadastrar vários)

Ao realizar o cadastro, deverá ser exibida uma tela de checkout com o resumo dos dados cadastrados, planos disponíveis e o form para pagamento.

Ao selecionar o plano, preencher o form e confirmar, deverá consumir a API para processar o pagamento e exibir ao usuário o resultado da transação. Nesta tela, disponibilizar link para tentar novamente se a transação falhar.

### API de pagamentos
A API de pagamentos deve:
-   utilizar a arquitetura REST
-   ter um endpoint para "charge"
--   Crie um número de cartão que sempre aprova os pagamentos, outro que sempre os reprova e outro que varia aleatoriamente.
-   ter um endpoint para obter os dados de um pagamento
-   gravar todas as chamadas à API
    
## Obrigatoriedades
-   Utilizar PHP 7.x sem framework    
-   Testes unitários
-   Ambiente em contêineres
-   Readme do projeto com guia para instalar e rodar localmente
-   Disponibilizar os projetos em Git (Github, Bitbucket, Gitlab, etc)
