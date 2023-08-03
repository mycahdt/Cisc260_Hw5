#include <stdio.h>
#include <stdlib.h>
#include <math.h>




int multBooth(int a, int b);




void main() {


        int a, b, c;
    printf("Enter an integer:\n");
    scanf("%d", &a);
    printf("Enter an integer:\n");
    scanf("%d", &b);


    c = 0; // product, initialized as 0.


    // the code of your subroutine multBooth is called below  c = multBooth(a, b)
    c = multBooth(a,b);
    printf("the product = %d\n", c);
}


int multBooth(int a, int b){
    int product = 0;
    int bSubNegOne = 0;
    for(int i = 16; i>0; i--){


            int subZero = abs(b%2);
            //printf("sub0: %d\n", subZero);
            //printf("subNegOne: %d\n", bSubNegOne);


            if((subZero == 0) && bSubNegOne == 1) {
            product = product + a;
            //printf("01 case a: %d\n", a);
            //printf("01 case: %d\n", product);
        } else if ((subZero == 1) && bSubNegOne==0){
            product = product - a;
            //printf("10 case a: %d\n", a);
            //printf("10 case: %d\n", product);
        }
        bSubNegOne = abs(b%2);
        a = a<<1;
        b = b>>1;
    }
    return product;
}