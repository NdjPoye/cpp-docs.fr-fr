---
title: "_ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock | Microsoft Docs"
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
  - "_ungetch_nolock"
  - "_ungetwch_nolock"
  - "_ungetwch"
  - "_ungetch"
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
  - "_ungetch_nolock"
  - "ungetwch"
  - "ungetch_nolock"
  - "_ungetwch"
  - "ungetch"
  - "ungetwch_nolock"
  - "_ungetch"
  - "_ungettch_nolock"
  - "_ungettch"
  - "_ungetwch_nolock"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_ungetch (fonction)"
  - "_ungetch_nolock (fonction)"
  - "_ungettch (fonction)"
  - "_ungettch_nolock (fonction)"
  - "_ungetwch (fonction)"
  - "_ungetwch_nolock (fonction)"
  - "caractères, push vers la console"
  - "ungetch_nolock (fonction)"
  - "ungettch (fonction)"
  - "ungettch_nolock (fonction)"
  - "ungetwch (fonction)"
  - "ungetwch_nolock (fonction)"
ms.assetid: 70ae71c6-228c-4883-a57d-de6d5f873825
caps.latest.revision: 17
caps.handback.revision: 15
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# _ungetch, _ungetwch, _ungetch_nolock, _ungetwch_nolock
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Renvoie le dernier caractère qui est lu de la console.  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime.  Pour plus d'informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
int _ungetch(  
   int c   
);  
wint_t _ungetwch(  
   wint_t c   
);  
int _ungetch_nolock(  
   int c   
);  
wint_t _ungetwch_nolock(  
   wint_t c   
);  
```  
  
#### Paramètres  
 `c`  
 Caractère à renvoyer.  
  
## Valeur de retour  
 Les fonctions retournent le caractère `c` en cas de réussite.  S'il y a une erreur, `_ungetch` retourne la valeur `EOF` et `_ungetwch`retourne`WEOF`.  
  
## Notes  
 Ces fonctions poussent le caractère `c` dans la console, et `c` est le caractère suivant lu par `_getch` ou `_getche` \(`_getwch` ou`_getwche`\).  `_ungetch` et `_ungetwch` échouent si elles sont appelées plusieurs fois avant la lecture suivante.  L'argument `c` ne peut pas être `EOF` \(ou `WEOF`\).  
  
 Les versions avec le suffixe `_nolock` sont identiques mais elles ne sont pas protégées contre les interférence en provenance d'autres threads.  Elles peuvent être plus rapides car elles n'entraînent pas la charge du verrouillage des autres threads.  Utilisez ces fonctions uniquement dans les contextes thread\-safe, tels que les applications à un seul thread ou lorsque la portée appelante gère déjà l'isolation des threads.  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_ungettch`|`_ungetch`|`_ungetch`|`_ungetwch`|  
|`_ungettch_nolock`|`_ungetch_nolock`|`_ungetch_nolock`|`_ungetwch_nolock`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_ungetch`, `_ungetch_nolock`|\<conio.h\>|  
|`_ungetwch`, `_ungetwch_nolock`|\<conio.h\> or \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_ungetch.c  
// compile with: /c  
// In this program, a white-space delimited   
// token is read from the keyboard. When the program   
// encounters a delimiter, it uses _ungetch to replace   
// the character in the keyboard buffer.  
//  
  
#include <conio.h>  
#include <ctype.h>  
#include <stdio.h>  
  
int main( void )  
{  
   char buffer[100];  
   int count = 0;  
   int ch;  
  
   ch = _getche();  
   while( isspace( ch ) )      // Skip preceding white space.  
      ch = _getche();  
   while( count < 99 )         // Gather token.  
   {  
      if( isspace( ch ) )      // End of token.  
         break;  
      buffer[count++] = (char)ch;  
      ch = _getche();  
   }  
   _ungetch( ch );            // Put back delimiter.  
   buffer[count] = '\0';      // Null terminate the token.  
   printf( "\ntoken = %s\n", buffer );  
}  
```  
  
  **`Blanc` jeton \= blanc**   
## Voir aussi  
 [Console et port E\/S](../../c-runtime-library/console-and-port-i-o.md)   
 [\_cscanf, \_cscanf\_l, \_cwscanf, \_cwscanf\_l](../../c-runtime-library/reference/cscanf-cscanf-l-cwscanf-cwscanf-l.md)   
 [\_getch, \_getwch](../../c-runtime-library/reference/getch-getwch.md)