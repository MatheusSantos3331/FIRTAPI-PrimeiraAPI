#API - é um lugar para disponibilizar recursos e funcionalidades
# Objetivo - Criar um apo que disponibiliza a consulta, criação, edição e exclusão de livros.
# URL Base - localhost
# Endpoints - 
#  - localhost/livros (GET)
#  - localhost/livros (POST)
#  - localhost/livros/id (GET)
#  - localhost/livros/id (PUT)
#  - localhost/livros/id (DELETE)
# recursos - livros
from flask import Flask, jsonify, request

app = Flask(__name__)
#lista de livros
livros = [ 
    {
        'id': 1,
        'titulo': 'O senhor dos Anéis - A sociedade do Anel',
        'autor' : 'J.R.R Tolkien',
    },
    {
        'id' : 2,
        'titulo' : 'Harry Potter e a Pedra Filosofal',
        'autor' : 'J.k Howling',
    },
    {
        'id' : 3,
        'titulo' : 'Código Limpo',
        'autor' : 'Robert Cecil Martin',
    },
    {
        'id' : 4,
        'titulo' : 'A Teoria Geral do Emprego, do Juro e da Moeda',
        'autor' : 'John Maynard Keynes',
    },
    {
        'id' : 5,
        'titulo' : 'A Riqueza das Nações',
        'autor' : 'Adam Smith',
    }

]
#consultar os livros
@app.route('/livros', methods=['GET'])#adiciona no final do link do local host
def oberter_livros():
    return jsonify(livros)
#constultar livros por id
@app.route('/livros/<int:id>',methods=['GET'])
def consultar_livros_id (id):
    for livro in livros:
        if livro.get('id') == (id):
            return jsonify(livro)
#editar o livro
@app.route('/livros/<int:id>',methods=['PUT'])
def editar_licro_id(id):
    livro_alterado = request.get_json()
    for indice,livro in enumerate(livros):
        if livro.get ('id') == id:
            livros[indice].update(livro_alterado)
            return jsonify(livros[indice])
#incluir novo livro
@app.route('/livros/',methods=['POST'])
def incluir_Novo_livro():
    novo_livros = request.get_json()
    livros.append(novo_livros)
    return jsonify(livros)
#excluir um livro
@app.route('/livros/<int:id>',methods=['DELETE'])
def Excluir_livro(id):
    for indice, livro in enumerate(livros):
        if livro.get('id') == id:
            del livros[indice]
    
    return jsonify(livros)
    
app.run(port=5000,host='localhost',debug=True)
