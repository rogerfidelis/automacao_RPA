# renomearArquivos
Renomear arquivos em diretório
O código a seguir foi desenvolvido em Python para renomear arquivos em diretório utilizando RPA (Robotic Process Automation).

Passo 1: Importar os Módulos necessários para localizar os diretórios onde o python fará modificações

from pathlib import Path 
import os


Passo 2: Localizar o diretório onde se encontra a pasta com os arquivos a serem modificados

arquivos= r'C:\Users\roger\automacoes_notas'  #NOTA_SE que a pasta "automacoes_notas" é a pasta onde contém arquivos .pdf a serem modificados
caminho= Path(f'{arquivos}')


Passo 3: Rodar a função os.chdir para direcionar o codigo para dentro da pasta descrita no passo 2, e rodar a função os.getcwd() para certificar que o jupyter esta no diretório correto.

os.chdir(arquivos)
os.getcwd()


Passo 4: Certificar que o código esta lendo todos os arquivos PDF da pasta específicada.

arquivos = caminho.iterdir()

i=0
for arquivo in arquivos:
    a= str(arquivo)
    if ".PDF" in a:
        print(f'{a[:]}')
        print(f'CTE_{a[-20:-14]}')
        i=i+1
print(i)


Passo 5: Alterar a nomenclatura do arquivos PDF para nova nomenclatura.

arquivos = caminho.iterdir()

for arquivo in arquivos:
    a= str(arquivo)
    if '.PDF' in a:
        print(f'{a[:]}')
        print(f'{medicao}\CTE_{a[-20:-14]}.pdf')
        Path(f'{a[:]}').rename(f'{medicao}\CTE_{a[-20:-14]}.pdf')

print("Operação concluída")

OBS: nome do arquivo era: 33200560541240000710570010000358161006836166.PDF
     nome do arquivo passou a ser: CTE_035816.pdf
