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



