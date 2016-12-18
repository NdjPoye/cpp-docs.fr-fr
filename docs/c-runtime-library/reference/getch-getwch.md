---
title: "_getch, _getwch | Microsoft Docs"
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
  - "_getch"
  - "_getwch"
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
  - "api-ms-win-crt-conio-l1-1-0.dll"
apitype: "DLLExport"
f1_keywords: 
  - "getwch"
  - "_getch"
  - "_getwch"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getch (fonction)"
  - "_getwch (fonction)"
  - "caractères, obtenir de la console"
  - "console, lire dans"
  - "getch (fonction)"
  - "getwch (fonction)"
ms.assetid: cc116be7-cff2-4274-970f-5e7b18ccc05c
caps.latest.revision: 26
caps.handback.revision: 24
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getch, _getwch
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient un caractère venant de la console sans écho.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _getch( void );  
wint_t _getwch( void );  
```  
  
## Valeur de retour  
 Retourne le caractère lu.  Aucun retour d'erreur.  
  
## Notes  
 Les fonctions `_getch` et`_getwch` lisent un seul caractère de la console sans répercuter le caractère.  Aucune de ces fonctions ne peut être utilisée pour lire Ctrl\+C.  En parcourant une touche de fonction ou une touche de direction, chaque fonction doit être appelée deux fois ; le premier appel retourne 0 ou 0xE0, et le deuxième appel retourne le code de touche demandé.  
  
 Ces fonctions verrouillent le thread appelant et sont donc thread\-safe.  Pour les versions non verrouillantes, consultez [\_getch\_nolock, \_getwch\_nolock](../../c-runtime-library/reference/getch-nolock-getwch-nolock.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_gettch`|`_getch`|`_getch`|`_getwch`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getch`|\<conio.h\>|  
|`_getwch`|\<conio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_getch.c  
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
      ch = _getch();  
      ch = toupper( ch );  
   } while( ch != 'Y' );  
  
   _putch( ch );  
   _putch( '\r' );    // Carriage return  
   _putch( '\n' );    // Line feed    
}  
```  
  
  **`abcdey`Taper « O » quand vous avez fini de taper les clés : O**   
## Équivalent .NET Framework  
 Non applicable.  Pour appeler la fonction C standard, utilisez `PInvoke`.  Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [Console et port E\/S](../../c-runtime-library/console-and-port-i-o.md)   
 [\_getche, \_getwche](../../c-runtime-library/reference/getche-getwche.md)   
 [\_cgets, \_cgetws](../../c-runtime-library/cgets-cgetws.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)