#include <stdio.h>

int main() {
    int senha, senha1, opcao;
    float saldo = 500.00;
    float deposito, saque;
    float maiordeposito = 0.00;
    
	printf("\n\n--- AREA DE CADASTRO ---");
    printf("\nInsira uma senha numerica de 4 digitos: ");
    scanf("%d", &senha);

    while (senha < 1000 || senha > 9999) {
        printf("Senha invalida! Digite uma senha de 4 digitos: ");
        scanf("%d", &senha);
    }

    do {
        printf("\n----- BANCO LERO LERO -----\n");
        printf("1 - Depositar\n");
        printf("2 - Sacar\n");
        printf("3 - Consultar Saldo\n");
        printf("4 - Sair\n");
        printf("Escolha uma opcao: ");
        scanf("%d", &opcao);

        switch (opcao) {

            case 1:
            	printf("\n--- AREA DE DEPOSITO ---\n");
                printf("\nDigite o valor do deposito: R$ ");
                scanf("%f", &deposito);

                if (deposito <= 0) {
                    printf("Valor invalido!\n");
                } else {
                    saldo += deposito;

                    printf("Deposito realizado com sucesso!\n");

                    if (deposito > deposito1) {
                        deposito1 = deposito;
                    }
                }
                break;

            case 2:
            	printf("\n--- VERIFICACAO ---\n");
                printf("\nDigite sua senha: ");
                scanf("%d", &senha1);

                if (senha1 != senha) {
                    printf("Senha Incorreta! Operacao cancelada.\n");
                } else {
                	printf("\n--- AREA DE SAQUE ---\n");
                    printf("Digite o valor do saque: R$ ");
                    scanf("%f", &saque);

                    if (saque <= 0) {
                        printf("Valor invalido!\n");
                    } else if (saque > saldo) {
                        printf("Saldo Insuficiente!\n");
                    } else {
                        saldo -= saque;
                        printf("Saque realizado com sucesso!\n");
                    }
                }
                break;

            case 3:
                printf("\n----- EXTRATO -----\n");
                printf("Saldo atual: R$ %.2f\n", saldo);
                printf("Maior deposito: R$ %.2f\n", deposito1);
                break;

            case 4:
                printf("\nObrigado por usar nosso banco!\n");
                break;

            default:
                printf("\nOpcao invalida! Tente novamente.\n");
                break;
        }

    } while (opcao != 4);

    return 0;
}
