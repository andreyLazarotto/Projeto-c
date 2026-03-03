#include <stdlib.h>
float calcularMedia(float n1, float n2, float n3) {
    return (n1 + n2 + n3) / 3.0;
}

int main() {
    char nome[100];
    int idade;
    float nota1, nota2, nota3, media;
    int numeros[5];
    int i, soma = 0, maior;

    printf("Digite seu nome: ");
    fgets(nome, sizeof(nome), stdin);

    do {
        printf("Digite sua idade (>= 0): ");
        scanf("%d", &idade);

        if (idade < 0) {
            printf("Idade inválida! Tente novamente.\n");
        }

    } while (idade < 0);

    printf("Digite a primeira nota: ");
    scanf("%f", &nota1);

    printf("Digite a segunda nota: ");
    scanf("%f", &nota2);

    printf("Digite a terceira nota: ");
    scanf("%f", &nota3);

    media = calcularMedia(nota1, nota2, nota3);

    printf("\nMedia: %.2f\n", media);

    if (media >= 7) {
        printf("Situacao: Aprovado\n");
    } else if (media >= 5) {
        printf("Situacao: Recuperacao\n");
    } else {
        printf("Situacao: Reprovado\n");
    }

    printf("\nDigite 5 numeros inteiros:\n");

    for (i = 0; i < 5; i++) {
        printf("Numero %d: ", i + 1);
        scanf("%d", &numeros[i]);
        soma += numeros[i];
    }

    maior = numeros[0];

    for (i = 1; i < 5; i++) {
        if (numeros[i] > maior) {
            maior = numeros[i];
        }
    }

    printf("\nSoma dos numeros: %d\n", soma);
    printf("Maior numero: %d\n", maior);

    return 0;
}

