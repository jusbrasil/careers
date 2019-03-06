# Fullstack Engineer Challenge

Este é um desafio para testar seus conhecimentos em JavaScript, React, Relay, Graphql, tecnologia de backend e banco de dados de sua preferência;

Neste teste existem várias respostas corretas, pois o objetivo é avaliar a sua forma de codificação, e suas habilidades usando a tecnologia proposta.

## Obrigatoriedades

O projeto deve ser desenvolvido em React, Relay, Graphql consumindo as APIs (utilize a tecnologia de sua escolha) e utilizando banco de dados (de sua preferência também).

O Front-End deve utilizar Material UI: https://material-ui-next.com/

Os produtos disponíveis devem ser recuperados através do Graphql que por sua vez acessará sua(s) API(s).

## Carrinho de Compras

Seu objetivo é montar um carrinho de compras simples, conforme o prototipo a seguir:

O layout deve ser como de um site de vendas convencional, com uma listagem de produtos e um ícone de carrinho de compras no topo do site.

O ícone do carrinho de compras deve exibir uma badge com a quantidade de itens presente no carrinho.

Ao finalizar a compra no carrinho, deverá ser direcionado a uma tela de checkout para pagamento somente com cartão de crédito e com persistência do pedido ao concluir com sucesso.

A tela de listagem de produtos deve:

- Listar produtos
  - Ao entrar no projeto, deve exibir os produtos na listagem com foto, titulo e preço formatado em reais. Esses produtos devem estar cadastrados no banco de dados;
  - Ao clicar no produto da lista, deve exibir os detalhes de um produto individual;
- Permitir comprar
  - Ao clicar em comprar e o produto não estiver no carrinho, deve ser adicionado;
  - Ao clicar em comprar e o produto ja existir no carrinho, deve ser incrementado em 1;
- Exibir resumo do carrinho
  - Exibir no ícone do carrinho uma badge com quantidade de itens;
  - Exibir ao lado do icone, o valor total da compra;

O carrinho deve:

- Permitir remover itens;
  - Ao remover, liberar o estoque do produto;
- Permitir alterar a quantidade de um item;
  - Ao clicar em aumentar, deve incrementar em 1;
  - Ao clicar em diminuir, deve decrementar em 1;
  - Ao incrementar, deve validar se o produto ainda possui estoque;
  - Ao decrementar, deve liberar o estoque do produto;
  - Não deve permitir o usuário informar quantidade zero;
- Exibir o somatório total dos itens incluidos;
- Exibir botão para concluir a compra e direcionar para a tela de checkout;

A tela de checkout deve:

- Ter um número de cartão que sempre aprova os pagamentos e outro que sempre os reprova;
- Ao concluir, checar se existe estoque;
- Persistir o pedido no banco de dados ao confirmar a compra;

## Diferenciais
- Usar uma dessas tecnologias para o backend: PHP, Python ou NodeJS
- Criar issues e resolvê-las a partir de pull requests
- Documentação no código
- Arquivos pequenos com poucas responsabilidades
- Estado da aplicação bem estruturado
- Usabilidade e feedback para o usuário no carregamento da consulta
- Seguir algum Javascript Style Guide
- Layout responsivo (seja criativo!)
- Ambiente em contâineres
- Testes unitários
