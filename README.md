#include <stdio.h>
#include <stdlib.h>
#include <time.h>

#define SIZE 6 // Tamanho do campo
#define BOMBS 3 // Número de bombas
#define MAX_ATTEMPTS 5 // Máximo de tentativas

// Função para inicializar o campo minado com espaços vazios
void inicializarCampo(char campo[SIZE][SIZE]) {
    for (int i = 0; i < SIZE; i++) {
        for (int j = 0; j < SIZE; j++) {
            campo[i][j] = ' ';
        }
    }
}

// Função para imprimir o campo minado
void imprimirCampo(char campo[SIZE][SIZE]) {
    printf("     A   B   C   D   E   F\n");
    for (int i = 0; i < SIZE; i++) {
        printf(" %d  ", i + 1);
        for (int j = 0; j < SIZE; j++) {
            printf("[%c] ", campo[i][j]);
        }
        printf("\n");
    }
}

// Função para gerar posições aleatórias das bombas
void gerarBombas(int bombas[BOMBS][2]) {
    srand(time(NULL));
    for (int i = 0;
Inicialização do campo: O campo é uma matriz de 6x6 inicializada com espaços vazios (' ').

Posicionamento das bombas: O código sorteia 3 posições aleatórias para alocar as bombas. Cada posição é única.

Jogadas do usuário: O usuário pode fazer até 5 jogadas, escolhendo posições no formato A1, B2, etc.

Verificação de bomba: Se o usuário escolher uma posição onde há uma bomba, ele perde e o jogo termina. Caso contrário, o local escolhido é marcado com 'O'.

Condição de vitória: Se o jogador fizer 5 jogadas sem acertar nenhuma bomba, ele vence.
