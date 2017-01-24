---
title: "_getche, _getwche | Microsoft Docs"
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
  - "_getwche"
  - "_getche"
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
  - "getwche"
  - "_getche"
  - "_getwche"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getche (fonction)"
  - "_getwche (fonction)"
  - "caractères, obtenir de la console"
  - "console, lire dans"
  - "getche (fonction)"
  - "getwche (fonction)"
ms.assetid: eac978a8-c43a-4130-938f-54f12e2a0fda
caps.latest.revision: 23
caps.handback.revision: 21
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _getche, _getwche
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Obtient un caractère venant de la console avec écho.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _getche( void );  
wint_t _getwche( void );  
```  
  
## Valeur de retour  
 Retourne le caractère lu.  Aucun retour d'erreur.  
  
## Notes  
 Les fonctions `_getche` et `_getwche` lisent un caractère unique de la console avec l'écho, ce qui signifie que le caractère est affiché dans la console.  Aucune de ces fonctions ne peut être utilisée pour lire Ctrl\+C.  En parcourant une touche de fonction ou une touche de direction, chaque fonction doit être appelée deux fois ; le premier appel retourne 0 ou 0xE0, et le deuxième appel retourne le code de touche demandé.  
  
 Ces fonctions verrouillent le thread appelant et sont donc thread\-safe.  Pour les versions non verrouillantes, consultez [\_getche\_nolock, \_getwche\_nolock](../../c-runtime-library/reference/getche-nolock-getwche-nolock.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_getche`|`_getche`|`_getch`|`_getwche`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_getche`|\<conio.h\>|  
|`_getwche`|\<conio.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_getche.c  
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
      ch = _getche();  
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
 [\_cgets, \_cgetws](../../c-runtime-library/cgets-cgetws.md)   
 [getc, getwc](../../c-runtime-library/reference/getc-getwc.md)   
 [\_ungetch, \_ungetwch, \_ungetch\_nolock, \_ungetwch\_nolock](../../c-runtime-library/reference/ungetch-ungetwch-ungetch-nolock-ungetwch-nolock.md)