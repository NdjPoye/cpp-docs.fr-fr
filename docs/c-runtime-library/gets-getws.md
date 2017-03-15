---
title: "gets, _getws | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getws"
  - "gets"
apilocation: 
  - "msvcr80.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
  - "msvcr110.dll"
  - "msvcr110_clr0400.dll"
  - "msvcrt.dll"
  - "msvcr100.dll"
apitype: "DLLExport"
f1_keywords: 
  - "_getts"
  - "gets"
  - "_getws"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_getts (fonction)"
  - "_getws (fonction)"
  - "gets (fonction)"
  - "getts (fonction)"
  - "getws (fonction)"
  - "lignes, obtenir"
  - "entrée standard, lire dans"
  - "flux, obtenir des lignes"
ms.assetid: 1ec2dd4b-f801-48ea-97c2-892590f16024
caps.latest.revision: 32
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 32
---
# gets, _getws
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Obtient une ligne du flux `stdin` Des versions plus sécurisées de ces fonctions sont disponibles. Consultez [gets\_s, \_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
> [!IMPORTANT]
>  Ces fonctions sont obsolètes. Depuis Visual Studio 2015, elles ne sont pas disponibles dans la bibliothèque CRT. Les versions sécurisées de ces fonctions, gets\_s et getws\_s, sont toujours disponibles. Pour plus d’informations sur ces fonctions alternatives, consultez [gets\_s, \_getws\_s](../c-runtime-library/reference/gets-s-getws-s.md).  
  
> [!IMPORTANT]
>  Cette API ne peut pas être utilisée dans les applications qui s'exécutent dans le Windows Runtime. Pour plus d’informations, consultez [Fonctions CRT non prises en charge avec \/ZW](http://msdn.microsoft.com/library/windows/apps/jj606124.aspx).  
  
## Syntaxe  
  
```  
char *gets(   
   char *buffer   
);  
wchar_t *_getws(   
   wchar_t *buffer   
);  
template <size_t size>  
char *gets(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Paramètres  
 `buffer`  
 Emplacement de stockage pour une chaîne entrée.  
  
## Valeur de retour  
 Retourne son argument en cas de réussite. Un pointeur `NULL` indique une condition d’erreur ou de fin de fichier. Utilisez [ferror](../c-runtime-library/reference/ferror.md) ou [feof](../c-runtime-library/reference/feof.md) pour déterminer laquelle des deux s’est produite. Si `buffer` est `NULL`, ces fonctions appellent un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent `NULL` et définissent errno sur `EINVAL`.  
  
## Notes  
 La fonction `gets` lit une ligne dans le flux d’entrée standard `stdin` et la stocke dans `buffer`. La ligne se compose de tous les caractères jusqu’à et y compris le premier caractère de saut de ligne \(« \\n »\).`gets` remplace ensuite le caractère de saut de ligne par un caractère null \(« \\0 »\) avant de retourner la ligne. En revanche, la fonction `fgets` conserve le caractère de saut de ligne.`_getws` est une version à caractères larges de `gets` ; son argument et sa valeur de retour sont des chaînes à caractères larges.  
  
> [!IMPORTANT]
>  Comme il n’existe aucun moyen de limiter le nombre de caractères lus par gets, une entrée non approuvée peut facilement provoquer des dépassements de la mémoire tampon. Utilisez plutôt `fgets`.  
  
 En C\+\+, ces fonctions ont des surcharges de modèle qui appellent les équivalents plus récents et sécurisés de ces fonctions. Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE et \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|-------------------------------------|-------------------|----------------------|  
|`_getts`|`gets`|`gets`|`_getws`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`gets`|\<stdio.h\>|  
|`_getws`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, voir [Compatibilité](../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_gets.c // compile with: /WX /W3 #include <stdio.h> int main( void ) { char line[21]; // room for 20 chars + '\0' gets( line );  // C4996 // Danger: No way to limit input to 20 chars. // Consider using gets_s instead. printf( "The line entered was: %s\n", line ); }  
```  
  
 Notez qu’une entrée de plus de 20 caractères entraînera le dépassement de la mémoire tampon de ligne et presque certainement le blocage du programme.  
  
```Output  
  
Hello there!La ligne entrée était : Hello there!  
```  
  
## Équivalent .NET Framework  
 [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Voir aussi  
 [E\/S de flux](../c-runtime-library/stream-i-o.md)   
 [fgets, fgetws](../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../c-runtime-library/reference/fputs-fputws.md)   
 [puts, \_putws](../c-runtime-library/reference/puts-putws.md)