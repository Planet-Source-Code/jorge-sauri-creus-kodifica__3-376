<div align="center">

## Kodifica


</div>

### Description

This code encrypts any file u want using a bit complement.
 
### More Info
 
just wirte the input file and output file in command line.


<span>             |<span>
---                |---
**Submitted On**   |
**By**             |[Jorge Sauri Creus](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByAuthor/jorge-sauri-creus.md)
**Level**          |Beginner
**User Rating**    |4.0 (8 globes from 2 users)
**Compatibility**  |C
**Category**       |[Miscellaneous](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByCategory/miscellaneous__3-1.md)
**World**          |[C / C\+\+](https://github.com/Planet-Source-Code/PSCIndex/blob/master/ByWorld/c-c.md)
**Archive File**   |[](https://github.com/Planet-Source-Code/jorge-sauri-creus-kodifica__3-376/archive/master.zip)





### Source Code

```
// By: Jorge Sauri Creus
// Jsauri@sureste.com
#include <stdlib.h>
#include <stdio.h>
#include <conio.h>
void main(int argc, char *argv[])
  {
    unsigned char car, dump;
    FILE *in, *out;
    long int i, perc, cont;
    i=1;
    perc=1;
    cont=0;
    if ((argc<2) || (argc>3))
	{
	  printf(" Usage: CODIFICA <Input_File> [Output_File]\n\n");
	  printf(" Where:  <Input_File>= File to encrypt \n");
	  printf("      [Output_File] = Guess...(optional).\n");
	}
    if (argc==2) argv[2]=argv[1];
    if ((in = fopen(argv[1], "rt"))== NULL)
	{
	  fprintf(stderr, "Error openning file.\n");
	  return 1;
	}
    putchar('\n');
    while(!feof(in)) {dump=fgetc(in); cont++;}
    fclose(in);
    if ((in = fopen(argv[1], "rt"))== NULL)
	{
	  fprintf(stderr, "Error openning file.\n");
	  return 1;
	}
    if ((out = fopen(argv[2], "wt"))== NULL)
	{
	  fprintf(stderr, "Write error.\n");
	  return 1;
	}
    while (!feof(in))
	 {
	  i++;
	  car=fgetc(in);
	  car=~car;
	  fputc(car, out);
	  perc=(i*100)/cont;
	  color(4,0);
	  gotoxy(1,wherey());
	  cprintf(" %d%% encoded.", perc);
	 }
	  gotoxy(1,wherey());
	  cprintf(" 100% encoded.");
    fclose(in);
    fclose(out);
    color(7,0);
    putchar('\n');
    cprintf(" File done.\n\n");
  }
```

