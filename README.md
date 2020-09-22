<div align="center">

## Non\-negative integer Multiplication of ANY LENGTH\!\!


</div>

### Description

Please rate me if it worked for you.It is an extremely efficient Non-Negative INTEGER MULTIPLICATION of ANY LENGTH!!I assure you it is very quick..Any CS student may need it.It is my first Submission.
 
### More Info
 


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Adnan Faisal](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/adnan-faisal.md)
**Level**          |Intermediate
**User Rating**    |5.0 (10 globes from 2 users)
**Compatibility**  |C, C\+\+ \(general\), Borland C\+\+, UNIX C\+\+
**Category**       |[Math](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/math__3-12.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/adnan-faisal-non-negative-integer-multiplication-of-any-length__3-3786/archive/master.zip)





### Source Code

```
//Char to Char MUL
//WORKS 100% :)
// No Strrev!!
//20-4-2002
/*It is an extremely efficient Non-Negative
INTEGER MULTIPLICATION of ANY LENGTH!!
I assure you it is very quick..Any CS student may need it.
Increse L in order to increase the input length.
 (Default L=50) */
#include<stdio.h>
#include<string.h>
#include<stdlib.h>
#define L 500
#define START 5
char mul[2*L];
long totallen=0;
long Multiply(char a[],char b[],long len1,long len2)
{
 long i,j,k=START,m;
 int temp ;
 m=START;     //len1+len2
// mul = (char *) malloc((2*L+5)*sizeof(char));
 for(i=0;i<=len1+len2+5;i++)
 mul[i]=0;
 for(i=len1-1;i>=START;i--)
 {
  for(j=len2-1;j>=START;j--)
  {
  temp = mul[k] + (a[i]-48) * (b[j]-48) ;
  mul[k] = temp % 10 ;
  mul[k+1] = mul[k+1] +temp /10;
  k++;
  }
  m++;
  k=m;
 }
// mul[k]='\n';
 return m; //no. of digits in resultant
}
void print(long k)
{
 long i;
// finding starting position from last
 for(i=totallen;i>=START;i--)
 { if ( mul[i]>=1 && mul[i]<=9) break;}
 k = i;
 //printing
 for(i=k;i>=START;i--)
  printf("%d",mul[i]);
 printf("\n");
}
void main()
{
 char a[L],b[L];
 char c;
 long i=START,len1,len2,x=0,k,j=START;
 // freopen("prod.txt","r",stdin);
 //a = (char *) malloc (L*sizeof(char));
 //b = (char *) malloc (L*sizeof(char));
 strcpy(a,"");
 strcpy(b,"");
 strcpy(mul,"");
 while(scanf("%c",&c)==1)
  {
  if(x==0)
	if(c!='\n' && c!=' ')
	 { a[i++] = c; continue; }
	else { x=1; a[i]='\n'; len1 = i ;continue;}
  if(x==1)
	 if(c!='\n' && c!=' ')
	  {b[j++] = c; continue; }
	 else { x = 0 ; b[j]='\n'; len2 = j; }
	totallen = len1+len2;
	if(a[START]=='0' || b[START]=='0')
	  { printf("0\n"); goto end;}
	 k = Multiply(a,b,len1,len2);
	 //no use of this k
	 print(k+START);
end:
  strcpy(a,"");
  strcpy(b,"");
  strcpy(mul,"");
  //a = (char *) malloc (L*sizeof(char));
  //b = (char *) malloc (L*sizeof(char));
  x=0;
  i =j = START;
  }//end of while
}
```

