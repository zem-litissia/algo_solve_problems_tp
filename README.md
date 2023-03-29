# algo_solve_problems_tp
![Background](https://user-images.githubusercontent.com/127783044/228566427-bd3aaa48-f15c-46d9-ac45-66a6a8343886.png)

## Contents:
* travail 3 
  * 1-tri par bulles :
   * 2-tri par selection
    * 3-tri par insertion
    
 * travail 4 
 
 
 
 
 ## travaile 3:
 ### 1-tri par bulles :

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
### 2-tri par selection :
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
### 3-tri par insertion :
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


