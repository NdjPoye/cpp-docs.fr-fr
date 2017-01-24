---
title: "_getche_nolock, _getwche_nolock | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getche_nolock"
  - "_getwche_nolock"
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
apitype: "DLLExport"
f1_keywords: 
  - "_getche_nolock"
  - "_gettche_nolock"
  - "_getwche_nolock"
  - "getche_nolock"
  - "getwche_nolock"
  - "gettche_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getche_nolock (fonction)"
  - "_gettche_nolock (fonction)"
  - "_getwche_nolock (fonction)"
  - "caractères, obtenir de la console"
  - "console, lire dans"
  - "getche_nolock (fonction)"
  - "gettche_nolock (fonction)"
  - "getwche_nolock (fonction)"
ms.assetid: 9e853ad4-4d8a-4442-9ae5-da4b434f0b8c
caps.latest.revision: 18
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getche_nolock, _getwche_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient un caractère depuis la console sans écho et sans verrouiller le thread.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _getche_nolock( void );  
wint_t _getwche_nolock( void );  
```  
  
## Valeur de retour  
 Retourne le caractère lu.  Aucun retour d'erreur.  
  
## Notes  
 `_getche_nolock` et `_getwche_nolock` sont identiques à `_getche` et `_getwche` sauf qu'ils ne sont pas protégés des interférences avec d'autres threads.  Elles peuvent être plus rapides, car elles n'entraînent pas la charge du verrouillage des autres threads.  Utilisez ces fonctions uniquement dans les contextes thread\-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_gettche_nolock`|`_getche_nolock`|`_getch_nolock`|`_getwche_nolock`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getche_nolock`|\<conio.h\>|  
|`_getwche_nolock`|\<conio.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_getche_nolock.c  
// compile with: /c  
// This program reads characters from  
// the keyboard until it receives a 'Y' or 'y'.  
  
#include <conio.h>  
#include <ctype.h>  
  
int main( void )  
{  
   int ch;  
  
   _cputs( "Type 'Y' when finished typing keys: " );  
   do  
   {  
      ch = _getche_nolock();  
      ch = toupper( ch );  
   } while( ch != 'Y' );  
  
   _putch_nolock( ch );  
   _putch_nolock( '\r' );    // Carriage return  
   _putch_nolock( '\n' );    // Line feed   
}  
```  
  
  **`abcdey`Taper « O » quand vous avez fini de taper les clés : O**   
## Équivalent .NET Framework  
 Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Console et port E\/S](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cgets, \_cgetws](../../c-runtime-library/cgets-cgetws.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)