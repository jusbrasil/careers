# Desafio: Autocomplete

Olá! Esse desafio técnico tem como propósito medir suas habilidades, ver como estuda, pensa e se organiza na prática. Dê o seu melhor! :-)

Existem diversas maneiras e profundidades de solucionar o problema que estamos propondo. Vamos listar algumas sub-tasks opcionais que podem guiá-lo(a) em relação a essas possibilidades. Se optar por fazê-las, escolha as que melhor demonstram suas habilidades e perfil.

Vale salientar que os opcionais são realmente **opcionais**. O jeito que você pensa, estrutura seu código, pesquisa e se organiza são **muito** importantes, portanto não se preocupe se não souber ou tiver tempo de fazê-los. Nesse caso, é melhor entregar algo 100%, mesmo que seja mais básico.

## O desafio
A busca do Jusbrasil permite que você busque pelo título de tópicos e pessoas, entre toda nossa base.
Conforme você digita, alguns resultados são sugeridos, de forma a completar o que você está escrevendo automaticamente.

<p align="center">
  <img src="https://api.monosnap.com/rpc/file/download?id=NXGOEodtY6iY69o3MwJ3slJO9X59W8" />
</p>

Essa funcionalidade (normalmente chamada de TypeAhead ou Autocompletion) é bem difundida e contribui bastante para a UX (*User Experience*) de uma aplicação.

Para esse desafio, queremos que implemente uma *Search Engine*. Há bastante material na Internet, portanto é fácil se perder em relação a isso.

Recomendamos primeiro estudar sobre mecanismos de busca e a estrutura de dados de [índice invertido](https://en.wikipedia.org/wiki/Inverted_index), já que essa estrutura é amplamente utilizada em Search Engines.

Portanto, o mínimo requerido para esse desafio é que seja implementado um Webserver que forneça as seguintes operações em sua API:

## Implementação mínima:
### 1) Indexar um item:
Sua API deve permitir que novos itens sejam adicionados (indexados) através do seguinte endpoint:
```bash
curl -X POST http://my-search-engine/entities -d '{"title": "Some title", "type": "TOPIC"}'
```

### 2) Buscar um item após indexá-lo:
Sua API deve permitir que itens indexados sejam buscados através do seguinte endpoint:
```bash
curl -XGET http://my-search-engine/entities/?q=som
```
Essa busca deve retornar uma lista contendo o item salvo em (1), em formato JSON, por exemplo.

*\*\*A título de exemplo, utilizamos o curl para especificar o formato da API.*


## Opcionais:
### 3) Utilizar uma biblioteca de search engine:
Existem diversas bibliotecas que disponibilizam funcionalidades para search (Lucene, Elasticsearch, Solr, etc). Elas permitem que você persista uma grande quantidade de registros em disco de maneira eficiente. Algumas, como o Elasticsearch, permitem inclusive que seu cluster de busca seja facilmente escalável.

### 4) Criar uma interface para a busca:
Caso deseje ir além da implementação da API, se você se sente confortável implementando tecnologias Frontend ou Mobile, jogue duro e implemente uma interface para usuários finais.

### 5) Utilizar Docker:
Se manja de infra e quer deixar sua API pronta para escalar na cloud, deixe ela pronta para rodar em containers Docker. Sugerimos utilizar o Docker-compose, já que caso utilize alguma Search Engine como o Elasticsearch, fica mais fácil de criar um ambiente de desenvolvimento controlado.

### 6) Implementar filtro por tipo de entidade:
Aceitar na API um parâmetro para filtrar os resultados por determinado tipo de entidade (TOPIC, PERSON, etc). Por exemplo:
```bash
curl -XGET http://my-search-engine/entities/?q=som&entity_type=TOPIC
```

### 7) Criar testes:
Uma parte importantissima do desenvolvimento é a criação de testes automatizados. Recomendamos fortemente que você cubra sua aplicação implementando testes unitários/integração.

### 8) Integrar com ambiente de Continuous Integration:
Quer que os testes implementados no item (7) rodem a cada commit para saber de forma automatizada o que está quebrado? Integre seu projeto com uma ferramenta de integração contínua. Sugestão: https://travis-ci.org/

**Happy coding! :-)**
