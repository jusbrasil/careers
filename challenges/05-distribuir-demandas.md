# Desafio: Distribuição de demandas para correspondentes

Muitos escritórios de advocacia precisam contratar centenas de advogados em diferentes cidades do Brasil todos os meses.
O objetivo desse desafio é distribuir de forma eficiente as demandas enviadas pelos escritórios aos advogados cadastrados no sistema.

### Setup
Os tipos de serviço prestados pelos correspondentes em nosso desafio serão:

* Audiências
* Cópia
* Protocolo
* Acompanhamento
* Distribuição

Você deve gerar randomicamente uma base de 5.000 advogados distribuídos entre os Estados. Geralmente os advogados prestam mais de um serviço e alguns podem atuar em mais de um Estado. Distribuir SP: 30%, RJ 15%, MG 10%, demais estados igualmente.

Também será necessário gerar um arquivo CSV com 2000 demandas, conforme exemplo abaixo. A Cidade não é obrigatório.

### Entrega

Inicialmente será preciso disponibilizar uma rota para receber as demandas dos escritórios.
Na API do exemplo abaixo, o envio pode ser feito de duas formas: uma demanda por vez ou por meio do upload de um arquivo.

O principal desse desafio é criar um programa capaz de distribuir as demandas entre os advogados cadastrados.
A distribuição deve atender os seguintes requisitos:
- uma demanda não pode ser enviada para mais de 10 advogados por vez
- um advogado só pode receber demandas das cidades (ou estado) em que atuam
- um advogado só pode receber demandas dos serviços que fornecem

Sugerimos adotar uma abordagem produtor/consumidor assíncrona, em que novas demandas são publicadas em uma fila (e.g. RabbitMQ) e os consumidores (e.g. tasks Celery) notificam os advogados. A notificação é simples, apenas imprimir na tela conform API exemplo.


#### API Base
```python
# app.py
import flask
from flask import request

app = flask.FLask(__name__)

@app.route('/demandas/', methods=['POST'])
def new():
  # single job
  pass

@app.route('/demandas/upload', methods=['POST'])
def upload():
  # multiple jobs, import from CSV
  pass

@app.route('/advogados/<int:id>/notificar', methods=['POST'])
def notificar(id):
  print('Advogado {id} recebeu a demanda {lead_id} do estado {state}'.format(id=id, **request.form))
```


#### Exemplo arquivo de demandas em CSV
```csv
Cidade,Estado,DataLimite,TipoServico
Salvador,BA,2019-08-20,Cópia
São Paulo,SP,2019-09-03,Protocolo
```
