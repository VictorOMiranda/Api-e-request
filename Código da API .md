# Api-e-request


Código criado no replit

#Bibliotecas usadas 

import pandas as pd
from flask import Flask, jsonify

app = Flask(__name__)

#funcionalidades

@app.route('/')
def homepage():
  return "A Api está no ar"

@app.route('/pegarvendas')
def pegarvendas():
  tabela = pd.read_csv('advertising.csv')
  total_vendas = tabela['Vendas'].sum()
  resposta = {'total_vendas':total_vendas}
  return jsonify(resposta)


#rodar a api
app.run(host='0.0.0.0')
