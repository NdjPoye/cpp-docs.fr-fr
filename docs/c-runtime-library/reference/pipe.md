---
title: "_pipe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_pipe"
apilocation: 
  - "msvcrt.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr100_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
  - "msvcr120_clr0400.dll"
  - "ucrtbase.dll"
  - "api-ms-win-crt-stdio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "pipe"
  - "_pipe"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_pipe (fonction)"
  - "pipe (fonction)"
  - "canaux"
  - "canaux, créer"
ms.assetid: 8d3e9800-4041-44b5-9e93-2df0b0354a75
caps.latest.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 20
---
# _pipe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un canal pour lire et écrire.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le [!INCLUDE[wrt](../../atl/reference/includes/wrt_md.md)].  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
  
      int _pipe(  
int *pfds,  
unsigned int psize,  
int textmode   
);  
```  
  
#### Paramètres  
 `pfds`\[2\]  
 Tableau qui contient les descripteurs de fichier en lecture et en écriture.  
  
 `psize`  
 Quantité de mémoire à réserver.  
  
 `textmode`  
 Mode d'accès au fichier.  
  
## Valeur de retour  
 En cas de réussite, retourne 0.  Retourne \-1 pour indiquer une erreur.  S'il y a une erreur, une des valeurs suivantes est affectée à `errno` :  
  
-   `EMFILE`, qui indique qu'aucun descripteur de fichier n'est disponible.  
  
-   `ENFILE`, qui indique un dépassement de capacité de système\-fichier\-table.  
  
-   `EINVAL`, qui indique que le tableau `pfds` est un pointeur null ou qu'une valeur valide pour `textmode` a été passée.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [errno, \_doserrno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_pipe` crée un *canal*, qui est un canal d'E\/S artificiel qu'un programme utilise pour passer des informations à d'autres programmes.  Un canal ressemble à un fichier parce qu'il possède un pointeur de fichier, un descripteur de fichier, ou les deux, et il peut être lu en lecture ou en écriture en utilisant les fonctions d'entrée et de sortie standard de bibliothèque.  Toutefois, un canal ne représente pas un fichier spécifique ou un périphérique.  À la place, il représente le stockage temporaire en mémoire qui est indépendant de la propre mémoire du programme et est contrôlée entièrement par le système d'exploitation.  
  
 `_pipe` ressemble à `_open` mais ouvre le canal pour lire et écrire et retourne deux descripteurs de fichier au lieu d'un.  Le programme peut utiliser les deux côtés du canal ou fermer celui depuis depuis celui qui lui est inutile.  Par exemple, l'interpréteur de commandes dans Windows crée un canal lorsqu'il exécute une commande telle qye `PROGRAM1 | PROGRAM2`.  
  
 Le descripteur de sortie standard de `PROGRAM1` est attaché au descripteur de l'écriture du canal.  Le descripteur d'entrée standard de `PROGRAM2` est attaché au descripteur de lecture du canal.  Cela évite d'avoir à créer des fichiers temporaires pour passer des informations à d'autres programmes.  
  
 Fonction d'`_pipe` retourne deux descripteurs de fichier au canal dans l'argument `pfds`.  L'élément `pfds`\[0\] contient le descripteur de lecture, et l'élément `pfds`\[1\] contient le descripteur d'écriture.  Les descripteurs de fichier de canal sont utilisés de la même manière que les autres descripteurs de fichier. \(Les fonctions d'entrée et de sortie de bas niveau `_read` et `_write` peuvent lire et écrire depuis un canal.\) Pour détecter l'état de fin du cycle, vérifier l'existence d'une demande `_read` qui retourne 0 comme nombre d'octets.  
  
 L'argument `psize` spécifie la quantité de mémoire, en octets, à réserver pour le canal.  L'argument `textmode` spécifie le mode de traduction du canal.  La constante `_O_TEXT` spécifie une traduction de texte, et la constante `_O_BINARY` spécifie la traduction binaire. \(Consultez [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md) pour une description des modes de texte et binaire.\) Si l'argument `textmode` est à 0, `_pipe` utilise le mode de traduction par défaut spécifié par la variable [\_fmode](../../c-runtime-library/fmode.md)de valeur par défaut mode.  
  
 Dans les programmes multithreads, aucun verrouillage n'est exécuté.  Les descripteurs de fichier retournés sont récemment ouverts et ne doivent pas être référencés par aucun thread tant que l'appel d'`_pipe` n'est pas terminé.  
  
 Pour utiliser la fonction `_pipe` pour communiquer entre un processus parent et un processus enfant, chaque processus ne doit avoir qu'un seul descripteur ouvert sur le canal.  Les descripteurs doivent être opposés : si le parent a un descripteur de lecture ouvert, l'enfant doit avoir un descripteur d'écriture ouvert.  La façon la plus simple consiste à `OR` \(  `|`\) l'indicateur `_O_NOINHERIT` avec `textmode`.  Ensuite, utilisez `_dup` ou `_dup2` pour créer une copie héritable du descripteur de canal que vous souhaitez passer à l'enfant.  Fermez le descripteur d'origine, puis engendrez le processus enfant.  Sur retour de l'appel de frai, fermez le descripteur en double dans le processus parent.  Pour plus d'informations, consultez l'exemple 2 ultérieurement dans cet article.  
  
 Dans le système d'exploitation Windows, un canal est détruit lorsque tous ses descripteurs associés. \(Si tous les descripteurs de lecture du canal ont été fermés, l'écriture au canal provoque une erreur.\) Toutes les opérations en lecture et en écriture sur le canal attendent jusqu'à ce qu'il y ait assez de données ou suffisamment d'espace de mémoire tampon pour terminer la demande d'E\/S.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_pipe`|\<io.h,\>|\<fcntl.h\>,1 \<errno.h\>2|  
  
 1 Pour `_O_BINARY` et des définitions de `_O_TEXT`.  
  
 2 définitions `errno`.  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple 1  
  
```  
// crt_pipe.c  
/* This program uses the _pipe function to pass streams of  
 * text to spawned processes.  
 */  
  
#include <stdlib.h>  
#include <stdio.h>  
#include <io.h>  
#include <fcntl.h>  
#include <process.h>  
#include <math.h>  
  
enum PIPES { READ, WRITE }; /* Constants 0 and 1 for READ and WRITE */  
#define NUMPROBLEM 8  
  
int main( int argc, char *argv[] )  
{  
  
   int fdpipe[2];  
   char hstr[20];  
   int pid, problem, c;  
   int termstat;  
  
   /* If no arguments, this is the spawning process */  
   if( argc == 1 )  
   {  
  
      setvbuf( stdout, NULL, _IONBF, 0 );  
  
      /* Open a set of pipes */  
      if( _pipe( fdpipe, 256, O_BINARY ) == -1 )  
          exit( 1 );  
  
      /* Convert pipe read descriptor to string and pass as argument   
       * to spawned program. Program spawns itself (argv[0]).  
       */  
      _itoa_s( fdpipe[READ], hstr, sizeof(hstr), 10 );  
      if( ( pid = _spawnl( P_NOWAIT, argv[0], argv[0],   
            hstr, NULL ) ) == -1 )  
          printf( "Spawn failed" );  
  
      /* Put problem in write pipe. Since spawned program is   
       * running simultaneously, first solutions may be done   
       * before last problem is given.  
       */  
      for( problem = 1000; problem <= NUMPROBLEM * 1000; problem += 1000)  
      {  
  
         printf( "Son, what is the square root of %d?\n", problem );  
         _write( fdpipe[WRITE], (char *)&problem, sizeof( int ) );  
  
      }  
  
      /* Wait until spawned program is done processing. */  
      _cwait( &termstat, pid, WAIT_CHILD );  
      if( termstat & 0x0 )  
         printf( "Child failed\n" );  
  
      _close( fdpipe[READ] );  
      _close( fdpipe[WRITE] );  
  
   }  
  
   /* If there is an argument, this must be the spawned process. */  
   else  
   {  
  
      /* Convert passed string descriptor to integer descriptor. */  
      fdpipe[READ] = atoi( argv[1] );  
  
      /* Read problem from pipe and calculate solution. */  
      for( c = 0; c < NUMPROBLEM; c++ )  
      {  
  
        _read( fdpipe[READ], (char *)&problem, sizeof( int ) );  
        printf( "Dad, the square root of %d is %3.2f.\n",  
                 problem, sqrt( ( double )problem ) );  
  
      }  
   }  
}  
```  
  
## Résultat de l'exemple  
  
```  
Son, what is the square root of 1000?  
Son, what is the square root of 2000?  
Son, what iDad, the square root of 1000 is 31.62.  
Dad, the square root of 2000 is 44.72.  
s the square root of 3000?  
Dad, the square root of 3000 is 54.77.  
Son, what is the square root of 4000?  
Dad, the square root of 4000 is 63.25.  
Son, what is the square root of 5000?  
Dad, the square root of 5000 is 70.71.  
Son, what is the square root of 6000?  
SonDad, the square root of 6000 is 77.46.  
, what is the square root of 7000?  
Dad, the square root of 7000 is 83.67.  
Son, what is the square root of 8000?  
Dad, the square root of 8000 is 89.44.  
```  
  
## Exemple 2  
 C'est une application de base de filtre.  Elle engendre l'application crt\_pipe\_beeper après qu'elle crée un canal qui dirige le stdout de l'application engendrée au filtre.  Le filtre supprime ASCII 7 caractères \(signal sonore\).  
  
```  
// crt_pipe_beeper.c  
  
#include <stdio.h>  
#include <string.h>  
  
int main()  
{  
   int   i;  
   for(i=0;i<10;++i)  
      {  
         printf("This is speaker beep number %d...\n\7", i+1);  
      }  
   return 0;  
}  
```  
  
 L'application réelle des filtres :  
  
```  
// crt_pipe_BeepFilter.C  
// arguments: crt_pipe_beeper.exe  
  
#include <windows.h>  
#include <process.h>  
#include <memory.h>  
#include <string.h>  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
#define   OUT_BUFF_SIZE 512  
#define   READ_FD 0  
#define   WRITE_FD 1  
#define   BEEP_CHAR 7  
  
char szBuffer[OUT_BUFF_SIZE];  
  
int Filter(char* szBuff, ULONG nSize, int nChar)  
{  
   char* szPos = szBuff + nSize -1;  
   char* szEnd = szPos;  
   int nRet = nSize;  
  
   while (szPos > szBuff)  
   {  
      if (*szPos == nChar)  
         {  
            memmove(szPos, szPos+1, szEnd - szPos);  
            --nRet;  
         }  
      --szPos;  
   }  
   return nRet;  
}  
  
int main(int argc, char** argv)  
{  
   int nExitCode = STILL_ACTIVE;  
   if (argc >= 2)  
   {  
      HANDLE hProcess;  
      int fdStdOut;  
      int fdStdOutPipe[2];  
  
      // Create the pipe  
      if(_pipe(fdStdOutPipe, 512, O_NOINHERIT) == -1)  
         return   1;  
  
      // Duplicate stdout file descriptor (next line will close original)  
      fdStdOut = _dup(_fileno(stdout));  
  
      // Duplicate write end of pipe to stdout file descriptor  
      if(_dup2(fdStdOutPipe[WRITE_FD], _fileno(stdout)) != 0)  
         return   2;  
  
      // Close original write end of pipe  
      _close(fdStdOutPipe[WRITE_FD]);  
  
      // Spawn process  
      hProcess = (HANDLE)_spawnvp(P_NOWAIT, argv[1],   
       (const char* const*)&argv[1]);  
  
      // Duplicate copy of original stdout back into stdout  
      if(_dup2(fdStdOut, _fileno(stdout)) != 0)  
         return   3;  
  
      // Close duplicate copy of original stdout  
      _close(fdStdOut);  
  
      if(hProcess)  
      {  
         int nOutRead;  
         while   (nExitCode == STILL_ACTIVE)  
         {  
            nOutRead = _read(fdStdOutPipe[READ_FD],   
             szBuffer, OUT_BUFF_SIZE);  
            if(nOutRead)  
            {  
               nOutRead = Filter(szBuffer, nOutRead, BEEP_CHAR);  
               fwrite(szBuffer, 1, nOutRead, stdout);  
            }  
  
            if(!GetExitCodeProcess(hProcess,(unsigned long*)&nExitCode))  
               return 4;  
         }  
      }  
   }  
   return nExitCode;  
}  
```  
  
## Sortie  
  
```  
This is speaker beep number 1...  
This is speaker beep number 2...  
This is speaker beep number 3...  
This is speaker beep number 4...  
This is speaker beep number 5...  
This is speaker beep number 6...  
This is speaker beep number 7...  
This is speaker beep number 8...  
This is speaker beep number 9...  
This is speaker beep number 10...  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Platform Invoke Examples](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)