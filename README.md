# RPG
My first project

from sys import exit
from random import randint

# from time import sleep
# from os import system

money = float(1000)
lvl1 = randint(100, 250)
lvl2 = randint(300, 500)
lvl3 = randint(550, 820)
lvl4 = randint(1000, 1450)
lvl5 = randint(1500, 2000)
lvl1m = randint(10, 25)
lvl2m = randint(30, 50)
lvl3m = randint(55, 92)
lvl4m = randint(100, 150)
lvl5m = randint(150, 200)


class Armas:
    def __init__(self, preco, dano):
        self.preco = preco
        self.dano = dano

    pass


class Pocao:
    def __init__(self, preco, efeito):
        self.preco = preco
        self.efeito = efeito

    pass


class Armaduras:
    def __init__(self, preco, defesa):
        self.preco = preco
        self.defesa = defesa

    pass


class Npc:
    def __init__(self, ataque, life, battle):
        self.ataque = ataque
        self.life = life
        self.battle = battle

    pass


espada_simples = Armas(preco=0, dano=1)
espada_guerreiro = Armas(preco=50, dano=2)
espada_lendaria = Armas(preco=8989, dano=390)
bee_keeper = Armas(preco=2900, dano=100)
breaker_blade = Armas(preco=1300, dano=78)
terra_blade = Armas(preco=5000, dano=250)
dente_sabre = Armas(preco=20800, dano=1200)
cactus_sword = Armas(preco=240, dano=69)

pocao_basica = Pocao(preco=1, efeito=1)  # Regeneração Simples
pocao_avancada = Pocao(preco=1, efeito=2)  # Super Regeneração
pocao_lendaria = Pocao(preco=1, efeito=3)  # Aumenta dano em 2 rounds
super_healing = Pocao(preco=700, efeito=4)  # triplo da regeneracao simples
pocao_battle = Pocao(preco=1200, efeito=5)  # duplica a vida e dano por 3 rounds
titan = Pocao(preco=2300, efeito=6)  # o dobro do efeito da pocao battle
death = Pocao(preco=20, efeito=7)  # mata os players
respawn = Pocao(preco=890, efeito=8)  # reinicia o modo campanha

armadura_basica = Armaduras(preco=1, defesa=1)  # Defesa Simples
armadura_avancada = Armaduras(preco=1, defesa=1)  # Defesa Avançada
armadura_lendaria = Armaduras(preco=1, defesa=1)  # Super Defesa
hulk = Armaduras(preco=3000, defesa=9999)  # anula o ataque a cada 5 rounds


class Personagem:
    def __init__(self, classe, nome, dano, vida, shield):
        self.classe = classe
        self.nome = nome
        self.dano = dano
        self.vida = int(vida)
        self.shield = shield

    pass


invent1 = []
invent2 = []
invent3 = []
invent4 = []


def mi():
    print(f'Inventário\n'
          f'\nGuerrero: ', invent1,
          f'\nArqueiro: ', invent2,
          f'\nMago: ', invent3,
          f'\nGatuno: ', invent4)


print(
    '\n\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒'
    '\n▒▒▒\033[0:31m════════╗\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m║════════════╗\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒'
    '\n▒▒▒\033[0:31m║░░░░░░░╚════╗\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m╚╗░░░░░░░░░░░╚═╗\033[0:36m▒▒▒▒▒▒▒▒▒▒▒'
    '\n▒▒▒\033[0:31m╚╗░░░░░░░░░░░╚╗\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░░░░╚═╗\033[0:36m▒▒▒▒▒▒▒▒▒'
    '\n▒▒▒▒\033[0:31m║░░░░░░░░░░░░╚═╗\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░░░░░░╚╗\033[0:36m▒▒▒▒▒▒▒▒'
    '\n▒▒▒▒\033[0:31m║░░░░░░░░░░░░░░║\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m╔╗\033[0:36m▒▒▒▒▒▒\033[0:31m╚╗░░░'
    '░░░░░░░░░░░░║\033[0:36m▒▒▒▒▒▒▒▒'
    '\n▒▒▒▒\033[0:31m╚╗░░░░░░░░░░░░╔╝\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m║║\033[0:36m▒▒▒▒▒▒▒\033[0:31m║░░░░'
    '░░░░░░░░░░░╚╗\033[0:36m▒▒▒▒▒▒▒'
    '\n▒▒▒▒▒\033[0:31m║░░░░░░░░░╔══╝\033[0:36m▒▒▒▒▒▒▒▒▒▒\033[0:31m╔══╦═╗╔═╝║\033[0:36m▒▒▒▒▒▒▒\033[0:31m║░░░░░░░'
    '░░░░░░░░░║\033[0:36m▒▒▒▒▒▒▒'
    '\n▒▒▒▒▒\033[0:31m║░░░░░░══╦╝\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m║╔╗║╔╗╣╔╗║\033[0:36m▒▒▒▒▒▒▒\033[0:31m╚╗░░░░░░░'
    '░░░░░░░░║\033[0:36m▒▒▒▒▒▒▒'
    '\n▒▒▒▒▒\033[0:31m╚╗░░░░░░░╚════╗\033[0:36m▒▒▒▒▒▒▒▒▒\033[0:31m║╔╗║║║║╚╝║\033[0:36m▒▒▒▒▒▒▒▒\033[0:31m║░░░░░░░░░'
    '░░░░░░╚╗\033[0:36m▒▒▒▒▒▒'
    '\n▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░░░╚╗\033[0:36m▒▒▒▒▒▒▒▒\033[0:31m╚╝╚╩╝╚╩══╝\033[0:36m▒▒▒▒▒▒▒▒\033[0:31m╚╗░░░░░░░░'
    '░░░░░░░║\033[0:36m▒▒▒▒▒▒'
    '\n▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░░░░╚╗\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░░░░░╔╝\033[0:36m▒▒▒▒▒▒'
    '\n▒▒▒▒▒▒\033[0:31m╚╗░░░░░░░░░░░░░║\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░░░░╔╝\033[0:36m▒▒▒▒▒▒▒'
    '\n▒▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░░░╔╝\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m╚╗░░░░░░░░░░░╔╝\033[0:36m▒▒▒▒▒▒▒▒'
    '\n▒▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░╔═╝\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m║░░░░░░░░░░╔╝\033[0:36m▒▒▒▒▒▒▒▒▒'
    '\n▒▒▒▒▒▒▒\033[0:31m═══════════╝\033[0:36m▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[0:31m═══════════╝\033[0:36m▒▒▒▒▒▒▒▒▒▒'
    '\n▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒\033[030m'
)
print(f"Olá Amigo\nBem-vindo ao B&D: Battles and Dragons\n{'=' * 30}\nPrimeiro vamos criar um personagem")

aleatorio = input('Deseja aleatorizar os status dos personagens? S/N: ')
if aleatorio == 'S' or aleatorio == 's':
    personagem1 = Personagem(classe='Guerreiro(a)',
                             nome=str(input('Informe o nome do Guerreiro(a): ')),
                             dano=randint(30, 50),
                             vida=randint(12, 20),
                             shield=0)
    personagem1.nome = personagem1.nome.strip()
    while True:

        if len(personagem1.nome) < 3:
            personagem1.nome = str(input(f'\nOBS: O nome deve ter no mínimo 3 caracteres.'
                                         f'\nInforme o nome do Guerreiro(a): '))
            personagem1.nome = personagem1.nome.strip()
        if len(personagem1.nome) >= 3:
            break

    personagem2 = Personagem(classe='Arqueiro(a)',
                             nome=str(input('Informe o nome do Arqueiro(a): ')),
                             dano=randint(30, 50),
                             vida=randint(12, 20),
                             shield=0)
    personagem2.nome = personagem2.nome.strip()
    while True:
        if len(personagem2.nome) < 3:
            personagem2.nome = str(input(f'\nOBS: O nome deve ter no mínimo 3 caracteres.'
                                         f'\nInforme o nome do Arqueiro(a): '))
            personagem2.nome = personagem2.nome.strip()
        if len(personagem2.nome) >= 3:
            break

    personagem3 = Personagem(classe='Mago(a)',
                             nome=str(input('Informe o nome do Mago(a): ')),
                             dano=randint(30, 50),
                             vida=randint(12, 20),
                             shield=0)
    personagem3.nome = personagem3.nome.strip()
    while True:
        if len(personagem3.nome) < 3:
            personagem3.nome = str(input(f'\nOBS: O nome deve ter no mínimo 3 caracteres.'
                                         f'\nInforme o nome do Mago(a): '))
            personagem3.nome = personagem3.nome.strip()
        if len(personagem3.nome) >= 3:
            break

    personagem4 = Personagem(classe='Gatuno(a)',
                             nome=str(input('Informe o nome do Gatuno(a): ')),
                             dano=randint(30, 50),
                             vida=randint(12, 20),
                             shield=0)
    personagem4.nome = personagem4.nome.strip()
    while True:
        if len(personagem4.nome) < 3:
            personagem4.nome = str(input(f'\nOBS: O nome deve ter no mínimo 3 caracteres.'
                                         f'\nInforme o nome do Gatuno(a): '))
            personagem4.nome = personagem4.nome.strip()
        if len(personagem4.nome) >= 3:
            break


elif aleatorio == 'N' or aleatorio == 'n':
    personagem1 = Personagem(classe='Guerreiro(a)',
                             nome=str(input('Informe o nome do Guerreiro(a): ')),
                             dano=float(input('Informe o dano que o personagem pode causar: ')),
                             vida=float(input('Informe o valor equivalente a vida do personagem: ')),
                             shield=0)
    personagem2 = Personagem(classe='Arqueiro(a)',
                             nome=str(input('Informe o nome do Arqueiro(a): ')),
                             dano=float(input('Informe o dano que o personagem pode causar: ')),
                             vida=float(input('Informe o valor equivalente a vida do personagem: ')),
                             shield=0)
    personagem3 = Personagem(classe='Mago(a)',
                             nome=str(input('Informe o nome do Mago(a): ')),
                             dano=float(input('Informe o dano que o personagem pode causar: ')),
                             vida=float(input('Informe o valor equivalente a vida do personagem: ')),
                             shield=0)
    personagem4 = Personagem(classe='Gatuno(a)',
                             nome=str(input('Informe o nome do Gatuno(a): ')),
                             dano=float(input('Informe o dano que o personagem pode causar: ')),
                             vida=float(input('Informe o valor equivalente a vida do personagem: ')),
                             shield=0)

    while personagem1.dano > 50 or personagem1.dano < 30:
        print(
            f'O dano do(a) {personagem1.nome} esta um absurdo, recomenda-se colocar o valor do dano entre'
            '30-50')
        personagem1.dano = float(input('Informe um novo valor para o dano: '))
    while personagem2.dano > 50 or personagem2.dano < 30:
        print(
            f'O dano do(a) {personagem2.nome} esta um absurdo, recomenda-se colocar o valor do dano entre'
            ' 30-50')
        personagem2.dano = float(input('Informe um novo valor para o dano: '))
    while personagem3.dano > 50 or personagem3.dano < 30:
        print(
            f'O dano do(a) {personagem3.nome} esta um absurdo, recomenda-se colocar o valor do dano entre'
            ' 30-50')
        personagem3.dano = float(input('Informe um novo valor para o dano: '))
    while personagem4.dano > 50 or personagem4.dano < 30:
        print(
            f'O dano do(a) {personagem4.nome} esta um absurdo, recomenda-se colocar o valor do dano entre'
            ' 30-50')
        personagem4.dano = float(input('Informe um novo valor para o dano: '))

    while personagem1.vida > 20 or personagem1.vida < 12:
        print(
            f'A vida do(a) {personagem1.nome} esta um absurdo, recomenda-se colocar o valor da vida entre'
            ' 12-20')
        personagem1.vida = float(input('Informe um novo valor para a vida: '))
    while personagem2.vida > 20 or personagem2.vida < 12:
        print(
            f'A vida do(a) {personagem2.nome} esta um absurdo, recomenda-se colocar o valor da vida entre'
            ' 12-20')
        personagem2.vida = float(input('Informe um novo valor para a vida: '))
    while personagem3.vida > 20 or personagem3.vida < 12:
        print(
            f'A vida do(a) {personagem3.nome} esta um absurdo, recomenda-se colocar o valor da vida entre'
            ' 12-20')
        personagem3.vida = float(input('Informe um novo valor para a vida: '))
    while personagem4.vida > 20 or personagem4.vida < 12:
        print(
            f'A vida do(a) {personagem4.nome} esta um absurdo, recomenda-se colocar o valor da vida entre'
            ' 12-20')
        personagem4.vida = float(input('Informe um novo valor para a vida: '))

    dano_media = (personagem4.dano + personagem3.dano + personagem2.dano + personagem1.dano) / 4
    while dano_media > 50 or dano_media < 30:
        print('Os danos estão muito altos, tente equilibra-los')
        personagem1.dano = float(input(f'Informe um novo valor para o dano do(a) {personagem1.nome} : '))
        personagem2.dano = float(input(f'Informe um novo valor para o dano do(a) {personagem2.nome} : '))
        personagem3.dano = float(input(f'Informe um novo valor para o dano do(a) {personagem3.nome} : '))
        personagem4.dano = float(input(f'Informe um novo valor para o dano do(a) {personagem4.nome} : '))

    vida_media = int((personagem4.vida + personagem3.vida + personagem2.vida + personagem1.vida) / 4)
    while vida_media < 12 or vida_media > 20:
        print('As vidas estão muito altas, tente equilibra-las')
        personagem1.vida = float(input(f'Informe um novo valor para a vida do(a) {personagem1.nome} : '))
        personagem2.vida = float(input(f'Informe um novo valor para a vida do(a) {personagem2.nome} : '))
        personagem3.vida = float(input(f'Informe um novo valor para a vida do(a) {personagem3.nome} : '))
        personagem4.vida = float(input(f'Informe um novo valor para a vida do(a) {personagem4.nome} : '))

l_personagem = [personagem1, personagem2, personagem3, personagem4]

while True:
    print(
        '\nEste é o menu de seleção do jogo\nVocê poderá navegar para diversos '
        f"lugares:\n{'-' * 20}\n  Modo Campanha(1)\n{'-' * 20}\n  Modo Treino(2)\n{'-' * 20}\n  Cr"
        f"éditos(3)\n{'-' * 20}\n  Loja(4)\n{'-' * 20}\n  Saída(5)\n{'-' * 20}")

    cnt = int(input('Insira o número correspondente à opção desejada (Digite apenas números entre 1 e 5): '))

    if cnt == 5:
        exit(0)

    elif cnt == 4:
        print('Bem-vindo à loja')
        store = int(input('Escolha um setor, entre WAR(1) e MAGIC(2)\n--->'))
        while True:
            if store == 1:
                break
            elif store == 2:
                break
            else:
                store = int(input('Escolha um setor, entre WAR(1) e MAGIC(2)\n--->'))

        if store == 1:
            print('Bem vindo a loja do Guerreiro e do Gatuno!'
                  f'\n\nLista de armas:'
                  f'\nNome              Preço       Dano      N° Escolha'
                  f'\nBee Keeper         2900        100               1'
                  f'\nBreaker Blade      1300         78               2'
                  f'\nTerra Blade        5000        250               3'
                  f'\nDeath Stickle     20800       1200               4'
                  f'\nCactus Sword        240         69               5')

            compra = int(input('Escolha um item para comprar\n--->'))
            while True:
                if compra == 1:
                    if money <= 2900:
                        print('Money Insuficiente')
                        break
                    dcompra = int(input('Queres comprar para o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                    if dcompra == 1:
                        invent1.append('bee_keeper')


                        def fw1():
                            personagem1.dano += 100


                        money -= 2900
                        break
                    elif dcompra == 2:
                        invent4.append('bee_keeper')


                        def fw2():
                            personagem1.dano += 100


                        money -= 2900
                        break
                    else:
                        dcompra = int(input('ERRO!! Escolha entre o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                elif compra == 2:
                    if money <= 1300:
                        print('Money Insuficiente')
                        break
                    dcompra = int(input('Queres comprar para o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                    if dcompra == 1:
                        invent1.append('breaker_blade')


                        def fw3():
                            personagem1.dano += 78


                        money -= 1300
                        break
                    elif dcompra == 2:
                        invent4.append('breaker_blade')


                        def fw4():
                            personagem1.dano += 78


                        money -= 1300
                        break
                    else:
                        dcompra = int(input('ERRO!! Escolha entre o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                elif compra == 3:
                    if money <= 5000:
                        print('Money Insuficiente')
                        break
                    dcompra = int(input('Queres comprar para o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                    if dcompra == 1:
                        invent1.append('terra_blade')


                        def fw5():
                            personagem1.dano += 250


                        money -= 5000
                        break
                    elif dcompra == 2:
                        invent4.append('terra_blade')


                        def fw6():
                            personagem1.dano += 250


                        money -= 5000
                        break
                    else:
                        dcompra = int(input('ERRO!! Escolha entre o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                elif compra == 4:
                    if money <= 20800:
                        print('Money Insuficiente')
                        break
                    dcompra = int(input('Queres comprar para o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                    if dcompra == 1:
                        invent1.append('death_stickle')


                        def fw7():
                            personagem1.dano += 1200


                        money -= 20800
                        break
                    elif dcompra == 2:
                        invent4.append('death_stickle')


                        def fw8():
                            personagem1.dano += 1200


                        money -= 20800
                        break
                    else:
                        dcompra = int(input('ERRO!! Escolha entre o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                elif compra == 5:
                    if money <= 240:
                        print('Money Insuficiente')
                        break
                    dcompra = int(input('Queres comprar para o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                    if dcompra == 1:
                        invent1.append('cactus_sword')


                        def fw9():
                            personagem1.dano += 69


                        money -= 240
                        break
                    elif dcompra == 2:
                        invent4.append('cactus_sword')


                        def fw10():
                            personagem1.dano += 69


                        money -= 240
                        break
                    else:
                        dcompra = int(input('ERRO!! Escolha entre o Guerreiro(1) ou para o Gatuno(2)\n--->'))
                else:
                    print(f'\n\nLista de armas:'
                          f'\nNome              Preço       Dano      N° Escolha'
                          f'\nBee Keeper         2900        100               1'
                          f'\nBreaker Blade      1300         78               2'
                          f'\nTerra Blade        5000        250               3'
                          f'\nDeath Stickle     20800       1200               4'
                          f'\nCactus Sword        240         69               5')

                    compra = int(input('ERRO!! Escolha um item para comprar\n--->'))

        if store == 2:
            print('Bem vindo a loja do Mago!'
                  f'\n\nLista de Poções:'
                  f'\nNome              Preço        N° Escolha'
                  f'\nPoção Básica        100                 1'
                  f'\nPoção Avançada      500                 2'
                  f'\nPoção Lendária      700                 3'
                  f'\nSuper Healing       600                 4'
                  f'\nBattle             1240                 5'
                  f'\nTitan               940                 6'
                  f'\nDeath              1300                 7'
                  f'\nRespawn            1400                 8')

            compra = int(input('Escolha um item para comprar\n--->'))
            while True:
                if compra == 1:
                    if money <= 100:
                        print('Money Insuficiente')
                        break
                    invent3.append('pocao_básica')


                    def fm1():
                        personagem3.vida *= 1.5


                    money -= 100
                    break
                elif compra == 2:
                    if money <= 500:
                        print('Money Insuficiente')
                        break
                    invent3.append('poção_avançada')


                    def fm2():
                        personagem3.vida *= 1.75


                    money -= 500
                    break
                elif compra == 3:
                    if money <= 700:
                        print('Money Insuficiente')
                        break
                    invent3.append('poção_lendária')


                    def fm3():
                        personagem3.vida *= 2


                    money -= 700
                    break
                elif compra == 4:
                    if money <= 600:
                        print('Money Insuficiente')
                        break
                    invent3.append('super_healing')


                    def fm4():
                        personagem3.vida *= 4.5


                    money -= 600
                    break
                elif compra == 5:
                    if money <= 1240:
                        print('Money Insuficiente')
                        break
                    invent3.append('battle')


                    def fm5():
                        personagem3.dano *= 2
                        personagem3.vida += 100


                    money -= 1240
                    break
                elif compra == 6:
                    if money <= 940:
                        print('Money Insuficiente')
                        break
                    invent3.append('titan')


                    def fm6():
                        personagem3.dano *= 4
                        personagem3.vida += 200


                    money -= 2480
                    break
                elif compra == 7:
                    if money <= 1300:
                        print('Money Insuficiente')
                        break
                    invent3.append('death')


                    def fm7():
                        personagem3.dano -= personagem3.dano
                        personagem3.vida -= personagem3.vida


                    money -= 1380
                    break
                elif compra == 8:
                    if money <= 1400:
                        print('Money Insuficiente')
                        break
                    invent3.append('respawn')


                    def fm8():
                        print('ERRO 080')  # Funcao ainda nao criada
                else:
                    print(f'\n\nLista de Poções:'
                          f'\nNome              Preço        N° Escolha'
                          f'\nPoção Básica        100                 1'
                          f'\nPoção Avançada      500                 2'
                          f'\nPoção Lendária      700                 3'
                          f'\nSuper Healing       600                 4'
                          f'\nBattle             1240                 5'
                          f'\nTitan               940                 6'
                          f'\nDeath              1300                 7'
                          f'\nRespawn            1400                 8')
                    compra = int(input('ERRO!! Escolha um item para comprar\n--->'))

    elif cnt == 3:
        print(
            'CRÉDITOS:\nEQUIPE - LUIZ ROBERTO, COTIAS, MATHEUS E YAN\nIDEALIZAÇÃO - YAN E MATHEUS\nROTERI'
            'ZAÇÃO - COTIAS\nPROGRAMAÇÃO E REVISÃO - YAN E COTIAS\nBALANCEAMENTO - LUIZ ROBERTO'.title())
        cnt = input('Deseja voltar ao menu principal? S/N')
        if cnt == 'N' or cnt == 'n':
            exit(0)

    elif cnt == 2:
        selecao_m = int(input(
            '\nEste é o menu de seleção do mobs para treino\nVocê poderá escolher um dentre diversos '
            f"mobs:\n{'-' * 20}\n  Mobs Basicos(1)\n{'-' * 20}\n  Bosses(2)\n{'-' * 20}\n"))
        escolha1 = False
        escolha2 = False
        escolha = input(
            'Antes de acessar o modo, escolha apenas dois aventureiros [Guerreiro(1), Arqueiro(2), Mago(3), '
            'Gatuno(4)] ')
        while escolha1 is False and escolha2 is False:
            if '1' in escolha and '2' in escolha:
                escolha1 = 0
                escolha2 = 1
            elif '1' in escolha and '3' in escolha:
                escolha1 = 0
                escolha2 = 2
            elif '1' in escolha and '4' in escolha:
                escolha1 = 0
                escolha2 = 3
            elif '2' in escolha and '3' in escolha:
                escolha1 = 1
                escolha2 = 2
            elif '2' in escolha and '4' in escolha:
                escolha1 = 1
                escolha2 = 3
            elif '3' in escolha and '4' in escolha:
                escolha1 = 2
                escolha2 = 3
            else:
                escolha = input(
                    'ERRO! Escolha apenas dois aventureiros [Guerreiro(1), Arqueiro(2), Mago(3), '
                    'Gatuno(4)] ')
        if selecao_m == 1:
            m_basico = int(input(
                'Este é o menu de seleção do mobs basicos para treino\nVocê poderá escolher um dentre diversos '
                f"mobs basicos:\n{'-' * 20}\n  Zumbi(1)\n{'-' * 20}\n  Bruxa(2)\n{'-' * 20}\n  Minion"
                f"(3)\n{'-' * 20}\n  Goblin(4)\n{'-' * 20}"
                f"\n  Metamorphus(5)\n{'-' * 20}\n  Demon(6)\n{'-' * 20}\n  Voltar(7)\n Random(0)"))
            if m_basico == 0:
                m_basico = randint(1, 6)
            if m_basico == 1:
                cot0 = 0
                zumbi = Npc(ataque=int(1), life=int(50), battle=True)
                while zumbi.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0
                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        zumbi.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            zumbi.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Zumbi tira {zumbi.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {zumbi.life}')
                        l_personagem[escolha1].vida -= zumbi.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        zumbi.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            zumbi.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Zumbi tira {zumbi.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {zumbi.life}')
                        l_personagem[escolha2].vida -= zumbi.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if zumbi.life <= 0:
                        zumbi.battle = False
            if m_basico == 2:
                cot0 = 0
                bruxa = Npc(ataque=int(2), life=int(60), battle=True)
                while bruxa.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0
                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        bruxa.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            bruxa.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nA Bruxa tira {bruxa.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {bruxa.life}')
                        l_personagem[escolha1].vida -= bruxa.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        bruxa.life -= l_personagem[escolha2].dano
                        cot0 = cot0 + 1
                        if cot0 % 2 == 0:
                            bruxa.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nA Bruxa tira {bruxa.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {bruxa.life}')
                        l_personagem[escolha2].vida -= bruxa.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if bruxa.life <= 0:
                        bruxa.battle = False
            if m_basico == 3:
                cot0 = 0
                minion = Npc(ataque=int(3), life=int(70), battle=True)
                while minion.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0
                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        minion.life -= l_personagem[escolha1].dano
                        cot0 = cot0 + 1
                        if cot0 % 2 == 0:
                            minion.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Minion tira {minion.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {minion.life}')
                        l_personagem[escolha1].vida -= minion.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        minion.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            minion.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Minion tira {minion.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {minion.life}')
                        l_personagem[escolha2].vida -= minion.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if minion.life <= 0:
                        minion.battle = False
            if m_basico == 4:
                cot0 = 0
                goblin = Npc(ataque=int(4), life=int(80), battle=True)
                while goblin.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0
                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        goblin.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            goblin.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Goblin tira {goblin.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {goblin.life}')
                        l_personagem[escolha1].vida -= goblin.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        goblin.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            goblin.life += 25
                        print('A terrivel besta grita de dor')
                        print(
                            f'\nO Goblin tira {goblin.ataque} de vida de cada aventureiro enquanto sua vida'
                            f' esta em {goblin.life}')
                        l_personagem[escolha2].vida -= goblin.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if goblin.life <= 0:
                        goblin.battle = False
            if m_basico == 5:
                cot0 = 0
                metamorphus = Npc(ataque=int(10), life=int(120), battle=True)
                while metamorphus.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0
                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        metamorphus.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            metamorphus.life += 25
                        print('A terrivel besta grita de dor')
                        print(
                            f'\nO Metamorphus tira {metamorphus.ataque} de vida de cada aventureiro '
                            f'enquanto sua vida esta em {metamorphus.life}')
                        l_personagem[escolha1].vida -= metamorphus.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        metamorphus.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            metamorphus.life += 25
                        print('A terrivel besta grita de dor')
                        print(
                            f'\nO Metamorphus tira {metamorphus.ataque} de vida de cada aventureiro enquanto '
                            f'sua vida esta em {metamorphus.life}')
                        l_personagem[escolha2].vida -= metamorphus.ataque

                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if metamorphus.life <= 0:
                        metamorphus.battle = False
            if m_basico == 6:
                cot0 = 0
                demon = Npc(ataque=int(30), life=int(350), battle=True)
                while demon.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0
                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        demon.life -= l_personagem[escolha1].dano
                        cot0 = cot0 + 1
                        if cot0 % 2 == 0:
                            demon.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Demom tira {demon.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {demon.life}')
                        l_personagem[escolha1].vida -= demon.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        demon.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            demon.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Demom tira {demon.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {demon.life}')
                        l_personagem[escolha2].vida -= demon.ataque

                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if demon.life <= 0:
                        demon.battle = False

        elif selecao_m == 2:
            m_boss = int(input(
                'Este é o menu de seleção de Bosses para treino\nVocê poderá escolher um dentre diversos '
                f"Bosses:\n{'-' * 20}\n  Golem(1)\n{'-' * 20}\n  Baleia Branca(2)\n{'-' * 20}\n  Esquelet"
                f"o(3)\n{'-' * 20}\n  Super Xandao(4)\n{'-' * 20}\n  Dragao(5)\n{'-' * 20}\n  Voltar(7)\n Random(0)"
                "\n --->"))
            if m_boss == 0:
                m_boss = randint(1, 5)
            elif m_boss == 1:
                cot0 = 0
                golem = Npc(ataque=int(5), life=int(150), battle=True)
                while golem.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0

                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        golem.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            golem.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Golem tira {golem.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {golem.life}')
                        l_personagem[escolha1].vida -= golem.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        golem.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            golem.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Golem tira {golem.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {golem.life}')
                        l_personagem[escolha2].vida -= golem.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if golem.life <= 0:
                        golem.battle = False
            if m_boss == 2:
                cot0 = 0
                bb = Npc(ataque=int(5), life=int(150), battle=True)
                while bb.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0

                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        bb.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            bb.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Baleia Branca tira {bb.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {bb.life}')
                        l_personagem[escolha1].vida -= bb.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        bb.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            bb.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Baleia Branca tira {bb.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {bb.life}')
                        l_personagem[escolha2].vida -= bb.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if bb.life <= 0:
                        bb.battle = False

            if m_boss == 3:
                cot0 = 0
                esqueleto = Npc(ataque=int(6), life=int(150), battle=True)
                while esqueleto.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0

                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")

                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        esqueleto.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            esqueleto.life += 25
                        print('A terrivel besta grita de dor')
                        print(
                            f'\nO Super Xandao tira {esqueleto.ataque} de vida de cada aventureiro enquanto '
                            f'sua vida esta em {esqueleto.life}')
                        l_personagem[escolha1].vida -= esqueleto.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        esqueleto.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            esqueleto.life += 25
                        print('A terrivel besta grita de dor')
                        print(
                            f'\nO Esqueleto tira {esqueleto.ataque} de vida de cada aventureiro enquanto sua '
                            f'vida esta em {esqueleto.life}')
                        l_personagem[escolha2].vida -= esqueleto.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if esqueleto.life <= 0:
                        esqueleto.battle = False

            if m_boss == 4:
                cot0 = 0
                sxandao = Npc(ataque=int(7), life=int(150), battle=True)
                while sxandao.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0

                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        sxandao.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            sxandao.life += 25
                        print('A terrivel besta grita de dor')
                        print(
                            f'\nO Super Xandao tira {sxandao.ataque} de vida de cada aventureiro enquanto '
                            f'sua vida esta em {sxandao.life}')
                        l_personagem[escolha1].vida -= sxandao.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        sxandao.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            sxandao.life += 25
                        print('A terrivel besta grita de dor')
                        print(
                            f'\nO Super Xandao tira {sxandao.ataque} de vida de cada aventureiro enquanto sua '
                            f'vida esta em {sxandao.life}')
                        l_personagem[escolha2].vida -= sxandao.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if sxandao.life <= 0:
                        sxandao.battle = False

            if m_boss == 5:
                cot0 = 0
                dragao = Npc(ataque=int(8), life=int(150), battle=True)
                while dragao.battle:
                    if l_personagem[escolha1].vida < 0:
                        l_personagem[escolha1].vida = 0
                    if l_personagem[escolha2].vida < 0:
                        l_personagem[escolha2].vida = 0
                    print(f"{l_personagem[escolha1].classe}\nDAM{l_personagem[escolha1].dano}\n"
                          f"HP{l_personagem[escolha1].vida}\n{'_' * 10}"
                          f"\n{l_personagem[escolha2].classe}\nDAM{l_personagem[escolha2].dano}\n"
                          f"HP{l_personagem[escolha2].vida}\n{'_' * 10}")
                    LT1 = int(input(f'Escolha com quem atacar: {l_personagem[escolha1].classe}(1),'
                                    f' {l_personagem[escolha2].classe}(2)\n--->'))
                    if LT1 == 1 and not l_personagem[escolha1].vida <= 0:
                        dragao.life -= l_personagem[escolha1].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            dragao.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Dragao tira {dragao.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {dragao.life}')
                        l_personagem[escolha1].vida -= dragao.ataque
                    if LT1 == 2 and not l_personagem[escolha2].vida <= 0:
                        dragao.life -= l_personagem[escolha2].dano
                        cot0 += 1
                        if cot0 % 2 == 0:
                            dragao.life += 25
                        print('A terrivel besta grita de dor')
                        print(f'\nO Dragao tira {dragao.ataque} de vida de cada aventureiro enquanto sua vida esta '
                              f'em {dragao.life}')
                        l_personagem[escolha2].vida -= dragao.ataque
                    if l_personagem[escolha1].vida <= 0 and l_personagem[escolha2].vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if dragao.life <= 0:
                        dragao.battle = False
        else:
            selecao_m = int(input('ERRO! Insira apenas números entre 1 e 2.'
                                  f" \n{'-' * 20}\n  Mobs Basicos(1)\n{'-' * 20}\n  Bosses(2)\n{'-' * 20}\n"))
    elif cnt == 1:
        print('Bom Jogo : D')
        print('=' * 20)
        print(' A história dos nossos heróis começa num passado próximo...')
        print(
            ' A Humanidade contemplava uma longa e estável paz, as pessoas eram felizes e escutavam músicas dos Bardos '
            'enquanto riam sobre a vida. Mas então... ELE apareceu.')
        print('Cidade de Pjodia ')
        print(
            ' Um pobre vilarejo que compreendia-se nas periferias do Reino de Gustaf, tinha poucas ruas, poucos '
            'moradores e pouca segurança.')
        print('\033[0:35m Mago (Criança): Snif Snif Buààà\033[0:30m')
        print(' Camponesa: Nossa, o que foi, Criança?')
        print('  (Olha ao redor)')
        print('  Por acaso você se perdeu da sua mamãe?')
        print('\033[0:35m Mago (Criança): hic s-s-sim\033[0:30m')
        print(' Bêbado: Eu te disse para ir embora! Criança vagabunda')
        print(
            '(Bate na Criança), Não espante as pessoas desse bar, já não basta ter sido abandonada, agora quer '
            'roubar nossas coisas')
        print(' Camponesa: Venha meu bem, cuidarei de você.')
        print('Casa da Camponesa')
        print(' Uma pequena casa, dois andares. Ambiente simples, agradável e aconchegante.')
        print(
            '\033[0:35m Mago (Criança): Estou vendo três outras crianças e um adulto, agora vou ter que aceitar minha'
            ' nova família\033[0:30m')
        print('12 anos depois...')
        print('\033[0:35m Mago (Adolescente): Mãe, o que é essa pedra brilhante que eu e meus '
              'irmãos achamos?\033[0:30m')
        print(
            'Camponesa: Crianças, como? Essa é a pedra de seleção, usada para descobrir os futuros heróis que '
            'derrotarão O Dragão. Vocês devem partir numa jornada, está na hora!')
        print(
            'Camponesa: Andem crianças, vão para o leste, em direção à Rafena, lá vocês encontrarão equipamentos '
            'e ajuda para auxiliá-los a combater o Dragão.')
        print('...\nComeça uma jornada\n...')

        DA1 = int(input('\nEscolha entre seguir sua jornada pelo Pantano(Digite 1) ou pelas Gra'
                        'ndes Dunas(Digite 2)\n--->'))

        while True:
            if DA1 == 1:
                break
            elif DA1 == 2:
                break
            else:
                DA1 = int(input('\nEscolha entre seguir sua jornada pelo Pantano(Digite 1) ou pelas Gra'
                                'ndes Dunas(Digite 2)\n--->'))

        if DA1 == 2:
            print('Grandes Dunas')
            print(
                'Este lugar recebe o nome de Grandes Dunas por conta da quantidade assombrosa de grandes'
                ' aglomerações de areia (dunas), tem-se o boato de que ainda existem piratas nestas terras')
            print('\033[0:35m  Mago: Olhem lá meus irmãos, aquele é um andarilho?\033[0:30m')
            print('\033[0:31m  Guerreiro: Não, parece que é um peregrino, olha as roupas dele.\033[0:30m')
            print('  Andarilho: Olá meu jovens, o sol está quente hoje, não?')
            print(
                'Sou um andarilho em peregrinação, estava viajando junto com o meu grupo, por causa do perigo dos'
                'piratas, mas, acabei me perdendo deles.')
            print('   Vocês viram mais alguém nesse deserto? Vocês podem me ajudar a encontrar o meu bando?')

            DD1 = int(input('\nEscolha entre ajudar(Digite 1) ou não(Digite 2) o Andarilho\n--->'))
            if DD1 == 1:
                print('\n Andarilho: Ah! Muito obrigado por terem apontado a direção que vocês vieram')
                print(
                    ' Vou seguir logo o meu caminho, caso contrário, pode ser que um pirata apareça... '
                    '(Segue seu caminho)')
                print(
                    'Alguns segundos depois do Andarilho sair, percebe-se um tremor em uma das dunas próximas'
                    ' da equipe.')
                print(
                    'Repentinamente, surge um GOLEM que estava soterrado em uma das dunas, ele não possui armadura,'
                    'muito menos olhos.')

                cot1 = 0

                golem = Npc(ataque=int(5), life=int(150), battle=True)
                while golem.battle:
                    if personagem1.vida < 0:
                        personagem1.vida = 0
                    if personagem2.vida < 0:
                        personagem2.vida = 0
                    if personagem3.vida < 0:
                        personagem3.vida = 0
                    if personagem4.vida < 0:
                        personagem4.vida = 0
                    print(f'\nQue comece a batalha...\n'
                          f"\nSTATUS DOS AVATARES\n"
                          f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                          f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                          f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                          f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
                    LG1 = int(
                        input(f'Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                              f'\n\tAbrir o inventario(5)\n--->'))

                    if LG1 == 5:
                        mi()
                    elif LG1 == 1 and not personagem1.vida <= 0:
                        golem.life -= personagem1.dano
                        cot1 += 1
                        if cot1 % 2 == 0 and golem.life > 0:
                            golem.life += 25
                            print("Ele se regenera como uma fenix.")
                        print('A terrivel besta chamada Golem grita de dor')
                        print(f'\nO Golem tira {golem.ataque} de vida de {personagem1.nome} enquanto sua vida esta '
                              f'em {golem.life}')
                        personagem1.vida -= golem.ataque

                    elif LG1 == 2 and not personagem2.vida <= 0:
                        golem.life -= personagem2.dano
                        cot1 += 1
                        if cot1 % 2 == 0 and golem.life > 0:
                            golem.life += 25
                            print("Ele se regenera como uma fenix.")
                        print('A terrivel besta chamada Golem grita de dor')
                        print(f'\nO Golem tira {golem.ataque} de vida de {personagem2.nome} enquanto sua vida esta'
                              f' em {golem.life}')
                        personagem2.vida -= golem.ataque

                    elif LG1 == 3 and not personagem3.vida <= 0:
                        golem.life -= personagem3.dano
                        cot1 += 1
                        if cot1 % 2 == 0 and golem.life > 0:
                            golem.life += 25
                            print("Ele se regenera como uma fenix.")
                        print('A terrivel besta chamada Golem grita de dor')
                        print(f'\nO Golem tira {golem.ataque} de vida de {personagem3.nome} enquanto sua'
                              f' vida esta em {golem.life}')
                        personagem3.vida -= golem.ataque

                    elif LG1 == 4 and not personagem4.vida <= 0:
                        golem.life -= personagem4.dano
                        cot1 += 1
                        if cot1 % 2 == 0 and golem.life > 0:
                            golem.life += 25
                            print("Ele se regenera como uma fenix.")

                        print(f'\nO Golem tira {golem.ataque} de vida de {personagem4.nome} enquanto sua vida esta'
                              f' em {golem.life}')
                        personagem4.vida -= golem.ataque
                        print("Todos os aventureiros foram atacados pela terivel besta, um mar de dores e gritos")
                    else:
                        LG1 = input(
                            'ERRO!!Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                            '\n\tAbrir o inventario(5)\n--->')

                    if personagem1.vida <= 0 and personagem2.vida <= 0 and personagem3.vida <= 0 and personagem4.vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if golem.life <= 0:
                        money += 100
                        print("Vocês acabam de ganhar dinheiro dropado do Golem\n"
                              f"Você tem {money} moedas no atual momento."
                              "\n\033[0:34mGatuno: Ebaa! Desse jeito vamos ficar ricos!\033[0:30m")
                        personagem1.vida += 70
                        personagem2.vida += 70
                        personagem3.vida += 70
                        personagem4.vida += 70
                        print(f"\nSTATUS NOVO DOS AVATARES\n"
                              f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                              f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                              f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                              f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
                        golem.battle = False
                        break

            if DD1 == 2:
                print(' Andarilho: Eu só queria AJUDA!!')
                print('  Deixa, não preciso de vocês mesmo. Passar bem.')
                print(
                    'Alguns segundos depois do Andarilho sair, os aventureiros perceberam um sussurro pairando ao ar.'
                    'Quando olharam para atrás, viram o Andarilho conjurando um feitiço de invocação.')
                print('Repentinamente, surge um GOLEM com uma armadura mágica e com olhos vermelhos. Por mais que'
                      'todos os heróis apliquem sua força, o Golem é muito forte e aparenta ser invencível!')
                print(
                    'Assustado, o aventureiro Gatuno corre do local e abandona os demais. Depois de uma longa'
                    'caminhada, o Gatuno é surpreendido e morto por uma caravana de piratas da areia.')
                print('\nFim de Jogo\n')
                exit(0)

        if DA1 == 1:
            print('Pantano Nevoeiro')
            print(
                'Este local recebeu esse nome por conta de preencher uma grande quantidade de terra com água e '
                'musgo, a umidade do local faz com que grandes porções de névoa se espalhe pelo ambiente.')
            print('É um pântano famoso pelos espécimes de peixes presentes na fauna.')
            print('\033[0:31m Guerreiro: Argh! É horrível ter que lidar com toda essa água.\033[0:30m')
            print('\033[0:32m Arqueiro: Trate de aguentar, você não é criança.\033[0:30m')
            print('\033[0:35m Mago: Aquilo é uma casa?\033[0:30m')
            print('\033[0:34m Gatuno: É sim! Vamos bater na porta.\033[0:30m')
            print('Depois de algumas batidas, uma figura alta abre.')
            print(' Eremita: O que vocês querem? Não tenho esmola, muito menos peixe.')
            DP1 = int(
                input('\nEscolha entre assumir ser pedinte(Digite 1) ou nao se pedinte(Digite 2) o Andarilho\n--->'))
            if DP1 == 1:
                print('\033[0:35m Mago: Tem certeza, senhor?\033[0:30m')
                print('O gatuno entra rapidamente na casa do eremita')
                print('\033[0:34m Gatuno: O senhor parece tem várias coisas de valor, que tal compartilhar?\033[0:30m')
                print(' Eremita: Ladrões!!!! Sintam a minha fúria.')
                print(
                    'O eremita pega um bastão e lança uma rajada de água forte que expulsa todos da sua casa')
                print(' Eremita: Não subestimem os peixes desse pântano')
                print(
                    'O eremita faz um movimento brusco com o bastão e repentinamente surge uma baleia que engole'
                    'todos os aventureiros.')
                exit(0)
            if DP1 == 2:
                print(
                    '\033[0:31m Guerreiro: Acha que eu tenho cara de pedinte? Queremos informações que nos leve '
                    'para Rafena.\033[0:30m')
                print(' Eremita: Ah, nesse caso...')
                print(
                    '\033[0:32mArqueiro: Desculpe a intromissão e mal-educação dos meus irmãos, poderia POR FAVOR, nos '
                    'ajudar? Aparentemente, somos heróis ou alguma coisa assim.\033[0:30m')
                print(' Eremita: Ah, Entendo! Pois bem, peguem esse amuleto e sigam para a direção norte')
                print('  Este pântano costuma a confundir as bússolas de forasteiros.')
                print('\033[0:35m Mago: Esse amuleto parece um espanta-pesadelos, obrigado.\033[0:30m')
                print('  Vamos pessoal. Obrigado de novo, senhor.')
                print('Depois de se retirar, os aventureiros seguem para o norte')
                print(
                    'Após caminhar por um bom tempo, percebem que a água do pântano começou a gerar ondas. Com o '
                    'tempo, estas ondas foram ficando cada vez mais fortes.')
                print('Depois disso, surge uma enorme Baleia Branca')

                cot = 0
                bb = Npc(ataque=int(5), life=int(150), battle=True)
                while bb.battle:
                    if personagem1.vida < 0:
                        personagem1.vida = 0
                    if personagem2.vida < 0:
                        personagem2.vida = 0
                    if personagem3.vida < 0:
                        personagem3.vida = 0
                    if personagem4.vida < 0:
                        personagem4.vida = 0
                    print(f'\nQue comece a batalha...\n'
                          f"\nSTATUS DOS AVATARES\n"
                          f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                          f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                          f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                          f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
                    LB1 = int(input(f'Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                                    f'\n\tAbrir o inventario(5)\n--->'))
                    if LB1 == 5:
                        mi()

                    elif LB1 == 1 and not personagem1.vida <= 0:
                        bb.life -= personagem1.dano
                        cot += 1
                        if cot % 2 == 0:
                            bb.ataque += 8

                        print('A terrivel besta chamada Baleia Branca grita de dor')
                        print(
                            f'\nO Baleia Branca tira {bb.ataque} de vida de {personagem1.nome} enquanto sua vida esta '
                            f'em {bb.life}')
                        personagem1.vida -= bb.ataque

                    elif LB1 == 2 and not personagem2.vida <= 0:
                        bb.life -= personagem2.dano
                        cot += 1
                        if cot % 2 == 0:
                            bb.ataque += 8

                        print('A terrivel besta chamada Baleia Branca grita de dor')
                        print(
                            f'\nO Baleia Branca tira {bb.ataque} de vida de {personagem2.nome} enquanto sua vida esta'
                            f' em {bb.life}')
                        personagem2.vida -= bb.ataque

                    elif LB1 == 3 and not personagem3.vida <= 0:
                        bb.life -= personagem3.dano
                        cot += 1
                        if cot % 2 == 0:
                            bb.ataque += 8

                        print('A terrivel besta chamada Baleia Branca grita de dor')
                        print(f'\nO Baleia Branca tira {bb.ataque} de vida de {personagem3.nome} enquanto sua'
                              f' vida esta em {bb.life}')
                        personagem3.vida -= bb.ataque

                    elif LB1 == 4 and not personagem4.vida <= 0:
                        bb.life -= personagem4.dano
                        cot += 1
                        if cot % 2 == 0:
                            bb.ataque += 8

                        print('A terrivel besta chamada Baleia Branca grita de dor')
                        print(
                            f'\nO Baleia Branca tira {bb.ataque} de vida de {personagem4.nome} enquanto sua vida esta'
                            f' em {bb.life}')
                        personagem4.vida -= bb.ataque
                    else:
                        LB1 = input(
                            'ERRO!!Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                            '\n\tAbrir o inventario(5)\n--->')

                    if personagem1.vida <= 0 and personagem2.vida <= 0 and personagem3.vida <= 0 and personagem4.vida <= 0:
                        print('GAME OVER. Todos os personagens morreram.')
                        exit(0)
                    if bb.life <= 0:
                        money += 500
                        print("Voces acabam de ganhar dinheiro dropado da Baleia Branca"
                              f"Voce tem {money} moedas no atual momento."
                              "\033[0:34mGatuno: Ebaa! Desse jeito vamos ficar ricos!\033[0:30m")
                        personagem1.vida += 70
                        personagem2.vida += 70
                        personagem3.vida += 70
                        personagem4.vida += 70
                        print(f"\nSTATUS NOVO DOS AVATARES\n"
                              f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                              f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                              f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                              f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
                        bb.battle = False

        print('\033[0:31m Guerreiro: Ufa! Finalmente nos livramos daquilo\033[0:30m')
        print('\033[0:32m Arqueiro: Estava tudo sobre controle\033[0:30m')
        print('\033[0:34m Gatuno: Hahaha\033[0:30m')
        print('\033[0:35m Mago: Olha só! Aquela é Rafena!\033[0:30m')
        print('As armadilhas')
        print('\033[0:31m Guerreiro: AAAAII!! O QUE DIABOS É ISSO NA MINHA PERNA??\033[0:30m')
        print('\033[0:32m Arqueiro: Uma armadilha de urso, vem aqui, deixa eu desativar.\033[0:30m')
        print('\033[0:34m Gatuno: AAAAIII!! O que é isso??\033[0:30m')
        print('\033[0:35m Mago: Mais uma armadilha, dessa vez é uma de caça.\033[0:30m')
        print('\033[0:32m Arqueiro: Prestem atenção, esse lugar é cheio de armadilhas\033[0:30m')
        print('\033[0:34m Gatuno: Vamos andar em fila e prestando atenção no chão\033[0:30m')
        print('\033[0:35m Mago: Que enrascada! Quantas armadilhas!\033[0:30m')
        print('\033[0:32m Arqueiro: Deve ter um motivo para isso tudo...\033[0:30m')
        print('\033[0:32m Arqueiro: Nossa mãe tinha falado de um dragão, né? Deve ter alguma relação...\033[0:30m')
        print('\033[0:34m Gatuno: Enfim! Chegamos na cidade, e agora?\033[0:30m')
        print('\nVilarejo de Rafena')
        print(
            'Um vilarejo enorme, possui muitas lojas e casas espaçosas. Tem um extensa população e possui uma '
            'economia muito forte. É ponto turístico e uma cidade muito bonita.')
        print('\033[0:34m Gatuno: Que tal irmos reunir informações?\033[0:30m')
        print('\033[0:31m Guerreiro: Quero ir na loja de armas!\033[0:30m')
        print('\033[0:32m Arqueiro: Acho melhor irmos atrás de um guia\033[0:30m')
        print('\033[0:31m Guerreiro: Quero ir na loja de armas!\033[0:30m')
        print('\033[0:35m Mago: Acho melhor acharmos um gui-\033[0:30m')
        print(' Guia: Ei!! Eu escutei que vocês querem um guia??')
        print('  Eu sou uma ótima guia, por favor, me contratem!')
        print('  Eu custo apenas 199.99$')
        print('\033[0:34m Gatuno: OIII??\033[0:30m')
        print('\033[0:35m Mago: Tudo bem, eu pago\033[0:30m')
        print('\033[0:31m Guerreiro: Irmão, está muito caro, olha a reação do Gatuno.\033[0:30m')
        print('\033[0:35m Mago: Precisamos ser rápido, vamos logo\033[0:30m')
        print(' Guia: Garanto que os senhores não irão se arrepender')
        print('  Então, onde os senhores querem que eu os leve?')
        print('\033[0:31m Guerreiro: A loja de armas!!\033[0:30m')
        print('A guia olha para o mago')
        print('\033[0:35m Mago: Para a loja de armas, por favor.\033[0:30m')
        print(' Guia: Voailá! Eis aqui a melhor loja de armas de Rafena')
        print('  Nós a chamamos de RWS')
        print("\nRafena's Weapon Storage")
        print(
            'Uma loja escura com alguns bancos próximos ao caixa, com várias armas, escudos e armaduras espalhadas '
            'pela loja. Iluminação à velas e um atendente de caixa barbudo e musculoso')
        print('\033[0:31m Guerreiro: Uhuuuuuu!!! Loja de armas!\033[0:30m')
        print(' Balconista: Calma aí, jovem.')
        print('  Não fique tão animado só porque viu algumas prateleiras')
        print('\033[0:34m Gatuno: Seu Balconista, tem alguma recomendação para nós?\033[0:30m')
        print(
            'Balconista: Bem... O animadinho aí poderia comprar um escudo, você talvez uma faca, o do arco poderia '
            'pegar um amuleto e o outro uma armadura')
        print('  Agora é só uma recomendação')
        print(' Guia: Já terminaram as suas compras?')
        print('\033[0:35m Mago: Sim, agora, gostaríamos que nos mostrasse o caminho para o Dragão que '
              'aterroriza estas terras.\033[0:30m')
        print(' Guia: O Dragão? Que pedido incomum, fazem anos que não recebo um pedido deste.')
        print('  É só seguirmos em direção ao portão sul da cidade, depois de lá, não poderei acompanhá-los.')
        print('  Quando saírem da cidade, sigam em linha reta e eventualmente vocês acharão a caverna do dragão.')
        print('  Desejo-lhes boa sorte.')
        print('\033[0:34m Gatuno: Não acho que vamos precisar, mas, obrigado\033[0:30m')
        print('\033[0:32m Arqueiro: Obrigado.\033[0:30m')
        print('\033[0:35m Mago: Vamos?\033[0:30m')
        print('\033[0:31m Guerreiro: Claro, tá esperando o quê?\033[0:30m')

        DA2 = int(input(
            '\nEscolha entre seguir sua jornada pelo Vulcão da Morte(Digite 1), pela Colina dos '
            'Ventos Eternos(Digite 2) ou pela Vale dos Ossos(Digite 3)\n--->'))
        while True:
            if DA2 == 1:
                break
            elif DA2 == 2:
                break
            elif DA2 == 3:
                break
            else:
                DA2 = int(input(
                    '\nEscolha entre seguir sua jornada pelo Vulcão da Morte(Digite 1), pela Colina dos '
                    'Ventos Eternos(Digite 2) ou pela Vale dos Ossos(Digite 3)\n--->'))
        if DA2 == 1:
            print('\033[0:31m Guerreiro: Em direção ao Vulcão da Morte!\033[0:30m')
            print('Depois de várias horas de caminhada')
            print(
                'A larga montanha com uma passagem ingrime e um ar extremamente poluído e denso de cor'
                ' avermelhada. Reza a lenda de que todos os que sobem a montanha, não acabam bem.')
            print('\033[0:34mGatuno: Vamos ter que subir isso tudo?\033[0:30m')
            print('\033[0:35m Mago: Infelizmente sim, algo nos aguarda lá em cima\033[0:30m')
            print('Depois de subir a montanha')
            print('\033[0:31m Guerreiro: Que sufoco! Subir tudo isso com o equipamento adicional não é legal\033[0:30m')
            print('\033[0:32m Arqueiro: Cuidado com a borda, aquilo para ser lava.\033[0:30m')
            print('Repentinamente, os heróis escutam um barulho agudo vindo do céu')
            print('\033[0:34m Gatuno: Meu Deus, uma FÊNIX???\033[0:30m')
            print('\033[0:32m Arqueiro: Não tem jeito, temos que tentar dar um jeito nela\033[0:30m')
            print('\nLuta contra o pássaro\n')
            print('\033[0:32m Arqueiro: Cuidado!!!!\033[0:30m')
            print('O pássaro lança uma rajada de vento muito forte')
            print('Todos os heróis caem dentro do vulcão e morrem.')
            exit(0)
        if DA2 == 2:
            print('\nColina dos Ventos Eternos\n')
            print(
                'Trata-se de uma grande montanha arredondada que é carinhosamente chamada '
                'de colina. Por conta do seu formato oval, é comum presenciar grandes ventanias próximas da base '
                'e, pequenos ciclones quando o vento atinge grandes magnitudes. Reza a lenda que a árvore ao'
                ' topo da colina consegue passar as nuvens')
            print('\033[0:31m Guerreiro: Finalmente Chegamos!!!\033[0:30m')
            print('\033[0:34m Gatuno: Meu Deus, vamos ter que subir isso nesse ventania toda?\033[0:30m')
            print('\033[0:35m Mago: Sim, algo nos aguarda ao topo da colina\033[0:30m')
            print('Depois de vários minutos sofridos')
            print('\033[0:32m Arqueiro: Chegamos.\033[0:30m')
            print('\033[0:31m Guerreiro: Ufa! Que cansaço, o vento não facilita\033[0:30m')
            print('\033[0:35m Mago: Que árvore enorme\033[0:30m')
            print('\033[0:34m Gatuno: Aquilo é um ninho?\033[0:30m')
            print(
                'Gatuno chega perto do ninho.\nApós a aproximação do gatuno ao ninho, ouviu-se um grito '
                'agudo vindo pelo céu')
            print('\033[0:31m Guerreiro: Um UNICÓRNIO ALADO, isso é sério?\033[0:30m')
            print('\033[0:32m Arqueiro: Ele não deve ter gostado de termos chegado perto do ninho\033[0:30m')
            print('\033[0:35m Mago: Acho que não temos opção, vamos ter que lutar\033[0:30m')
            print(
                'Durante a luta, o unicórnio expeliu uma grande rajada de vento muito forte que arremessou '
                'os aventureiros ao ar.\nSuspensos e indefesos no ar, os heróis sucumbiram à morte')
            exit(0)
        if DA2 == 3:
            print(
                'O Vale dos Ossos é chamado assim por conta da atmosfera de morte que rodeia o local e'
                ' a impregnação de esqueletos encantados. Dizem que as almas dos mortos ressentidos '
                'encarnam nesses esqueletos.')
            print('\033[0:35m Mago: Não me sinto confortável aqui.\033[0:30m')
            print('\033[0:32m Arqueiro: Temos que passar por aqui para matar o dragão\033[0:30m')
            print('\033[0:34m Gatuno: Vamos logo.\033[0:30m')
            print(' ? : Cuidado, viajantes!')
            print('Todos olham para atrás')
            print('\033[0:35m Mago: Você tem muita energia espiritual, você é um feiticeiro?\033[0:30m')
            print(' Feiticeiro : Vejo que você tem bom olho, sou o Feiticeiro das Terras Assombradas')
            print(
                '  Tomem cuidado com estas terras, existem várias criaturas místicas perigosas e '
                'malignas por essas bandas.')
            print('\033[0:31m Guerreiro: Valeu Tiozão, mas, a gente já sabe disso\033[0:30m')
            print('  Vamos irmãos, não podemos perder tempo')
            print(
                'Após ignorar os avisos do feiticeiro e seguir em frente, os heróis se depararam com uma'
                ' figura gigante')
            print('\033[0:34m Gatuno: Caramba! Um esqueleto gigante\033[0:30m')
            print('\033[0:32m Arqueiro: Não temos escolha, preparem-se para a batalha.\033[0:30m')
            print('\nComeça a luta com o Boss Esqueleto Gigante')

            cot = 0
            esqueleto = Npc(ataque=int(6), life=int(150), battle=True)
            while esqueleto.battle:
                if personagem1.vida < 0:
                    personagem1.vida = 0
                if personagem2.vida < 0:
                    personagem2.vida = 0
                if personagem3.vida < 0:
                    personagem3.vida = 0
                if personagem4.vida < 0:
                    personagem4.vida = 0
                print(f'\nQue comece a batalha...\n'
                      f"\nSTATUS DOS AVATARES\n"
                      f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                      f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                      f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                      f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
                LE1 = int(input(f'Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                                f'\n\tAbrir o inventario(5)\n--->'))
                if LE1 == 5:
                    mi()

                elif LE1 == 1 and not personagem1.vida <= 0:
                    esqueleto.life -= personagem1.dano
                    cot += 1
                    if cot % 5 == 0:
                        esqueleto.ataque += 4
                        print("Ele se regenera como uma fenix.")
                    print('A terrivel besta chamada Esqueleto Gigante grita de dor')
                    print(f'\nO Esqueleto tira {esqueleto.ataque} de vida de {personagem1.nome} enquanto sua vida esta '
                          f'em {esqueleto.life}')
                    personagem1.vida -= esqueleto.ataque

                elif LE1 == 2 and not personagem2.vida <= 0:
                    esqueleto.life -= personagem2.dano
                    cot += 1
                    if cot % 5 == 0:
                        esqueleto.ataque += 4
                        print("Ele se regenera como uma fenix.")
                    print('A terrivel besta chamada Esqueleto Gigante grita de dor')
                    print(f'\nO Esqueleto tira {esqueleto.ataque} de vida de {personagem2.nome} enquanto sua vida esta'
                          f' em {esqueleto.life}')
                    personagem2.vida -= esqueleto.ataque

                elif LE1 == 3 and not personagem3.vida <= 0:
                    esqueleto.life -= personagem3.dano
                    cot += 1
                    if cot % 5 == 0:
                        esqueleto.ataque += 4
                        print("Ele se regenera como uma fenix.")
                    print('A terrivel besta chamada Esqueleto grita de dor')
                    print(f'\nO Esqueleto tira {esqueleto.ataque} de vida de {personagem3.nome} enquanto sua'
                          f' vida esta em {esqueleto.life}')
                    personagem3.vida -= esqueleto.ataque

                elif LE1 == 4 and not personagem4.vida <= 0:
                    esqueleto.life -= personagem4.dano
                    cot += 1
                    if cot % 5 == 0:
                        esqueleto.ataque += 4
                        print("Ele se regenera como uma fenix.")
                    print('A terrivel besta chamada Grande Esqueleto grita de dor')
                    print(f'\nO Esqueleto tira {esqueleto.ataque} de vida de {personagem4.nome} enquanto sua vida esta'
                          f' em {esqueleto.life}')
                    personagem4.vida -= esqueleto.ataque

                else:
                    LE1 = input(
                        'ERRO!!Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                        '\n\tAbrir o inventario(5)\n--->')

                if personagem1.vida <= 0 and personagem2.vida <= 0 and personagem3.vida <= 0 and personagem4.vida <= 0:
                    print('GAME OVER. Todos os personagens morreram.')
                    exit(0)
                if esqueleto.life <= 0:
                    money += 800
                    print("Voces acabam de ganhar dinheiro dropado do Grande Esqueleto"
                          f"Voce tem {money} moedas no atual momento."
                          "\033[0:34mGatuno: Ebaa! Desse jeito vamos ficar ricos!\033[0:30m")
                    personagem1.vida += 80
                    personagem2.vida += 80
                    personagem3.vida += 80
                    personagem4.vida += 80
                    print(f"\nSTATUS NOVO DOS AVATARES\n"
                          f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                          f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                          f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                          f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
                    esqueleto.battle = False
        print('\nMontanha dos Deuses\n')
        print(
            'Uma montanha de cor amarela e extremamente reluzente. Dizem que a montanha é recipiente de um poder antigo'
            'proveniente dos deuses')
        print(' S.Xandão: Alto lá! O que vocês querem na montanha do Xandão?')
        print('\033[0:34m Gatuno: Ah não! É o Super Xandão\033[0:30m')
        print(
            '\033[0:32m Arqueiro: Sussurra Gente, temos que ter muito cuidado, pois, o Super Xandão a'
            'parenta ser muito poderoso\033[0:30m')
        print(' S.Xandão: Me Respondam! O que vocês querem na Super Montanha que abriga o Castelo do Super Xandão?')
        print('\033[0:31m Guerreiro: Senhor Super Xandão, temos que passar pelos seus aposentos para derrotar'
              ' o Grande Dragão\033[0:30m')
        print(' S.Xandão: Vocês são muito corajosos para tentar passar próximos ao Castelo Lendário do Super Xandão')
        print(
            'S.Xandão: Somente os dignos podem passar perto da Montanha do Super Xandão, então, Super Xandão'
            ' vai ter que lutar contra vocês.')
        print('\nComeça a lutar contra o Boss\n')
        cot = 0
        sxandao = Npc(ataque=int(7), life=int(150), battle=True)
        while sxandao.battle:
            if personagem1.vida < 0:
                personagem1.vida = 0
            if personagem2.vida < 0:
                personagem2.vida = 0
            if personagem3.vida < 0:
                personagem3.vida = 0
            if personagem4.vida < 0:
                personagem4.vida = 0
            print(f'\nQue comece a batalha...\n'
                  f"\nSTATUS DOS AVATARES\n"
                  f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                  f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                  f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                  f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
            LS1 = int(input(f'Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                            f'\n\tAbrir o inventario(5)\n--->'))
            if LS1 == 5:
                mi()

            elif LS1 == 1 and not personagem1.vida <= 0:
                sxandao.life -= personagem1.dano
                cot += 1
                if cot % 2 == 0:
                    sxandao.ataque += 8
                    sxandao.life += 20

                print('A terrivel besta chamada Super Xandao grita de dor')
                print(
                    f'\nO Super Xandao tira {sxandao.ataque} de vida de {personagem1.nome} enquanto sua vida esta '
                    f'em {sxandao.life}')
                personagem1.vida -= sxandao.ataque

            elif LS1 == 2 and not personagem2.vida <= 0:
                sxandao.life -= personagem2.dano
                cot += 1
                if cot % 2 == 0:
                    sxandao.ataque += 8
                    sxandao.life += 20

                print('A terrivel besta chamada Super Xandao grita de dor')
                print(
                    f'\nO Super Xandao tira {sxandao.ataque} de vida de {personagem2.nome} enquanto sua vida esta'
                    f' em {sxandao.life}')
                personagem2.vida -= sxandao.ataque

            elif LS1 == 3 and not personagem3.vida <= 0:
                sxandao.life -= personagem3.dano
                cot += 1
                if cot % 2 == 0:
                    sxandao.ataque += 8
                    sxandao.life += 20

                print('A terrivel besta chamada Super Xandao grita de dor')
                print(f'\nO Super Xandao tira {sxandao.ataque} de vida de {personagem3.nome} enquanto sua'
                      f' vida esta em {sxandao.life}')
                personagem3.vida -= sxandao.ataque

            elif LS1 == 4 and not personagem4.vida <= 0:
                sxandao.life -= personagem4.dano
                cot += 1
                if cot % 2 == 0:
                    sxandao.ataque += 8
                    sxandao.life += 20

            else:
                LS1 = input(
                    'ERRO!!Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                    '\n\tAbrir o inventario(5)\n--->')

                print('A terrivel besta chamada Super Xandao grita de dor')
                print(
                    f'\nO Super Xandao tira {sxandao.ataque} de vida de {personagem4.nome} enquanto sua vida esta'
                    f' em {sxandao.life}')
                personagem4.vida -= sxandao.ataque

            if personagem1.vida <= 0 and personagem2.vida <= 0 and personagem3.vida <= 0 and personagem4.vida <= 0:
                print('GAME OVER. Todos os personagens morreram.')
                exit(0)
            if sxandao.life <= 0:
                money += 1200
                print("Voces acabam de ganhar dinheiro dropado do Super Xandao"
                      f"Voce tem {money} moedas no atual momento."
                      "\033[0:34mGatuno: Ebaa! Desse jeito vamos ficar ricos!\033[0:30m")
                personagem1.vida += 90
                personagem2.vida += 90
                personagem3.vida += 90
                personagem4.vida += 90
                print(f"\nSTATUS NOVO DOS AVATARES\n"
                      f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                      f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                      f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                      f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
                sxandao.battle = False

        DA3 = int(input('\nEscolha entre seguir sua jornada pela Gruta(Digite 1) ou pela Ponte(Digite 2)\n--->'))

        while True:
            if DA3 == 1:
                break
            elif DA3 == 2:
                break
            else:
                DA3 = int(
                    input('\nEscolha entre seguir sua jornada pela Gruta(Digite 1) ou pela Ponte(Digite 2)\n--->'))

        if DA3 == 2:
            print('Ponte')
            print(
                'Trata-se de uma ponte de madeira que cruza um enorme desfiladeiro e separa o território'
                ' humano do Dragão. Dizem que a fenda é tão grande que aqueles que caíram, nunca mais foram vistos.')
            print(' Guardião: Alto lá, humanos!')
            print('\033[0:34m Gatuno: Precisamos passar.\033[0:30m')
            print(
                ' Guardião: Eu sou o Guardião dessa ponte, e não permitirei que vocês provoquem a ira do'
                ' Grande Dragão.')
            print('\033[0:31m Guerreiro: Somos os Heróis destinados a derrotar o Grande Mal,'
                  ' deixe-nos passar.\033[0:30m')
            print('\033[0:32m Arqueiro: Deixe-nos passar, nosso tempo é curto.\033[0:30m')
            print(' Guardião: Tudo bem, os deixarei passar.\n  Se é a morte que vocês querem, podem ir.')
        if DA3 == 1:
            print('Gruta')
            print('Advinda de uma ramificação de ravina, a Gruta é mediamente espaçosa e possui várias estalactites e '
                  'estalagmites')
            print('\033[0:31m Guerreiro: Que gruta esquisita, aquilo são sons?\033[0:30m')
            print('\033[0:32m Arqueiro: De fato, escuto sussurros nessa gruta\033[0:30m')
            print('\033[0:34m Gatuno: Olha alí!\033[0:30m')
            print(' ?: A história diz que eles não devem passar')
            print(' ??: Mas fazer isso tão cedo? Dá um desconto')
            print(' ?: Eu escrevi desse jeito, vamos fazer assim. Eles morrem aqui')
            print(' ??: Tá bom, faça como quiser.')
            print('Depois dessa conversa, parte do teto da gruta caí e soterra os aventureiros.')
            exit(0)
        print('Caverna do Dragão')
        print(
            'Esse local recebeu esse nome por causa de um dragão que nela reside. É uma caverna espaçosa e é cheia de '
            'armaduras, armadilhas quebradas, espadas e materiais reluzentes')
        print('\033[0:35m Mago: Irmãos, finalmente chegamos\033[0:30m')
        print('\033[0:34m Gatuno: Vamos entrar?\033[0:30m')
        print('\033[0:32m Arqueiro: Vamos logo\033[0:30m')
        print('Os aventureiros entram na caverna')
        print(
            'Grande Dragão: Argh! Humanos Nojentos.\n  Já que resolveram aparecer na minha caverna, acredito'
            ' que desejam a morte.\n  Pois bem, concederei vosso desejo ')

        cot = 0
        dragao = Npc(ataque=int(8), life=int(150), battle=True)
        while dragao.battle:
            if personagem1.vida < 0:
                personagem1.vida = 0
            if personagem2.vida < 0:
                personagem2.vida = 0
            if personagem3.vida < 0:
                personagem3.vida = 0
            if personagem4.vida < 0:
                personagem4.vida = 0

            print(f'\nQue comece a batalha...\n'
                  f"\nSTATUS DOS AVATARES\n"
                  f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                  f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                  f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                  f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
            LD1 = int(input(f'Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                            f'\n\tAbrir o inventario(5)\n--->'))
            if LD1 == 5:
                mi()

            elif LD1 == 1 and not personagem1.vida <= 0:
                dragao.life -= personagem1.dano
                cot += 1
                if cot % 1 == 0:
                    dragao.ataque += 10
                    dragao.life += 30

                print('A terrivel besta chamada Dragao grita de dor')
                print(
                    f'\nO Dragao tira {dragao.ataque} de vida de {personagem1.nome} enquanto sua vida esta '
                    f'em {dragao.life}')
                personagem1.vida -= dragao.ataque

            elif LD1 == 2 and not personagem2.vida <= 0:
                dragao.life -= personagem2.dano
                cot += 1
                if cot % 1 == 0:
                    dragao.ataque += 10
                    dragao.life += 5

                print('A terrivel besta chamada Dragao grita de dor')
                print(
                    f'\nO Dragao tira {dragao.ataque} de vida de {personagem2.nome} enquanto sua vida esta'
                    f' em {dragao.life}')
                personagem2.vida -= sxandao.ataque

            elif LD1 == 3 and not personagem3.vida <= 0:
                dragao.life -= personagem3.dano
                cot += 1
                if cot % 1 == 0:
                    dragao.ataque += 10
                    dragao.life += 30

                print('A terrivel besta chamada Dragao grita de dor')
                print(f'\nO Dragao tira {dragao.ataque} de vida de {personagem3.nome} enquanto sua'
                      f' vida esta em {dragao.life}')
                personagem3.vida -= dragao.ataque

            elif LD1 == 4 and not personagem4.vida <= 0:
                dragao.life -= personagem4.dano
                cot += 1
                if cot % 1 == 0:
                    dragao.ataque += 10
                    dragao.life += 30

                print('A terrível besta chamada Dragao grita de dor')
                print(
                    f'\nO Dragao tira {dragao.ataque} de vida de {personagem4.nome} enquanto sua vida esta'
                    f' em {dragao.life}')
                personagem4.vida -= dragao.ataque

            else:
                LD1 = input(
                    'ERRO!!Escolha com quem atacar: Guerreiro(1), Arqueiro(2), Mago(3), Gatuno(4)'
                    '\n\tAbrir o inventario(5)\n--->')

            if personagem1.vida <= 0 and personagem2.vida <= 0 and personagem3.vida <= 0 and personagem4.vida <= 0:
                print('GAME OVER. Todos os personagens morreram.')
                exit(0)
            if dragao.life <= 0:
                money += 2000
                print("Voces acabam de ganhar dinheiro dropado do Dragao"
                      f"Voce tem {money} moedas no atual momento."
                      "\033[0:34mGatuno: Ebaa! Desse jeito vamos ficar ricos!\033[0:30m")
                personagem1.vida += 100
                personagem2.vida += 100
                personagem3.vida += 100
                personagem4.vida += 100
                print(f"\nSTATUS NOVO DOS AVATARES\n"
                      f"Guerreiro\nDAM{personagem1.dano}\nHP{personagem1.vida}\n{'_' * 10}"
                      f"\nArqueiro\nDAM{personagem2.dano}\nHP{personagem2.vida}\n{'_' * 10}"
                      f"\nMago\nDAM{personagem3.dano}\nHP{personagem3.vida}\n{'_' * 10}"
                      f"\nGatuno\nDAM{personagem4.dano}\nHP{personagem4.vida}\n{'_' * 10}")
                dragao.battle = False

            print(
                '\n▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒'
                '\n▒▒▒════════╗▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒║════════════╗▒▒▒▒▒▒▒▒▒▒▒▒'
                '\n▒▒▒║░░░░░░░╚════╗▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒╚╗░░░░░░░░░░░╚═╗▒▒▒▒▒▒▒▒▒▒'
                '\n▒▒▒╚╗░░░░░░░░░░░╚╗▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒║░░░░░░░░░░░░░╚═╗▒▒▒▒▒▒▒▒'
                '\n▒▒▒▒║░░░░░░░░░░░░╚═╗▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒║░░░░░░░░░░░░░░░╚╗▒▒▒▒▒▒▒'
                '\n▒▒▒▒║░░░░░░░░░░░░░░║▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒╔╗▒▒▒▒▒▒╚╗░░░░░░░░░░░░░░░║▒▒▒▒▒▒▒'
                '\n▒▒▒▒╚╗░░░░░░░░░░░░╔╝▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒║║▒▒▒▒▒▒▒║░░░░░░░░░░░░░░░╚╗▒▒▒▒▒▒'
                '\n▒▒▒▒▒║░░░░░░░░░╔══╝▒▒▒▒▒▒▒▒▒▒╔══╦═╗╔═╝║▒▒▒▒▒▒▒║░░░░░░░░░░░░░░░░║▒▒▒▒▒▒'
                '\n▒▒▒▒▒║░░░░░░══╦╝▒▒▒▒▒▒▒▒▒▒▒▒▒║╔╗║╔╗╣╔╗║▒▒▒▒▒▒▒╚╗░░░░░░░░░░░░░░░║▒▒▒▒▒▒'
                '\n▒▒▒▒▒╚╗░░░░░░░╚════╗▒▒▒▒▒▒▒▒▒║╔╗║║║║╚╝║▒▒▒▒▒▒▒▒║░░░░░░░░░░░░░░░╚╗▒▒▒▒▒'
                '\n▒▒▒▒▒▒║░░░░░░░░░░░░╚╗▒▒▒▒▒▒▒▒╚╝╚╩╝╚╩══╝▒▒▒▒▒▒▒▒╚╗░░░░░░░░░░░░░░░║▒▒▒▒▒'
                '\n▒▒▒▒▒▒║░░░░░░░░░░░░░╚╗▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒║░░░░░░░░░░░░░░╔╝▒▒▒▒▒'
                '\n▒▒▒▒▒▒╚╗░░░░░░░░░░░░░║▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒║░░░░░░░░░░░░░╔╝▒▒▒▒▒▒'
                '\n▒▒▒▒▒▒▒║░░░░░░░░░░░░╔╝▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒╚╗░░░░░░░░░░░╔╝▒▒▒▒▒▒▒'
                '\n▒▒▒▒▒▒▒║░░░░░░░░░░╔═╝▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒║░░░░░░░░░░╔╝▒▒▒▒▒▒▒▒'
                '\n▒▒▒▒▒▒▒═══════════╝▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒═══════════╝▒▒▒▒▒▒▒▒▒'
                '\n▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒▒'
                '\nOVER')
    else:
        print('ERRO!! Digite apenas números entre 1 e 5'.upper())
