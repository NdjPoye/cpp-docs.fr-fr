---
title: "_cgets, _cgetws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_cgetws"
  - "_cgets"
apilocation: 
  - "msvcr100.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr120.dll"
  - "msvcr90.dll"
  - "msvcrt.dll"
  - "msvcr110_clr0400.dll"
apitype: "DLLExport"
f1_keywords: 
  - "cgetws"
  - "_cgetws"
  - "_cgets"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_cgets (fonction)"
  - "_cgetws (fonction)"
  - "cgets (fonction)"
  - "cgetws (fonction)"
  - "console, obtenir des chaînes de"
  - "chaînes (C++), obtenir de la console"
ms.assetid: 4d5e134a-58c3-4f62-befd-5d235b0212f4
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# _cgets, _cgetws
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient une chaîne de caractères à partir de la console. Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Ces fonctions sont obsolètes. Depuis Visual Studio 2015, elles ne sont pas disponibles dans la bibliothèque CRT. Les versions sécurisées de ces fonctions, \_cgets\_s et \_cgetws\_s, sont toujours disponibles. Pour plus d’informations sur ces fonctions alternatives, consultez [\_cgets\_s, \_cgetws\_s](../c-runtime-library/reference/cgets-s-cgetws-s.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *_cgets(   
   char *buffer   
);  
wchar_t *_cgetws(  
   wchar_t *buffer  
);  
template <size_t size>  
char *_cgets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_cgetws(  
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage des données.  
  
## Valeur de retour  
 `_cgets` et `_cgetws` retournent un pointeur vers le début de la chaîne, à l’emplacement `buffer[2]`. Si `buffer` est `NULL`, ces fonctions appellent le gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à continuer, elles retournent `NULL` et définissent `errno` sur `EINVAL`.  
  
## Notes  
 Ces fonctions lisent une chaîne de caractères à partir de la console, et stockent la chaîne et sa longueur à l’emplacement désigné par `buffer`. Le paramètre `buffer` doit être un pointeur vers un tableau de caractères. Le premier élément du tableau, `buffer[0]`, doit contenir la longueur maximale \(en caractères\) de la chaîne à lire. Le tableau doit contenir suffisamment d’éléments pour stocker la chaîne, un caractère null de fin \(« \\0 »\) et 2 octets supplémentaires. La fonction lit les caractères jusqu’à une combinaison CRLF \(retour chariot –  saut de ligne\) ou jusqu’à ce que le nombre de caractères spécifiés soit lu. La chaîne est stockée à partir de `buffer[2]`. Si la fonction lit un CRLF, elle stocke le caractère null \(« \\0 »\). La fonction stocke ensuite la longueur réelle de la chaîne dans le deuxième élément du tableau, `buffer[1]`.  
  
 Comme toutes les touches d’édition sont actives quand `_cgets` ou `_cgetws` est appelée alors que c’est une fenêtre de console qui est active, le fait d’appuyer sur la touche F3 répète la dernière entrée saisie.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions. Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine Tchar.h|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_cgetts`|`_cgets`|`_cgets`|`_cgetws`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`_cgets`|\<conio.h\>|  
|`_cgetws`|\<conio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_cgets.c // compile with: /c /W3 // This program creates a buffer and initializes // the first byte to the size of the buffer. Next, the // program accepts an input string using _cgets and displays // the size and text of that string. #include <conio.h> #include <stdio.h> #include <errno.h> int main( void ) { char buffer[83] = { 80 };  // Maximum characters in 1st byte char *result; printf( "Input line of text, followed by carriage return:\n"); // Input a line of text: result = _cgets( buffer ); // C4996 // Note: _cgets is deprecated; consider using _cgets_s if (!result) { printf( "An error occurred reading from the console:" " error code %d\n", errno); } else { printf( "\nLine length = %d\nText = %s\n", buffer[1], result ); } }  
```  
  
```Output  
  
A line of input.Ligne de texte entrée, suivi d’un retour chariot : Longueur de la ligne = 16  Texte = une ligne d’entrée.  
```  
  
## Voir aussi  
 [Console et port E\/S](../c-runtime-library/console-and-port-i-o.md)   
 [\_getch, \_getwch](../c-runtime-library/reference/getch-getwch.md)