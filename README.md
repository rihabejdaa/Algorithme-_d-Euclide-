#include <stdio.h>
int main() {
    int a, b, c;
    int x1, y1, x2, y2;
    int q, r, tempX, tempY;
    int d, x, y;
    double x_p, y_p, alpha, beta;

    /* Lecture des valeurs*/
    printf("Entrez les valeurs de deux nombres liés aux inconnus de votre équation a, b et la valeur du troisième nombre de l'équation c : ");
    scanf("%d %d %d", &a, &b, &c);

    /*Initialisation*/
    x1 = 1; y1 = 0;
    x2 = 0; y2 = 1;

    /* Sauvegarde des valeurs initiales pour éviter leur perte */
    int a0 = a, b0 = b;
    printf("Les étapes de calculs :");
    /*Algorithme d'Euclide étendu*/
    while (b != 0) {
        q = a / b;
        r = a % b;

        tempX = x1;
        tempY = y1;
    printf("\n a=%d,
    b=%d,r=%d",a,b,r);
        x1 = x2;
        y1 = y2;

        x2 = tempX - q * x2;
        y2 = tempY - q * y2;
    printf("\n x=%d,y=%d",x1,y1);
        a = b;
        b = r;
    }

    /* Résultats du PGCD et  les coefficients de Bézout*/
    d = a;
    x = x1;
    y = y1;

    printf("\nPGCD = %d\n", d);
    if (d==1){
    printf("votre deux nombres sont premiers entre eux");}
    else{
    printf("votre deux nombres ne sont pas premiers entre eux");
    }
    printf("\n Coefficients : x = %d , y = %d\n", x, y);

    /* Vérification de l'existence de solution entière*/
    if (c % d != 0) {
        printf("Pas de solution entière : d ne divise pas c\n");
    } else {
  printf("Il existe des solutions entières\n");

        /*La solution particulière*/
        x_p = x * (c / (double)d);
        y_p = y * (c / (double)d);
        printf("Solution particulière : (x_p, y_p) = (%.2f , %.2f)\n", x_p, y_p);

        /* La solution générale */
        alpha = (double)b0 / d;
        beta = -(double)a0 / d;
        printf("Solution générale :(x = %.2f + k*%.2f , y = %.2f + k*%.2f\n)", x_p, alpha, y_p, beta);
    }

    return 0;
}
