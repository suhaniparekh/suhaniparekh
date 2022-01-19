#include<stdio.h>
#include<conio.h>
#include<stdlib.h>
#include<string.h>
struct library{
   char bookname[50];
   char author[30];
   char genre[50];
   float price;
};
int main(){
   struct library lib[100];
   char bookname[30];
   char series[10];
   int i,j,days,x,fine,seriesno, keepcount;
   i=j=keepcount = 0;
   while(j!=6){
      printf("\n1. Add book information\n");
      printf("2. Display book information\n");
      printf("3. Number of books in the library\n");
      printf("4. Amount of fine to be paid\n");
      printf("5. Exit the program");
      printf ("\n\nEnter one of the number mentioned above: ");
      scanf("%d",&j);
      switch (j){
         /* Add book */
         case 1:
            printf ("Enter book name = \n");
            scanf ("%s",lib[i].bookname);
            printf ("Enter author name = \n");
            scanf ("%s",lib[i].author);
            printf ("Enter genre = \n");
            scanf ("%s",lib[i].genre);
            printf ("Enter price = \n");
            scanf ("%f",&lib[i].price);
            printf("Is your book a series?\n");
            scanf("%s",series);
            keepcount++;
            i++;
            break;
         case 2:
            printf("You have entered the following information\n");
            for(i=0; i<keepcount; i++){
               printf ("Name of the book : %s\n",lib[i].bookname);
               printf ("\t Author : %s\n",lib[i].author);
               printf ("\t Genre : %s\n",lib[i].genre);
               printf ("\t Price : %.2f Rs\n",lib[i].price);
               if (strcmp(series,"yes")==0){
                printf("How many books does your series have? ");
                scanf("%d", &seriesno);
                printf("How many books does your series have?  %d \n", seriesno);
                if (seriesno==2){
                    printf("Your book is a Sequal");
                }
                else if (seriesno==3){
                    printf("Your book is a Trilogy");
                }
                else if (seriesno==4){
                    printf("Your book is a Tetralogy");
                }
                else{
                    printf("Your book is a Series itself");
                }
            }
            else{
                printf("Your book is not a series");
            }
            }
            break;
         case 3:
            printf("\n Number of books in the library: %d", keepcount);
            break;
         case 4:
            printf("\n How many days has it been since you issued the book? ");
            scanf("%d", &days);
            printf("\n How many days has it been since you issued the book? %d\n", days);
            if (days>7){
                x=days-7;
                fine= x*2;
                printf("Amount of fine to be paid by you is: %d Rs", fine);
            }
            else{
                printf("No fine to be paid!");
            }
         case 5:
             exit(0);
      }  
      
   }
   return 0;
}
