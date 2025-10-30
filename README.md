#include<stdio.h>;
#include<stdbool.h>;
main() {
    int a,b,reste;/*On fait la saisie des nombres qu'on veut clculer PGCD*/
    printf("Entrez un nombre de votre choix: ");
    scanf("%d",&a);
    printf("Entrez un autre nombre: ");
    scanf("%d",&b);
    printf("\n Étapes de calcul\n");
    while (b!= 0)  {
        reste = a % b ;
        printf("a=%d,b=%d,reste=%d \n", a,b,reste);
        a=b;
        b=reste;
     }
    printf("Le pgcd est %d:",a);
    if (a==1) 
    printf("les deux nombres choisis sont premiers entre eux.")
    return 0;
}
