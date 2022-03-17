jogadores = {}
gols =[]
lista = []
while True:
    jogadores.clear()
    jogadores["nome"] = str(input("Insira o nome do jogador: ")).capitalize()
    partidas = int(input("Quantas partidas ele jogou: "))
    gols.clear()
    for n in range(0, partidas):
        gols.append(int(input(f"  Quantos gols ele fez na {n+1}ª partida: ")))
    jogadores["gols"] = gols[:]
    jogadores['total'] = sum(gols)
    lista.append(jogadores.copy())

    while True:
        perg = str(input("Deseja inserir mais jogadores [S/N]: ")).upper()[0]
        if perg in "SN":
            break
        print("Resposta Errada. Insira S ou N")
    if perg == "N":
        break
print("-=" * 30)
#código para fazer o cabeçalho
print("cod ", end=" ")
for i in jogadores.keys():
    print(f"{i:<16}", end="")
print()
print("-" * 40)
#código termina aqui
#código para mostrar tudo:
for k, v in enumerate(lista):
    print(f"{k:>4} ", end="")
    for d in v.values():
        print(f"{str(d):<15} ", end="")
    print()
print("-" * 40)
while True:
    busca = int(input("Mostrar dados de qual jogador? (Digite 999 para sair): "))
    if busca == 999:
        break
    if busca >= len(lista):
        print(f"ERRO! Não exite o jogador com código {busca}!")
    else:
        print(f"-- LEVANTAMENTO DO JOGADOR {lista[busca]['nome']}:")
        for i, g in enumerate(lista[busca]['gols']):
            print(f"    No jogo {i+1} fez {g} gols.")
    print("-" * 40)
print("Programa encerrado")

