#sudoku

#Preencha um tabuleiro 9x9 com os números de 1 a 9 de forma que nenhuma linha, coluna ou quadrante tenha o mesmo número duas vezes

from multiprocessing.resource_sharer import stop
from pickle import APPEND
import random
#from readline import append_history_file


board = [
    ['0', '0', '0', '0', '0', '0', '0', '0', '0'],
    ['0', '0', '0', '0', '0', '0', '0', '0', '0'],
    ['0', '0', '0', '0', '0', '0', '0', '0', '0'],
    ['0', '0', '0', '0', '0', '0', '0', '0', '0'],
    ['0', '0', '0', '0', '0', '0', '0', '0', '0'],
    ['0', '0', '0', '0', '0', '0', '0', '0', '0'],
    ['0', '0', '0', '0', '0', '0', '0', '0', '0'],
    ['0', '0', '0', '0', '0', '0', '0', '0', '0'],
    ['0', '0', '0', '0', '0', '0', '0', '0', '0']
]

def print_sudoku(sudoku):
    line = '   '.join(['–'] * 13)
    str_sudoku_list = [line]
    for i in range(0, len(sudoku), 3):
        group = sudoku[i:i+3]
        str_group_list = []
        for row in group:
            str_row_list = []
            for k in range(0, len(sudoku[0]), 3):
                str_row_list.append('   '.join(row[k:k+3]))
            str_group_list.append('|   ' + '   |   '.join(str_row_list) + '   |')
        str_sudoku_list.append('\n'.join(str_group_list))
        str_sudoku_list.append(line) 
    return '\n'.join(str_sudoku_list)

print(print_sudoku(board))

#validação

def valid(bo, num, pos):
    # Check row
    for i in range(len(bo[0])):
        if bo[pos[0]][i] == num and pos[1] != i:
            return False

    # Check column
    for i in range(len(bo)):
        if bo[i][pos[1]] == num and pos[0] != i:
            return False

    # Check box
    box_x = pos[1] // 3
    box_y = pos[0] // 3

    for i in range(box_y*3, box_y*3 + 3):
        for j in range(box_x * 3, box_x*3 + 3):
            if bo[i][j] == num and (i,j) != pos:
                return False

#Verificando se há ganhador

valor =['']

def posicao (board, soluções):
    if valor ==0:
        print(print_sudoku(board))
    else:
        print("Você completou o tabuleiro!!")    
    return (print_sudoku(board))
    
#Sorteio das casas do tabuleiro

import random

while random < 40:
    
    if random < 40:
        print(random.randint(1,9))

    for i in range(len(bo[y][x]))== valid:
        print(bo)    

else:
    continue
