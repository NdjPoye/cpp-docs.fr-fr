---
title: "gets_s, _getws_s | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apiname: 
  - "_getws_s"
  - "gets_s"
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
  - "_getws_s"
  - "gets_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "_getws_s (fonction)"
  - "dépassements de mémoire tampon"
  - "mémoires tampons, éviter les dépassements"
  - "mémoires tampons, dépassements de mémoire tampon"
  - "gets_s (fonction)"
  - "getws_s (fonction)"
  - "lignes, obtenir"
  - "entrée standard, lire dans"
  - "flux, obtenir des lignes"
ms.assetid: 5880c36f-122c-4061-a1a5-aeeced6fe58c
caps.latest.revision: 29
caps.handback.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# gets_s, _getws_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère une ligne du flux `stdin`.  Ces versions de [gets, \_getws](../../c-runtime-library/gets-getws.md) présentent des améliorations dans la sécurité, comme décrit dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
char *gets_s(   
   char *buffer,  
   size_t sizeInCharacters  
);  
wchar_t *_getws_s(   
   wchar_t *buffer,  
   size_t sizeInCharacters  
);  
template <size_t size>  
char *gets_s(   
   char (&buffer)[size]  
); // C++ only  
template <size_t size>  
wchar_t *_getws_s(   
   wchar_t (&buffer)[size]  
); // C++ only  
```  
  
#### Paramètres  
 \[out\] `buffer`  
 Emplacement de stockage de la chaîne d'entrée.  
  
 \[in\] `sizeInCharacters`  
 Taille de la mémoire tampon.  
  
## Valeur de retour  
 En cas de réussite, retourne `buffer`.  Un pointeur `NULL` indique une erreur ou une condition de fin de fichier.  Utilisez [ferror](../../c-runtime-library/reference/ferror.md) ou [feof](../../c-runtime-library/reference/feof.md) pour déterminer laquelle s'est produite.  
  
## Notes  
 La fonction `gets_s` lit une ligne du flux d'entrée standard `stdin` et la stocke dans `buffer`.  La ligne se compose de tous les caractère jusqu'au premier caractère de saut de ligne \("\\n "\) inclus.  `gets_s` remplace ensuite le caractère de saut de ligne par un caractère Null \("\\0 "\) avant de retourner la ligne.  En revanche, la fonction `fgets_s` conserve le caractère de nouvelle ligne.  
  
 Si la première lecture de caractère est le caractère de fin de fichier, un caractère Null est enregistré au début du `buffer` et `NULL` est retourné.  
  
 `_getws` est une version caractères larges `gets_s`; son argument et la valeur de retour sont des chaînes de caractères larges.  
  
 Si `buffer` est `NULL` ou `sizeInCharacters` est inférieur ou égal à zéro, ou si la mémoire tampon est trop petite pour contenir la ligne d'entrée et le terminateur null, ces fonctions appellent un gestionnaire de paramètre non valide, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, ces fonctions retournent `NULL` et définissent erno à la valeur `ERANGE`.  
  
 En C\+\+, l'utilisation de ces fonctions est simplifiée par les surcharges de modèle ; les surcharges peuvent déduire la longueur de la mémoire tampon automatiquement \(ce qui évite d'avoir à spécifier un argument taille\) et peuvent remplacer automatiquement les fonctions plus anciennes et non sécurisées par leurs équivalentes plus récentes et sécurisées.  Pour plus d'informations, consultez [Sécuriser les surcharges de modèle](../../c-runtime-library/secure-template-overloads.md).  
  
### Mappages de routines de texte générique  
  
|Routine TCHAR.H|\_UNICODE & \_MBCS non définis|\_MBCS défini|\_UNICODE défini|  
|---------------------|------------------------------------|-------------------|----------------------|  
|`_getts`|`gets_s`|`gets_s`|`_getws`|  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`gets_s`|\<stdio.h\>|  
|`_getws`|\<stdio.h\> ou \<wchar.h\>|  
  
 La console n'est pas prise en charge dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Les handles de flux standard associés à la console, `stdin`, `stdout` et `stderr` doivent être redirigés pour que les fonctions runtime C puissent les utiliser dans les applications [!INCLUDE[win8_appname_long](../../build/includes/win8_appname_long_md.md)] .  Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## Exemple  
  
```  
// crt_gets_s.c  
// This program retrieves a string from the stdin and   
// prints the same string to the console.  
  
#include <stdio.h>  
  
int main( void )  
{  
   char line[21]; // room for 20 chars + '\0'  
   gets_s( line, 20 );  
   printf( "The line entered was: %s\n", line );  
}  
```  
  
  **`Bonjour à vous !`la ligne entrée était : Bonjour à vous \!**   
## Équivalent .NET Framework  
 [System::Console::Read](https://msdn.microsoft.com/en-us/library/system.console.read.aspx)  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [gets, \_getws](../../c-runtime-library/gets-getws.md)   
 [fgets, fgetws](../../c-runtime-library/reference/fgets-fgetws.md)   
 [fputs, fputws](../../c-runtime-library/reference/fputs-fputws.md)   
 [puts, \_putws](../../c-runtime-library/reference/puts-putws.md)