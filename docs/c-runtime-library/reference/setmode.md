---
title: "_setmode | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_setmode"
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
  - "_setmode"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_setmode (fonction)"
  - "translation de fichier (C++), définir le mode"
  - "fichiers (C++), modes"
  - "fichiers (C++), translation"
  - "setmode (fonction)"
  - "Unicode (C++), sortie de la console"
ms.assetid: 996ff7cb-11d1-43f4-9810-f6097182642a
caps.latest.revision: 23
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _setmode
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Définit le mode de traduction des fichiers.  
  
## Syntaxe  
  
```  
int _setmode (    int fd,    int mode  );  
```  
  
#### Paramètres  
 `fd`  
 Descripteur de fichier.  
  
 `mode`  
 Nouveau mode de traduction.  
  
## Valeur de retour  
 En cas de réussite, retourne le mode de traduction précédent.  
  
 Si des paramètres non valides sont passés à cette fonction, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, cette fonction retourne –1 et affecte à `errno` la valeur `EBADF`, qui indique un descripteur de fichier non valide, ou la valeur `EINVAL`, qui indique un argument `mode` non valide.  
  
 Pour plus d'informations sur ces codes de retour et autres, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_setmode` affecte la valeur `mode` au mode de traduction du fichier donné par `fd`.  Le passage de la valeur `_O_TEXT` comme `mode` définit le mode texte \(autrement dit, traduit\).  Les combinaisons retour chariot\/saut de ligne sont traduites en un seul caractère de saut de ligne en entrée.  Les caractères de saut de ligne sont traduits en combinaisons retour chariot\/saut de ligne en sortie.  Le passage de la valeur `_O_BINARY` définit le mode binaire \(non traduit\), dans lequel ces traductions sont supprimées.  
  
 Vous pouvez également passer les valeurs `_O_U16TEXT`, `_O_U8TEXT` ou \_`O_WTEXT` pour activer le mode Unicode, comme illustré dans le second exemple plus loin dans ce document.  `_setmode` est généralement utilisé pour modifier le mode de traduction par défaut de `stdin` et `stdout`, mais vous pouvez l'utiliser sur n'importe quel fichier.  Si vous appliquez `_setmode` au descripteur de fichier pour un flux, appelez `_setmode` avant d'effectuer toute opération d'entrée ou de sortie sur le flux.  
  
> [!CAUTION]
>  Si vous écrivez des données dans un flux de fichiers, videz le code de façon explicite en utilisant [fflush](../../c-runtime-library/reference/fflush.md) avant d'utiliser `_setmode` pour changer le mode.  Si vous ne videz pas le code, un comportement inattendu peut se produire.  Si vous n'avez pas écrit de données dans le flux, vous n'avez pas à vider le code.  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-têtes facultatifs|  
|-------------|---------------------|---------------------------|  
|`_setmode`|\<io.h\>|\<fcntl.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_setmode.c  
// This program uses _setmode to change  
// stdin from text mode to binary mode.  
  
#include <stdio.h>  
#include <fcntl.h>  
#include <io.h>  
  
int main( void )  
{  
   int result;  
  
   // Set "stdin" to have binary mode:  
   result = _setmode( _fileno( stdin ), _O_BINARY );  
   if( result == -1 )  
      perror( "Cannot set mode" );  
   else  
      printf( "'stdin' successfully changed to binary mode\n" );  
}  
```  
  
  **'stdin' est correctement passé au mode binaire**   
## Exemple  
  
```  
// crt_setmodeunicode.c  
// This program uses _setmode to change  
// stdout to Unicode. Cyrillic and Ideographic  
// characters will appear on the console (if  
// your console font supports those character sets).  
  
#include <fcntl.h>  
#include <io.h>  
#include <stdio.h>  
  
int main(void) {  
    _setmode(_fileno(stdout), _O_U16TEXT);  
    wprintf(L"\x043a\x043e\x0448\x043a\x0430 \x65e5\x672c\x56fd\n");  
    return 0;  
}  
  
```  
  
## Équivalent .NET Framework  
  
-   [\<caps:sentence id\="tgt28" sentenceid\="fe03c471a7a38d5378cea62467482dae" class\="tgtSentence"\>System::IO::BinaryReader Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.binaryreader.aspx)  
  
-   [\<caps:sentence id\="tgt29" sentenceid\="105e62b7505c25e3e182779c87f145eb" class\="tgtSentence"\>System::IO::TextReader Class\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/system.io.textreader.aspx)  
  
## Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)   
 [\_creat, \_wcreat](../../c-runtime-library/reference/creat-wcreat.md)   
 [fopen, \_wfopen](../../c-runtime-library/reference/fopen-wfopen.md)   
 [\_open, \_wopen](../../c-runtime-library/reference/open-wopen.md)   
 [\_set\_fmode](../../c-runtime-library/reference/set-fmode.md)