# algo_solve_problems_tp
![Background](https://user-images.githubusercontent.com/127783044/229522997-014b253a-fae6-4016-b7a3-7e2192e0f5a1.png)

## contents

* [**travaile 3**](#travaile-3)
   * [ 1-tri par bulles](#tri-par-bulles)
   * [2-tri par selection](#tri-par-selection)
    * [3-tri par insertion](#tri-par-insertion)
 * [**travail 4**](#travaile-4)
    * [exercice 1](#exercice-1)
    * [exercice 3](#exercice-3)
    * [exercice 4](#exercice-4)
         * [**4.1**](#ex4-1)
    * [exercice 5](#exercice-5)
         * [**5.1**](#ex5-1)
         * [**5.2**](#ex5-2)
* [**travail 5**](#travaile-5)	 
    * [exercice 1](#exo1)
         * [**exo1 a**](#exo1-a)
	  * [**exo1 b**](#exo1-b)
	  * [**exo1 c**](#exo1-c)
    * [exercice 2](#exo2) 
          
	  * [**exo2 b**](#exo2-b)
	   
* [**the solutions from the PDF file**](#the-solutions-from-the-pdf) 
 
 
 
 ## travaile 3

 ### [⬆ **Back to top**](#contents)
 ### tri par bulles


 ```c
 #include <stdio.h>
void descendent1(int tab[]){
    int x,i,j,a;
   printf("veuiez entrer la taille de tablaux choisis ");
    scanf("%d",&x);
     for(i=0;i<x-1;i++){
    for(j=0;j<x-1;j++){
      if(tab[j]<tab[j+1]){
          a=tab[j];
          tab[j]=tab[j+1];
          tab[j+1]=a;
      }}}
     for(i=0;i<x;i++){
       printf("t1[%d]=%d \n",i,tab[i]);
}
}
int main() {
   int t1[100];
   int x,i;
   printf("veuiez entrer la taille de tablaux choisis ");
    scanf("%d",&x);
   for(i=0;i<x;i++){
       printf("enter lelement %d",i+1);
       scanf("%d",&t1[i]);
   }
    for(i=0;i<x;i++){
       printf("t1[%d]=%d \n",i,t1[i]);
   }
   descendent1(t1);
    return 0;
}

```
### [⬆ **Back to top**](#contents)

### tri par selection


```c
#include <stdio.h>
void descendent2(int tab[]){
    int x,i,j,aide,t,min;
   printf("veuiez entrer la taille de tablaux choisis ");
    scanf("%d",&x);
     for(i=0;i<x-1;i++){
         min=tab[i];t=i;
    for(j=i+1;j<x;j++){
      if(min<tab[j]){
          min=tab[j];
          t=j;
      }}
         aide=tab[t];
         tab[t]=tab[i];
         tab[i]=aide;
     }
     for(i=0;i<x;i++){
       printf("t1[%d]=%d \n",i,tab[i]);
}
}
int main() {
   int t1[100];
   int x,i;
   printf("veuiez entrer la taille de tablaux choisis ");
    scanf("%d",&x);
   for(i=0;i<x;i++){
       printf("enter lelement %d",i+1);
       scanf("%d",&t1[i]);
   }
    for(i=0;i<x;i++){
       printf("t1[%d]=%d \n",i,t1[i]);
   }
   descendent2(t1);
    return 0;
}

```
### [⬆ **Back to top**](#contents)

### tri par insertion


```c
#include <stdio.h>
void descendent3(int tab[]){
    int x,i,j,a;
   printf("veuiez entrer la taille de tablaux choisis ");
    scanf("%d",&x);
     for(i=1;i<x;i++){
      a=tab[i];
      j=i;
      while(j>0 && tab[j-1]<a){
      	tab[j]=tab[j-1];
      	j=j-1;}
	  tab[j]=a;}
     for(i=0;i<x;i++){
       printf("t1[%d]=%d \n",i,tab[i]);
}}
int main() {
   int t1[100];
   int x,i;
   printf("veuiez entrer la taille de tablaux choisis ");
    scanf("%d",&x);
   for(i=0;i<x;i++){
       printf("enter lelement %d",i+1);
       scanf("%d",&t1[i]);
   }
    for(i=0;i<x;i++){
       printf("t1[%d]=%d \n",i,t1[i]);
   }
   descendent3(t1);
    return 0;}


```

## travaile 4

### [⬆ **Back to top**](#contents)

### exercice 1

**ecrire un programme permettant de suprimer toutes les valeures nulles dans un vecteur** 

```c
#include <stdio.h>
int main() {
  int tab[100];
  int x,i,j;
  printf("veuiez entrer la taille de tablaux choisis ");
   scanf("%d",&x);
  for(i=0;i<x;i++){
      printf("enter lelement %d",i+1);
      scanf("%d",&tab[i]);
  }
  j=0;
    for(i=0;i<x;i++){
     if(tab[i]!=0){
         tab[j]=tab[i];
         j++;
     }}
    for(i=0;i<j;i++){
      printf("tab[%d]=%d \n",i,tab[i]);
  }
   return 0;
}

```

### [⬆ **Back to top**](#contents)

### exercice 3

**ecrire un programme permettant de aficher les nombre parfait dans une matrice** 

```c
#include <stdio.h>
int main() {
  int tab[100][100];
  int x,y,i,j,n,t;
  printf("veuiez entrer la taille de ligne tablaux choisis ");
   scanf("%d",&x);
   printf("veuiez entrer la taille de colone tablaux choisis ");
   scanf("%d",&y);
  for(i=0;i<x;i++){
       for(j=0;j<y;j++){
      printf("enter lelement %d %d",i+1,j+1);
      scanf("%d",&tab[i][j]);
  }}
  printf("les nombre parfait dans la matrice est ");
  for(i=0;i<x;i++){
       for(j=0;j<y;j++){
     n=0;
     for(t=1;t<=(tab[i][j]/2);t++){
         if(tab[i][j]%t==0){
             n=n+t;
         } }
         if(n==tab[i][j]){
             printf(" %d \n",tab[i][j]);
         }
         
  }}
   return 0;
}
```

### [⬆ **Back to top**](#contents)

### exercice 4
#### ex4 1

**4.1 :ecrire une fonction premier permettant de determiner  les nombre  premier dans un vecteur** 

```c
#include <stdio.h>
void premier(int tab[],int m) {
    int i, j, a;
    for (i=0;i<m;i++) {
        a=1;
    for (j=2; j<tab[i];j++) {
        if (tab[i]%j==0) {
          a=0;
          break;
            } }
        if (a==1 &&tab[i]>= 2) {
            printf("%d ",tab[i]);}}
}
    int main() {
  int tab[100];
  int x,i,j;
  printf("veuiez entrer la taille de tablaux choisis ");
   scanf("%d",&x);
  for(i=0;i<x;i++){
      printf("enter lelement %d",i+1);
      scanf("%d",&tab[i]);
  }
    for(i=0;i<j;i++){
      printf("tab[%d]=%d \n",i,tab[i]);
  }
  premier(tab , x);
   return 0;
}

```

### [⬆ **Back to top**](#contents)

#### ex4 2

**ecrire une fonction semi_premier permettant de determiner  les nombre semi premier dans un vecteur** 

```c

```
### [⬆ **Back to top**](#contents)

### exercice 5
#### ex5 1

**ecrire un programme  permettant de determiner  si un mot es palindromme** 

```c
#include <stdio.h>
#include <string.h>
int polindrome(char nom[]){
   int x,i,j;
   x=strlen(nom);
for(i=0,j=x-1;i<j;i++,j--){
    if(nom[i]!=nom[j]){
        return 0;
    }
}
return 1;
}
int main() {
  char nom[100];
  printf("veuiez entrer le mot ");
   scanf("%s",&nom);
  if(polindrome(nom)==1){
      printf("le mots est polindromme ");
  }else {
    printf("le mots n'est pas polindromme ");
  }
   return 0;
}
```
### [⬆ **Back to top**](#contents)

#### ex5 2

**ecrire un programme  permettant de determiner  si un mot es anagramme** 

```c
#include <stdio.h>
    #include <string.h>
    void tri(char mot[]) {
        int i,j;
        int  x=strlen(mot);
        char aide;
        for(i=0;i<x-1;i++) {
            for(j=i+1;j<x;j++) {
                if(mot[i]>mot[j]) {
                    aide=mot[i];
                    mot[i]=mot[j];
                    mot[j]=aide;
                }}} }
    int anagramme(char mot1[], char mot2[]) {
        int i;
        if(strlen(mot1) != strlen(mot2)) {
            return 0;
        }
        //pour trier les letrre des mot
        tri(mot1);
        tri(mot2);
        for(i=0;i<strlen(mot1);i++) {
            if(mot1[i] == mot2[i]) {
                return 1;
            }
        }
        return 0;
    }
    
    int main() {
        char mot1[100];
        char mot2[100];
        printf("veuiller entrer un  mot  ");
        scanf("%s", mot1);
        printf("veuillez entrer un autre mot  ");
        scanf("%s", mot2);

     if(anagramme(mot1, mot2)==1) {
        printf("les  mots sont  anagrammes ");
     } else {
        printf("les  mots ne sont pas anagrammes  ");
     }
        return 0;
}

```
### [⬆ **Back to top**](#contents)
## travaile 5

 ### exo1
  **Définir un type TEMP qui contient les champs heure,minute,seconde.**
   
  #### exo1 a
  
   **Ecrire une fonction/procédure qui transforme un temps T de type TEMP en un entier**
   
  ```c
  #include <stdio.h>
typedef struct {
int heure;
int min ;
int s ;
}TEMP;
void temp (TEMP a){
    int s;
    s=(a.heure)*3600+(a.min)*60+(a.s);
    printf("le temp expriment en second est %d",s);
}
int main (){
    TEMP x;
    printf("enter the heure ");
    scanf("%d",&x.heure);
    printf("enter the min ");
    scanf("%d",&x.min);
    printf("enter the secand ");
    scanf("%d",&x.s);
    temp(x);
    return 0;
}

  ```
  ### [⬆ **Back to top**](#contents)
   #### exo1 b
  
   **Ecrire une fonction/procédure qui décompose un temps exprimé en secondes en un
temps de types TEMP.**
   
  ```c
  #include <stdio.h>
typedef struct {
int heure;
int min ;
int s ;
}TEMP;
void temp (int a){
    int s;
     TEMP x;
     x.heure=a/3600;
     a=a%3600;
     x.min=a/60;
     a=a%60;
     x.s=a;
     printf("le temp est %d h %d min %d s " ,x.heure,x.min,x.s);
}
int main (){
    int a;
    printf("enter le temp en second ");
    scanf("%d",&a);
    
    temp(a);
    return 0;
}

  ```
 ### [⬆ **Back to top**](#contents)
   #### exo1 c
  
   **Ecrire une fonction/procédure qui fait la somme de deux durée T1 et T2 de types
TEMP.**
   
  ```c
  #include <stdio.h>
typedef struct {
int heure;
int min ;
int s ;
}TEMP;
void temp (TEMP x,TEMP y){
     TEMP a;
     a.s=x.s+y.s;
     a.min=x.min+y.min+(a.s/60);
     a.s =a.s % 60;
     a.heure=x.heure+y.heure+(a.min/60);
     a.min =a.min % 60;
  printf("la somme des temp est %d h %d min %d s " ,a.heure,a.min,a.s);
}

int main (){
    TEMP x;
    TEMP y;
     printf("Entrez la premiere duree h/min/s : ");
    scanf("%d %d %d", &x.heure, &x.min, &x.s);
 printf("Entrez la deusiemme duree h/min/s ");
    scanf("%d %d %d", &y.heure, &y.min, &y.s);

    temp(x,y);
    return 0;
}

  ```
### [⬆ **Back to top**](#contents)

### exo2
  **Définir un type TEMP qui contient les champs heure,minute,seconde.**
   
  #### exo2 b
  
   **Ecrire une fonction/procédure qui détermine la différence en nombre de jours entre
deux dates.**
   
  ```c
  #include <stdio.h>
typedef struct {
int jj;
int mm ;
int aa ;
}DATE;
void defirence (DATE x,DATE y){
     int a,b;
     a=x.jj+(x.mm)*30+(x.aa)*365;
     b=y.jj+(y.mm)*30+(y.aa)*365;
     if(a-b<0){
         printf("la difirence est %d",b-a);
     }else if(a-b==0){
         printf("les date sont les meme");
     }else{
         printf("la difirence est %d",a-b);
     }
}

int main (){
    DATE x;
    DATE y;
     printf("Entrez la premiere date jour/month/annee : ");
    scanf("%d %d %d", &x.jj, &x.mm, &x.aa);
 printf("Entrez la deusiemme date jour/month/annee ");
    scanf("%d %d %d", &y.jj, &y.mm, &y.aa);

    defirence(x,y);
    return 0;
}

  ```
  ### [⬆ **Back to top**](#contents)


## the solutions from the pdf

#### pdf de travail 3

[pdf file ](https://github.com/zem-litissia/algo_solve_problems_tp/files/11103366/algo_solve_pdf.pdf)


### [⬆ **Back to top**](#contents)
