import sqlite3 as lite
con = lite.connect('dados.db')

with con:
    cur = con.cursor()
    cur.execute("CREATE TABLE inventario(id PRIMARY KEY AUTOINCREMENT,nome TEXT, local TEXT, descricao TEXT,marca TEXT, data_da_compra DATE, valor_da_compra DECIMAL,serie TEXT, imagem TEXT)")

import sqlite3 as lite
from datetime import datetime

con = lite.connect('dados.db')
def inserir_form(i):
    with con:
        cur = con.cursor()
        query = "INSERT INTO inventario (nome, local, descricao, marca, data_da_compra, valor_da_compra, serie, imagem) VALUES (?,?,?,?,?,?,?,?)"
        cur.execute(query, i)

        def atualizar_form(i):
            with con:
                cur = con.cursor()
                query = "DELETE FROM inventario WHERE id=?"
                cur.execute(query, i)

                def atualizar_form(i):
                    with con:
                        cur = con.cursor()
                        query = "UPTADE inventario SET nome=?, local=?, descricao=?, marca=?, data_da_compra=?, valor_da_compra=?, serie=?, imagem=? WHERE id=?"
                        cur.execute(query, i)

                        def ver_form():
                            lista_itens = []
                            with con:
                                cur = con.cursor()
                                cur.execute("SELECT * FROM inventario")
                                rows = cur.fetchall()
                                for row in rows:
                                    lista_itens.append(row)
                                    return lista_itens

                                    def ver_iten(id):
                                        lista_itens = []
                                        with con:
                                            cur = con.cursor()
                                            cur.execute("SELECT * inventario WHERE id=?",(id))
                                            rows = cur.fetchall()
                                            for row in rows:
                                                lista_itens.append(row)
                                                return lista_itens
