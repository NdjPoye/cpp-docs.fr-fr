---
title: "_chdir, _wchdir | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_wchdir"
  - "_chdir"
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
  - "api-ms-win-crt-filesystem-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "tchdir"
  - "_chdir"
  - "_wchdir"
  - "_tchdir"
  - "wchdir"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_tchdir (fonction)"
  - "_chdir (fonction)"
  - "_wchdir (fonction)"
  - "tchdir (fonction)"
  - "wchdir (fonction)"
  - "chdir (fonction)"
  - "répertoires (C++), modification"
ms.assetid: 85e9393b-62ac-45d5-ab2a-fa2217f6152e
caps.latest.revision: 22
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 22
---
# _chdir, _wchdir
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Change le répertoire de travail actif.  
  
## Syntaxe  
  
```  
int _chdir(   
   const char *dirname   
);  
int _wchdir(   
   const wchar_t *dirname   
);  
```  
  
#### Paramètres  
 `dirname`  
 Chemin du nouveau répertoire de travail.  
  
## Valeur de retour  
 Ces fonctions retournent la valeur 0 en cas de réussite. Une valeur de retour –1 indique un échec. Si le chemin spécifié est introuvable, `errno`  est défini sur `ENOENT`. Si `dirname` a la valeur NULL, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno`  est défini sur `EINVAL`  et la fonction retourne \-1.  
  
## Notes  
 La fonction `_chdir`  change le répertoire de travail actuel pour le répertoire spécifié par `dirname`. Le paramètre `dirname` doit faire référence à un répertoire existant. Cette fonction peut changer le répertoire de travail actuel sur n’importe quel lecteur. Si une nouvelle lettre de lecteur est spécifiée dans `dirname`, la lettre du lecteur par défaut est également changée. Par exemple, si A est la lettre de lecteur par défaut et \\BIN le répertoire de travail actuel, l’appel suivant change le répertoire de travail actuel pour le lecteur C et établit C comme nouveau lecteur par défaut :  
  
```  
_chdir("c:\\temp");  
```  
  
 Quand vous utilisez le caractère facultatif barre oblique inverse \(`\`\) dans les chemins, vous devez placer deux barres obliques inverses \(`\\`\) dans une chaîne littérale C pour représenter une barre oblique inverse \(`\`\).  
  
 `_wchdir`  est une version à caractères larges de `_chdir` ; l’argument `dirname` de `_wchdir`  est une chaîne à caractères larges. Sinon, `. _wchdir`  et `_chdir`  se comportent de façon identique.  
  
### Mappage de routines de texte générique :  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tchdir`|`_chdir`|`_chdir`|`_wchdir`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|En\-tête facultatif|  
|-------------|---------------------|-------------------------|  
|`_chdir`|\<direct.h\>|\<errno.h\>|  
|`_wchdir`|\<direct.h\> ou \<wchar.h\>|\<errno.h\>|  
  
 Pour plus d’informations sur la compatibilité, voir [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_chdir.c  
// arguments: C:\WINDOWS  
  
/* This program uses the _chdir function to verify  
   that a given directory exists. */  
  
#include <direct.h>  
#include <stdio.h>  
#include <stdlib.h>  
#include <errno.h>  
  
int main( int argc, char *argv[] )  
{  
  
   if(_chdir( argv[1] ) )  
   {  
      switch (errno)  
      {  
      case ENOENT:  
         printf( "Unable to locate the directory: %s\n", argv[1] );  
         break;  
      case EINVAL:  
         printf( "Invalid buffer.\n");  
         break;  
      default:  
         printf( "Unknown error.\n");  
      }  
   }  
   else  
      system( "dir *.exe");  
}  
```  
  
```Output  
Le volume dans le lecteur C n’a pas de nom. Le numéro de série du volume est 2018-08A1 Répertoire de c:\windows 29/08/2002  04:00         1 004 032 explorer.exe 17/12/2002  16:43            10 752 hh.exe 03/03/2003  09:24            33 792 ieuninst.exe 29/10/1998  16:45           306 688 IsUninst.exe 29/08/2002  04:00            66 048 NOTEPAD.EXE 03/03/2003  09:24            33 792 Q330994.exe 29/08/2002  04:00           134 144 regedit.exe 28/02/2003  18:26            46 352 setdebug.exe 29/08/2002  04:00            15 360 TASKMAN.EXE 29/08/2002  04:00            49 680 twunk_16.exe 29/08/2002  04:00            25 600 twunk_32.exe 29/08/2002  04:00           256 192 winhelp.exe 29/08/2002  04:00           266 752 winhlp32.exe 13 Fichier(s)      2 249 184 octets 0 Rép(s)  67 326 029 824 octets libres  
```  
  
## Équivalent .NET Framework  
 [System::Environment::CurrentDirectory](https://msdn.microsoft.com/en-us/library/system.environment.currentdirectory.aspx)  
  
## Voir aussi  
 [Contrôle de répertoire](../../c-runtime-library/directory-control.md)   
 [\_mkdir, \_wmkdir](../../c-runtime-library/reference/mkdir-wmkdir.md)   
 [\_rmdir, \_wrmdir](../../c-runtime-library/reference/rmdir-wrmdir.md)   
 [system, \_wsystem](../../c-runtime-library/reference/system-wsystem.md)