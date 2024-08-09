# C-lculo-de-Tinta-Necess-ria-para-Pintura-e-Otimiza-o-de-Custos-em-uma-Loja-de-Tintas
Cálculo de Tinta Necessária para Pintura e Otimização de Custos em uma Loja de Tintas

Em uma loja de tintas. O programa deverá pedir o tamanho em metros quadrados da área a ser pintada. Considere que a cobertura da tinta é de 1 litro para cada 6 metros quadrados e que a tinta é vendida em latas de 18 litros, que custam R\\$ 80,00 ou em galões de 3,6 litros, que custam R\\$ 25,00.

# Descobrir quantas latas de tinta e qual o custo para pintar uma área
    # Descobrir quantas latas de tinta
        # Descobrir qual a área que o usuário vai pintar
area = int(input("Escreva qual a área a ser pintada (m²):"))
        # Quantos litros de tinta vou precisar para essa área
litros = area / 6
        # Quantas latas eu preciso para chegar nessa quatnidade de tinta
latas = litros / 18
# 1.3
# Se a parte inteira do numero de latas for menor do que o numero de latas
    # eu preciso de mais 1 lata
if latas > int(latas):
    latas = int(latas) + 1
    
    # Calcular o custo das latas de tinta
        # Quantidade de latas * preço da lata
custo = latas * 80

print("Latas", latas)
print("Custo", custo)


##### Informe ao usuário as quantidades de tinta a serem compradas e os respectivos preços em 3 situações.

Dica: lembre dos operadores // e % mostrados em exercícios anteriores<br>
Dica1: numero // 10 vai te dar como resposta a parte inteira da divisão do número por 10. Ex: 7 // 3 = 2; 10 // 3 = 3<br> 
Dica2: numero % 10 vai te dar o resto da divisão do número por 10. Ex: 7 % 3 = 1; 10 % 3 = 1; 15 % 3 = 0

##### 1. Comprar apenas latas de 18 litros: (apenas latas inteiras)


def area_a_ser_pintada():
    area = int(input("Escreva qual a área a ser pintada (m²):"))
    return area

def calcular_litros_tinta(area):
    litros = area / 6
    return litros
    
def calcular_latas_tinta(litros):
    latas = litros / 18
    if latas > int(latas):
        latas = int(latas) + 1
    return latas

def calcular_custo(latas):
    custo = latas * 80
    return custo

area = area_a_ser_pintada()
litros = calcular_litros_tinta(area)
latas = calcular_latas_tinta(litros)
custo = calcular_custo(latas)
print("Latas", latas)
print("Custo", custo)

##### 2. Comprar apenas galões de 3,6 litros: (apenas galoes inteiros)

def area_a_ser_pintada():
    area = int(input("Escreva qual a área a ser pintada (m²):"))
    return area

def calcular_litros_tinta(area):
    litros = area / 6
    return litros
    
def calcular_latas_tinta(litros):
    latas = litros / 3.6
    if latas > int(latas):
        latas = int(latas) + 1
    return latas

def calcular_custo(latas):
    custo = latas * 25
    return custo

area = area_a_ser_pintada()
litros = calcular_litros_tinta(area)
latas = calcular_latas_tinta(litros)
custo = calcular_custo(latas)
print("Galões", latas)
print("Custo", custo)



##### 3. Misturar latas e galões, de forma que o desperdício de tinta seja menor. Sempre arredonde os valores para cima, isto é, considere latas cheias.

O custo da lata é 80/18 = 4,44 R\\$/L

O custo do galão é 25/3,6 = 6,94 R\\$/L

A lata é mais econômica, então todas as latas inteiras que pudermos usar devemos comprar em latas. Se ficar faltando alguma coisa para completar devemos avaliar se é melhor comprar latas ou galões. Exemplo:

Se queremos comprar 90 litros. 5 latas dão exatamente 90 litros. Então devemos comprar tudo em latas.

Se queremos comprar 95 litros. 5 latas dão exatamente 90 litros. Então devemos comprar pelo menos 5 latas e avaliar o que falta, se estes últimos 5 litros valem mais apenas em latas ou galões.

Para os 5 litros faltantes precisamos de 2 galões que custam 50 reais no total. Ou de uma lata que custa 80 reais no total. Portanto, neste caso vale mais a pena usar 2 galões.

Se queremos comprar 107 litros. 5 latas dão exatamente 90 litros. Então devemos comprar pelo menos 5 latas e avaliar o que falta, se estes últimos 5 litros valem mais apenas em latas ou galões.

Para os 17 litros faltantes precisamos de 5 galões que custam 125 reais no total. Ou de uma lata que custa 80 reais no total. Portanto, neste caso vale mais a pena usar uma lata.

3 galões custam 75 reais, 4 galões custam 100 reais. Então, se for possível completar com até 3 galões escolhe-se galões. Qualquer quantidade maior que 3 galões, usa-se latas.

Podemos ir ao exercício:

# Pegar a área a ser pintada
def area_a_ser_pintada():
    area = int(input("Escreva qual a área a ser pintada (m²):"))
    return area

# Pegar quantos litros eu vou precisar de tinta
def calcular_litros_tinta(area):
    litros = area / 6
    return litros

# Calcular quantas latas e quantos galões eu vou precisar
    # Calcular quantas latas inteiras eu vou precisar
    # Calcular quantos litros ainda faltam comprar
    # Calcular quanto custa preencher esses litros que faltam com galao
    # Calcular quanto custa preencher esses litros que faltam com latas
    # Escolher a opção mais barata
def calcular_qtde_latas_galoes(litros):
    latas = 0
    galoes = 0

    latas_inteiras = int(litros / 18)

    litros_faltam = litros % 18
    # se for preencher com latas
    custo_extra_latas = 1 * 80

    # se for preencher com galoes
    galoes = litros_faltam / 3.6 # 2
    if galoes > int(galoes):
        galoes = int(galoes) + 1
    custo_extra_galoes = galoes * 25

    if custo_extra_latas < custo_extra_galoes:
        latas = latas_inteiras + 1
        galoes = 0
    else:
        latas = latas_inteiras
    return latas, galoes

# Calcular o custo total
def calcular_custo(latas, galoes):
    custo_latas = latas * 80
    custo_galoes = galoes * 25
    custo = custo_latas + custo_galoes
    return custo
