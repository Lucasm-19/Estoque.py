# Estoque.py

estoque = {}

def adicionar_produto():
    nome = input("Nome do produto: ")
    if nome in estoque:
        print("Produto já existe no estoque.")
    else:
        preco = float(input("Preço do produto: "))
        quantidade = int(input("Quantidade em estoque: "))
        estoque[nome] = {"preco": preco, "quantidade": quantidade}
        print("Produto adicionado com sucesso!")

def atualizar_produto():
    nome = input("Nome do produto a ser atualizado: ")
    if nome in estoque:
        preco = float(input("Novo preço: "))
        quantidade = int(input("Nova quantidade: "))
        estoque[nome] = {"preco": preco, "quantidade": quantidade}
        print("Produto atualizado!")
    else:
        print("Produto não encontrado.")

def excluir_produto():
    nome = input("Nome do produto a ser excluído: ")
    if nome in estoque:
        del estoque[nome]
        print("Produto excluído.")
    else:
        print("Produto não encontrado.")

def visualizar_estoque():
    if estoque:
        print("\nEstoque Atual:")
        for nome, dados in estoque.items():
            print(f"Produto: {nome} | Preço: R${dados['preco']:.2f} | Quantidade: {dados['quantidade']}")
    else:
        print("Estoque vazio.")

def menu():
    while True:
        print("\n--- MENU ---")
        print("1. Adicionar Produto")
        print("2. Atualizar Produto")
        print("3. Excluir Produto")
        print("4. Visualizar Estoque")
        print("5. Sair")
        opcao = input("Escolha uma opção: ")

        if opcao == "1":
            adicionar_produto()
        elif opcao == "2":
            atualizar_produto()
        elif opcao == "3":
            excluir_produto()
        elif opcao == "4":
            visualizar_estoque()
        elif opcao == "5":
            print("Saindo do sistema...")
            break
        else:
            print("Opção inválida.")

# Inicia o sistema
menu()



