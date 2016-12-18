---
title: "tmpnam_s, _wtmpnam_s | Microsoft Docs"
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
  - "tmpnam_s"
  - "_wtmpnam_s"
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
  - "tmpnam_s"
  - "_wtmpnam_s"
  - "L_tmpnam_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_wtmpnam_s (fonction)"
  - "noms de fichiers (C++), créer temporaire"
  - "noms de fichiers (C++), temporaires"
  - "L_tmpnam_s (constante)"
  - "fichiers temporaires, créer"
  - "tmpnam_s (fonction)"
  - "wtmpnam_s (fonction)"
ms.assetid: e70d76dc-49f5-4aee-bfa2-f1baa2bcd29f
caps.latest.revision: 20
caps.handback.revision: 20
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tmpnam_s, _wtmpnam_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Génére des noms que vous pouvez utiliser pour créer des fichiers temporaires.  Il s'agit de versions de [](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md "_tempnam, _wtempnam, tmpnam, _wtmpnam")[Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t tmpnam_s(  
   char * str,  
   size_t sizeInChars   
);  
errno_t _wtmpnam_s(  
   wchar_t *str,  
   size_t sizeInChars   
);  
template <size_t size>  
errno_t tmpnam_s(  
   char (&str)[size]  
); // C++ only  
template <size_t size>  
errno_t _wtmpnam_s(  
   wchar_t (&str)[size]  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `str`  
 Pointeur qui contiendra le nom généré.  
  
 \[in\] `sizeInChars`  
 La taille en nombre de caractères de la mémoire tampon.  
  
## Valeur de retour  
 Ces deux fonctions retournent 0 en cas de réussite ou un numéro d'erreur en cas de échec.  
  
### Conditions d'erreur  
  
|||||  
|-|-|-|-|  
|`str`|`sizeInChars`|**Valeur de retour**|**Contenu de** `str`|  
|`NULL`|any|`EINVAL`|non modifié|  
|Non  `NULL` \(pointe vers de la mémoire valide\)|trop court|`ERANGE`|non modifié|  
  
 Si `str` est `NULL`, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions définissent `errno` à la valeur `EINVAL` et retournent `EINVAL`.  
  
## Notes  
 Chacune de ces fonctions retourne le nom d'un fichier qui n'existe pas.  `tmpnam_s` retourne un nom unique dans le répertoire de travail actuel.  Notez que lorsqu'un nom de fichier est ajouté au début avec une barre oblique inverse et sans informations de chemin d'accès, par exempl comme \\fname21, cela indique que le nom est valide pour le répertoire de travail actuel.  
  
 Pour `tmpnam_s`, vous pouvez stocker le nom de fichier généré dans `str`.  La longueur maximale d'une chaîne retournée par `tmpnam_s` est `L_tmpnam_s`, défini dans. STDIO.H.  Si `str` est `NULL`, alors `tmpnam_s` laisse le résultat dans un tampon interne statique.  Par conséquent tout appel à cette meme fonction par la suite détruit cette valeur  Le nom généré par `tmpnam_s` se compose d'un nom de fichier programme généré et, après le premier appel à `tmpnam_s`, d'une extension de fichier composée des numéros séquentiels en base 32 \(.1\-.1vvvvvu, lorsque `TMP_MAX_S` dans STDIO.H est INT\_MAX\).  
  
 `tmpnam_s` gère automatiquement les arguments de chaîne de caractères multi\-octets comme approprié, identifiant des séquences de caractères multioctets selon la page de codes OEM extraite du système d'exploitation.  `_wtmpnam_s` est une version caractères larges de `tmpnam_s`; l'argument et la valeur de retour de  `_wtmpnam_s` sont des chaînes de caractères larges.  `_wtmpnam_s` et `tmpnam_s` se comportent de la même manière que `_wtmpnam_s` mais ne gèrent pas les chaînes de caractères multi\-octets.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par des surcharges de modèle ; les surcharges peuvent également déduire la longueur de la mémoire tampon automatiquement, en éliminant le besoin de spécifier un argument de taille.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_ttmpnam_s`|`tmpnam_s`|`tmpnam_s`|`_wtmpnam_s`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`tmpnam_s`|\<stdio.h\>|  
|`_wtmpnam_s`|\<stdio.h\> ou \<wchar.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
```  
// crt_tmpnam_s.c  
// This program uses tmpnam_s to create a unique filename in the  
// current working directory.   
//  
  
#include <stdio.h>  
#include <stdlib.h>  
  
int main( void )  
{     
   char name1[L_tmpnam_s];  
   errno_t err;  
   int i;  
  
   for (i = 0; i < 15; i++)  
   {  
      err = tmpnam_s( name1, L_tmpnam_s );  
      if (err)  
      {  
         printf("Error occurred creating unique filename.\n");  
         exit(1);  
      }  
      else  
      {  
         printf( "%s is safe to use as a temporary file.\n", name1 );  
      }  
   }    
}  
```  
  
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_getmbcp](../../c-runtime-library/reference/getmbcp.md)   
 [malloc](../../c-runtime-library/reference/malloc.md)   
 [\_setmbcp](../../c-runtime-library/reference/setmbcp.md)   
 [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md)