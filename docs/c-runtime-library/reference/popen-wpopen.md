---
title: "_popen, _wpopen | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_popen"
  - "_wpopen"
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
  - "tpopen"
  - "popen"
  - "wpopen"
  - "_popen"
  - "_wpopen"
  - "_tpopen"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_popen (fonction)"
  - "_tpopen (fonction)"
  - "_wpopen (fonction)"
  - "canaux, créer"
  - "popen (fonction)"
  - "tpopen (fonction)"
  - "wpopen (fonction)"
ms.assetid: eb718ff2-c87d-4bd4-bd2e-ba317c3d6973
caps.latest.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 15
---
# _popen, _wpopen
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un canal et exécute une commande.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
  
      FILE *_popen(  
const char *command,  
const char *mode   
);  
FILE *_wpopen(  
const wchar_t *command,  
const wchar_t *mode   
);  
```  
  
#### Paramètres  
 *command*  
 Commande à exécuter.  
  
 *mode*  
 Mode du flux retourné.  
  
## Valeur de retour  
 Retourne un flux associé à une extrémité du canal créé.  L'autre extrémité du canal est associée à l'entrée du standard de la commande engendrée ou à la sortie standard.  Les fonctions retournent **NULL** sur une erreur.  Si l'erreur est un paramètre non valide, tel que si *la commande* ou *le mode* est un pointeur null, ou *mode* n'est pas un mode valide, `errno` a la valeur `EINVAL`.  Consultez la section Notes des modes valides.  
  
 Pour plus d'informations sur ces éléments et autres codes d'erreur, consultez [\_doserrno, errno, \_sys\_errlist et \_sys\_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## Notes  
 La fonction `_popen` crée un canal et exécute de façon asynchrone une copie engendrée de l'interpréteur de commandes avec *la commande*spécifiée de chaîne.  *Le mode* de chaînes de caractères spécifie le type d'accès demandé, comme suit.  
  
 **"r"**  
 Le processus appelant peut lire la sortie standard de la commande engendrée à l'aide du flux retourné.  
  
 **"w"**  
 Le processus appelant peut écrire à l'entrée du standard de la commande engendrée à l'aide du flux retourné.  
  
 **"b"**  
 Ouvrez en mode binaire.  
  
 **"t"**  
 Ouvrir en mode texte  
  
> [!NOTE]
>  Si utilisé dans un programme Windows, la fonction `_popen` retourne un pointeur de fichier non valide qui implique que le programme arrête indéfiniment de répondre.  `_popen` fonctionne correctement dans une application console.  Pour créer une application Windows qui redirige les entrées et sorties, consultez [Création d'un processus enfant à l'entrée et sortie redirigée](http://msdn.microsoft.com/library/windows/desktop/ms682499) dans le [!INCLUDE[winsdkshort](../../atl/reference/includes/winsdkshort_md.md)].  
  
 `_wpopen` est une version à caractères larges de `_popen`; l'argument *path* de `_wpopen`est une chaîne à caractères larges.  `_wpopen` et `_popen` se comportent sinon de manière identique.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_tpopen`|`_popen`|`_popen`|`_wpopen`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_popen`|\<stdio.h\>|  
|`_wpopen`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## Exemple  
  
```  
// crt_popen.c  
/* This program uses _popen and _pclose to receive a   
 * stream of text from a system process.  
 */  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{  
  
   char   psBuffer[128];  
   FILE   *pPipe;  
  
        /* Run DIR so that it writes its output to a pipe. Open this  
         * pipe with read text attribute so that we can read it   
         * like a text file.   
         */  
  
   if( (pPipe = _popen( "dir *.c /on /p", "rt" )) == NULL )  
      exit( 1 );  
  
   /* Read pipe until end of file, or an error occurs. */  
  
   while(fgets(psBuffer, 128, pPipe))  
   {  
      printf(psBuffer);  
   }  
  
   /* Close pipe and print return value of pPipe. */  
   if (feof( pPipe))  
   {  
     printf( "\nProcess returned %d\n", _pclose( pPipe ) );  
   }  
   else  
   {  
     printf( "Error: Failed to read the pipe to the end.\n");  
   }  
}  
```  
  
## Résultat de l'exemple  
 Cette sortie suppose qu'il existe un seul fichier dans le répertoire actif avec l'extension de nom de fichier.c.  
  
```  
 Volume in drive C is CDRIVE  
 Volume Serial Number is 0E17-1702  
  
 Directory of D:\proj\console\test1  
  
07/17/98  07:26p                   780 popen.c  
               1 File(s)            780 bytes  
                             86,597,632 bytes free  
  
Process returned 0  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Contrôle de processus et d'environnement](../../c-runtime-library/process-and-environment-control.md)   
 [\_pclose](../../c-runtime-library/reference/pclose.md)   
 [\_pipe](../../c-runtime-library/reference/pipe.md)