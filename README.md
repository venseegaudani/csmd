#include<stdio.h>
#include<stdlib.h>
#include<time.h>
#define MA 16
#define ST 1
#define PD 2
#define FS 512
int main()
{
    srand(time(NULL));
    int att=0;
    int cd=0;
    while(!cd && att<MA)
    {
        int bt=(rand()%(1<<att))* ST;
        printf("Waiting for %d seconds...\n",bt+PD);
        sleep(bt+PD);
        if(rand()%2==0)
        {
            printf("Transmission Successful \n");
        }
        else{
            printf("Collision Detected \n");
            cd=1;
        }
        att++;
    }
    if(cd){
        printf("Maximum attempts reached Transmission Failed\n");
    }
    else{
        printf("Transmission Successful\n");
    }
    return 0;
}


