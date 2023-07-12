#include<AT89S8252.h>
#define DATA P0
#define DIG P2
#define BLANK 0x0F
const char code[11]={0xC0,0XF9,0xA4,0xB0,0X99,0x92,0X82,0XF8,0X80,0X90};
void wait(int);
void main()
{
int i,j;
while(1)
{
for(i=0;i<10;i++){
for( j=0;j<10;j++){
DATA =code[i];
DIG=~0X02;
DIG=BLANK;
DATA =code[j];
DIG=~0X01;
DIG=BLANK;
 wait(1);
}
}
}
}
void wait(int del)
{
 int i,j;
 for(i=0;i<del;i++)
 {
  for(j=0;j<20;j++)
  {}
 }
}
