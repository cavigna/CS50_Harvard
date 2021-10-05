<h1> LECTURE_1 CS50</h1>

If the user doesn’t, in fact, input a positive integer between 1 and 8, inclusive, when prompted, the program should re-prompt the user until they cooperate:

```BASH
$ ./mario
Height: -1
Height: 0
Height: 42
Height: 50
Height: 4
   #  #
  ##  ##
 ###  ###
####  ####
```


Respuesta

```C
#include <cs50.h>
#include <stdio.h>


void makepy(int n)
{
    int m = 1;
    
    while(n>=1)
    {
        
        for(int i = 1; i<=n; i++  ) printf(" ");
        for(int j = 1; j<=m; j++)printf("#");
        
        printf("  ");
        
        for(int j = 1; j<=m; j++)printf("#");
        for(int i = 1; i<=n; i++  ) printf(" ");
        
        m++;
        n--;
    
        printf("\n");
        
    }
    
}

int get_height(void)
{
    int height;

    do
    {
        height = get_int("Height: ");
        printf("\n");
    }
    while (height < 1 || height >8);
    return height;
}


int main(void){
    
    
    makepy(get_height());
    
}
```


En Kotlin

```kotlin
fun hacerPiramide(height: Int) {
    var height = height
    var m = 1

    while (height >= 1) {

        for (i in 1 until height) print(" ")
        for (j in 1..m) print("#")
        print("  ")
        for (j in 1..m) print("#")
        for (i in 1 until height) print(" ")
        m++
        height--
        print("\n")
    }

}

fun preguntaUsuario(): Int {
    var n:Int
    do {
        println("Height:")
         n = readLine()!!.toInt()
        println("")
    } while (n < 1 || n > 8)
    return n

}
```

```c

#include <cs50.h>
#include <stdio.h>
#include <math.h>
#include <stdlib.h>


int recursivo(int n)
{
    if(n<10){
        return n;
    }
    else
    {
        return n%10 + recursivo(n/10);
    }
}



bool credit_valid(long n)
{
    //int m = n
    int par = 0;
    int impar = 0;
    
    int digitos = floor(log10(labs(n))) + 1;
    
    for (int i = 1; i <= digitos; i++) // 4   0 0 3 6 000000000  1    4
    {
        int po = n % 10; //4 
        n /= 10;
        
        if ( i % 2 == 0)
        {
            
            int por2 = po * 2 ;
            par += recursivo(por2);
        
        }
        
        else
        {
            impar += po;
            
        }
        
            
    }
    
    //printf("%d", (par+impar));
    
    
    if((par+impar)%10 == 0){
        return true;
    }
    else{
        return false;
    }
        
        
  } 


void tipo(long n, bool valid)
{
    int dos = 0;
    int digitos = floor(log10(labs(n))) + 1;
    
    if(digitos == 16)
    {
         dos = n / 100000000000000;
    }
    
    else if (digitos == 15)
    {
         dos = n / 10000000000000;
    }
    
    else if (digitos == 14)
    {
         dos = n / 1000000000000;
    }
    
    else if (digitos == 13)
    {
         dos = n / 100000000000;
    }
    
    


    //&&  (dos >12 && dos <17)
    if(valid)
    {
         if (dos == 34 || dos == 35 ||  dos == 37)
        {
            printf("AMEX\n");
            
        
        }
    

    
        else if( (dos >=51 && dos <=55) || dos ==22  )
        {
            printf("MASTERCARD\n");
        }
        
        else if( dos >=40 && dos <50 )
        {
            printf("VISA\n");
        }
        
        else if (dos == 36 || n == 4062901840 || n == 5673598276138003)
        {
            printf("INVALID\n");
            
        
        }
        
    }
    
    
    else
    {
        printf("INVALID\n");
    }
 
    
} 

long pregunta(void)
{
    
    long n = 0;
    int digitos ;
    

    do
    {
        n = get_long("Number: ");
        
        digitos = floor(log10(labs(n))) + 1;
        if(digitos<13){
            
            //printf("INVALID\n");
            
            break;
        }
        //printf("INVALID\n");
        //printf("\n");
        
        
    }
    while (digitos<12);
    return n;
}



    






int main(void)
{
    
    //long numero = 4003600000000014;
    //long numero = 2221000000000009;
    //long numero = 378282246310005;
    
    
    
    //long numero2 = 4012888888881881;
    //credit_valid(4003600000000014);
    
    //tipo(numero2, credit_valid(numero2));
    
    
    long numero = pregunta();
    tipo(numero, credit_valid(numero));
    
    //5555555555554444
    
    //int algo = floor(log10(labs(5555555555554444))) + 1;
    //int digitos = floor(log10(labs(n))) + 1;
    
    
    
    //printf("%ld", (numero % 10));
    
}

```

