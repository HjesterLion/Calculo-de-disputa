# Calculo-de-disputa
Trabalho feito para fazer calculos de disputas de arremeços e notas ,trabalho de faculdade

    #include <stdio.h>
    #include <stdlib.h>

    //chama a função
    float somanotas(float n1);
    //variavel global cont;
    float cont = 0;

    int main()
    {
        int escolha,contatl = 1,aux;
        float nota[5],arremeco[3],resultado[2],atlarremeco1[3],atlarremeco2[3],auxf;
        //Meno e escolha
        printf("Escolha 1 - arremesso, 2 - nota: ");
        scanf("%d", &escolha);
        if(escolha == 1)
        {

            for(int i = 0; i<2; i++)
            {
                printf("%d Atleta\n",i+1);

                //Entrada do arremeço
                for(int i=0; i<3; i++)
                {
                    printf("Digite o %d arremesso: ",i+1);
                    scanf("%f", &arremeco[i]);
                }

                //Ortagização
                for(int i = 0; i<3; i++)
                {
                    for(int x = i; x<3; x++)
                    {
                        if(arremeco[i]<arremeco[x])
                        {
                            auxf = arremeco[i];
                            arremeco[i] = arremeco[x];
                            arremeco[x] = auxf;
                        }
                    }
                }
                if(contatl == 1)
                {
                    //Copia um vetor em outro vetorHjesterLion/teste
                    for(int i = 0; i<3; i++)
                    {
                        atlarremeco1[i] = arremeco[i];
                        printf("%d arremesso foi de %.2f \n", i+1, atlarremeco1[i]);
                    }
                }
                //Copia um vetor em outro vetor
                if(contatl == 2)
                    for(int i = 0; i<3; i++)
                    {HjesterLion/teste
                        atlarremeco2[i] = arremeco[i];
                        printf("%d arremesso foi de %.2f \n", i+1, atlarremeco2[i]);
                    }
                contatl++;//Aumenta o contador em +1
            }
            //Comparação do arremeço para ver qual é o ganhador
            if(atlarremeco1[0] == atlarremeco2[0])
            {
                if(atlarremeco1[1]< atlarremeco2[1])
                    printf("o vencedor eh  atleta 2");
                if(atlarremeco2[1]< atlarremeco1[1])
                    printf("o vencedor eh atleta 1");
            }
            if(atlarremeco1[0] < atlarremeco2[0])
                printf("O atleta 2 ganhou");
            if(atlarremeco2[0] < atlarremeco1[0])
                printf("O alteta 1 ganhou");
        }
        //a escolha 2 é para as notas;
        if(escolha == 2)
        {
            for(int i = 0; i<2; i++)
            {
                //Entrada de notasHjesterLion/teste
                printf("Digite as notas do %d adversario", i+1);
                //digita as notas
                for(int i = 0; i< 5; i++)
                {
                    printf("\nDigite a nota %d: ",i+1);
                    scanf("%f", &nota[i]);
                }
                //ordena o vetor
                for(int i = 0; i<5; i++)
                {
                    for(int x = i; x<5; x++)
                    {
                        if(nota[i]>nota[x])
                        {
                            aux = nota[i];
                            nota[i] = nota[x];
                            nota[x] = aux;
                        }
                    }
                }
                //guarda o resultado em um vetor
                for(int x = 1; x<5; x++)
                    resultado[i] = somanotas(nota[x]);
                printf("resultado do %d eh %.2f\n",i+1,resultado[i]/4);
                cont = 0;
            }
            //imprime o resultado
            if(resultado[0] > resultado[1])
                printf("O atleta 1 ganhou");
            else
                printf("O atleta 2 ganhou");
        }
        return 0;

    }

    //Função para somar as notas
    float somanotas(float n1)
    {
        cont += n1;
        return (cont);
    }

