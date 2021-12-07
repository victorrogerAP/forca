from random import choice
print('-='*30)
print('    JOGO DA FORCA  ')
print('-='*30)
palavras = ('vaca', 'cavalo', 'cachorro', 'mosquito', 'ornitorrinco')
print('Forca\n'
      'Tema: Animal')
palavra = choice(palavras)
quantidade = len(palavra)
letra_usada = list()
cont = 0
erro = 0
listas = list('_' * len(palavra))
print(listas)
num = 0
while cont <= quantidade + 6:
    letra = str(input('\nQual a letra? '))
    if letra in letra_usada:
        print('Letra já utilizada! digite outra letra')
        continue
    letra_usada.append(letra)
    cont += 1
    if letra.isnumeric():
        print('APENAS LETRA!')
    if len(letra) >= 2:
        print('ERRO DIGITE APENAS UMA LETRA')
    for c, v in enumerate(palavra):
        if v == letra:
            listas[c] = letra
            num += 1
    print(listas)
    if num == len(palavra):
        print(f'\n{listas}')
        print('Você ganhou')
        break
    if letra not in palavra:
        erro += 1
        if erro == 1:
            print('O')
        elif erro == 2:
            print('  O\n'
                  ' \\ \n')
        elif erro == 3:
            print('  O\n'
                  ' \\|\n')
        elif erro == 4:
            print('  O\n'
                  ' \\|/\n')
        elif erro == 5:
            print('  O\n'
                  ' \\|/\n'
                  ' /\n')
        elif erro == 6:
            print('  O\n'
                  ' \\|/\n'
                  ' / \\ \n')
    if erro == 6:
        print(f'VOCÊ PERDEU! a palavra era {palavra.upper()}')
        break
input('enter para sair')