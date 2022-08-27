#include<stdio.h>
#include<windows.h>
#include<string.h>
#include<conio.h>

char ch='*';
struct timezoney
{
    char name[20];
    int hrvalue;
    int minvalue;
};


void zero(int x,int y);
void one(int x,int y);
void two(int x,int y);
void three(int x,int y);
void four(int x,int y);
void five(int x,int y);
void six(int x,int y);
void seven(int x,int y);
void eight(int x,int y);
void nine(int x,int y);
void colon(int x,int y);
void call(int digit,int x,int y);
void gotoxy(int x,int y);

int main()
{
int h=0,m=0,s=0;
char tmzn[20];
int gmthr;
int gmtmin;
int i;
struct timezoney t[15];
strcpy(t[0].name,"washingtondc");
t[0].hrvalue=-4;
t[0].minvalue=0;
strcpy(t[1].name,"london");
t[1].hrvalue=1;
t[1].minvalue=0;
strcpy(t[2].name,"kathmandu");
t[2].hrvalue=5;
t[2].minvalue=45;
strcpy(t[3].name,"delhi");
t[3].hrvalue=5;
t[3].minvalue=30;
strcpy(t[4].name,"lisbon");
t[4].hrvalue=1;
t[4].minvalue=0;
strcpy(t[5].name,"tokyo");
t[5].hrvalue=9;
t[5].minvalue=0;
strcpy(t[6].name,"bangkok");
t[6].hrvalue=7;
t[6].minvalue=0;
strcpy(t[7].name,"berlin");
t[7].hrvalue=2;
t[7].minvalue=0;
strcpy(t[8].name,"athens");
t[8].hrvalue=3;
t[8].minvalue=0;
strcpy(t[9].name,"beijing");
t[9].hrvalue=8;
t[9].minvalue=0;
strcpy(t[10].name,"sydney");
t[10].hrvalue=10;
t[10].minvalue=0;
strcpy(t[11].name,"mexico");
t[11].hrvalue=-6;
t[11].minvalue=0;
strcpy(t[12].name,"abudhabi");
t[12].hrvalue=4;
t[12].minvalue=0;




printf("\t\t\t***************************\n");
printf("\t\t\t*******DIGITAL_CLOCK*******\n");
printf("\t\t\t***************************\n");

printf("\t\t\tTeam members:\n\t\t\t\tPyush Kunwar (077BCE114)\n\t\t\t\tRana Sah (077BCE122)\n\t\t\t\tSamyog Bhattarai (077BCE139)\n\t\t\t\tSansar Sah (077BCE142)\n");
printf("\nPlease enter time in the format HH:MM:SS\n");
scanf("%d%d%d",&h,&m,&s);
printf("Please enter your timezone\n");
printf("(You can change timezone later by entering any key)");
scanf("%s",&tmzn);
for(i=0;i<=12;i++)
{
    int temp=strcmp(tmzn,t[i].name);
    if(temp==0)
    {
        break;
    }
}
/*gmthr=h-t[i].hrvalue;
gmtmin=m-t[i].minvalue;*/
goto st;
edit:
printf("Enter the time zone you want");

char tempn[20];
scanf("%s",&tempn);
int j;
for( j=0;j<=12;j++)
{
    int temp=strcmp(tempn,t[j].name);
    if(temp==0)
    {
        break;
    }
}
h=h+t[j].hrvalue-t[i].hrvalue;
m=m+t[j].minvalue-t[i].minvalue;
 printf("%s,GMT %d:%d",t[j].name,t[j].hrvalue,t[j].minvalue);
goto et;

 st:
printf("%s,GMT %d:%d",t[i].name,t[i].hrvalue,t[i].minvalue);

et:

    for(h;h<24;h++)
    {
        for(m;m<60;m++)
        {
            for(s;s<60;s++)
            {
            call(h/10,31,15);
            call(h%10,41,15);
            colon(48,15);
            call(m/10,55,15);
            call(m%10,65,15);
            colon(73,15);
            call(s/10,80,15);
            call(s%10,88,15);
            Sleep(890);
            if(kbhit()==0)
            {
                continue;
            }
            else
            {
                goto edit;
            }
            }
            s=0;
        }
        m=0;
    }
    h=0;
    goto st;
    end:



return 0;
}
void gotoxy(int x,int y)
{
    COORD c;
    c.X=x;
    c.Y=y;
    SetConsoleCursorPosition(GetStdHandle(STD_OUTPUT_HANDLE),c);
}
void call(digit,x,y)
{
switch(digit)
{
case 1: one(x,y); break;
case 2: two(x,y); break;
case 3: three(x,y); break;
case 4: four(x,y); break;
case 5: five(x,y); break;
case 6: six(x,y); break;
case 7: seven(x,y); break;
case 8: eight(x,y); break;
case 9: nine(x,y); break;
default: zero(x,y); break;
}
}
void zero(x,y)
{
for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==1 ||I==9 ||j==1 ||j==5)
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}
}

void one(x,y)
{for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
    gotoxy(x,y);
if(j==1)
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}
}

void two(x,y)
{
for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==1 || I==5 || I==9 || (I>5 & j==1 ) || (I<5 & j==5))
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}}
void three(x,y)
{for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==1 ||I==9 ||j==5 ||I==5)
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}
}

void four(x,y)
{for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==5 ||j==5 ||(I<6 &j==1))
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}}

void five(x,y)
{
for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==1 || I==5 || I==9 || (I<5 & j==1 ) || (I>5 & j==5))
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}}

void six(x,y)
{
for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==1 || I==5 || I==9 || j==1  || (I>5 & j==5))
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}}

void seven(x,y)
{
for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==1 || j==5 )
{
printf("%c",ch);
}
else{
printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}}

void eight(x,y)
{


for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==1 ||I==9 ||j==1 ||j==5 || I==5)
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}
}

void nine(int x,int y)
{
for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if(I==1 || I==5 || I==9 || j==5|| (I<5 & j==1))
{printf("%c",ch);}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}
}

void colon(x,y)
{
for(int I=1;I<=9;I++)
{
for(int j=1;j<=5;j++)
{
gotoxy(x,y);
if((I==3 &j==3 )||(I==7 &j==3))
{printf("*");}
else
{printf(" ");}
x++;
}
y++;
x=x-5;
printf("\n");
}
}
