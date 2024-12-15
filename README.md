# Teste-Maluco-Proz-Educacao
Continuação do Estoque em Python

def lista_produtos(lst):
  boole = False
  while(boole == False):
    print("1 - Ver os produtos \n2 - Substituir um produto \n3 - Adicionar um produto \n4 - Verificar itens que precisam de reposição com urgência \n0 - Sair")
    n = int(input())

  if (n == 0):
      boole = True

  elif (n == 1):
      count = 0
      for i in lst:
        index = count
        produto = i[0]
        quantidade = i[1]
        print("Index %s || %s || quantidade: %s" % (index,produto,quantidade))
        count += 1

  elif (n == 2):
      print("Qual o produto que deseja substituir?")
      sub1 = input()
      print("Por qual produto deseja substituir " + sub1 + "?")
      sub2 = input()
      print("Qual a quantidade do produto em estoque?")
      qnt = int(input())
      novo_item = [sub2,qnt]
      item_existe = False
      i = 0
      for x in lst:
        if (x[0] == sub1):
          lst[i] = novo_item
          item_existe = True
        i += 1

  if (item_existe == False):
        print("Não há nenhum item com o nome %s registrado." % (sub1))

  elif (n == 3):
      print("Qual o produto que deseja adicionar?")
      add = input()
      print("Qual a quantidade do produto em estoque?")
      qnt = int(input())
      novo_item = [add,qnt]
      lst.append(novo_item)
    
  elif (n == 4):
      print("Escolha a quantidade de unidades que considera alarmantemente baixa:")
      n = int(input())
      i = 0
      for x in lst:
        if x[1] <= n:
          index = i
          produto = x[0]
          quantidade = x[1]
          print("Index %s || %s || quantidade: %s" % (index,produto,quantidade))
        i += 1

  else:
      print("Opção inválida. Por favor, tente novamente.")

array1 = [["banana", 5],["cenoura",7],["abacaxi",3],["tomate",0],["cereja",24],["melancia",2]]
lista_produtos(array1)
