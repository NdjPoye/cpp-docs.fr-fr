---
title: "tmpfile_s | Microsoft Docs"
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
  - "tmpfile_s"
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
  - "tmpfile_s"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fichiers temporaires"
  - "tmpfile_s (fonction)"
  - "fichiers temporaires, créer"
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: 20
caps.handback.revision: 18
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tmpfile_s
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un fichier temporaire.  Il s'agit d'une versions de [tmpfile](../../c-runtime-library/reference/tmpfile.md) avec des améliorations de sécurité, comme décrit dans[Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## Syntaxe  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### Paramètres  
 \[out\] `pFilePtr`  
 L'adresse d'un pointeur pour stocker l'adresse du pointeur généré vers une source de données.  
  
## Valeur de retour  
 Retourne zéro si l'opération a réussi, un code d'erreur en cas de échec.  
  
### Conditions d'erreur  
  
|`pFilePtr`|**Valeur de retour**|**Contenu de** `pFilePtr`|  
|----------------|--------------------------|-------------------------------|  
|`NULL`|`EINVAL`|non modifié|  
  
 Si l'une de ces erreurs de validation de paramètre ci\-dessus se produit, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  Si l'exécution est autorisée à se poursuivre, `errno` est fixé à `EINVAL` et la valeur de retour est `EINVAL`.  
  
## Notes  
 La fonction `tmpfile_s` crée un fichier temporaire et met un pointeur vers le flux de données dans l'argument `pFilePtr`.  Le fichier temporaire est créé dans le répertoire racine.  Pour créer un fichier temporaire dans un répertoire autre que la racine, utilisez [tmpnam\_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) ou [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) conjointement avec [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Si le fichier ne peut pas être ouvert, `tmpfile_s` écrit `NULL` pour le paramètre `pFilePtr`.  Ce fichier temporaire est automatiquement supprimé lorsque le fichier est fermé, lorsque le programme se termine normalement, ou lorsque `_rmtmp` est appelé, en supposant que le répertoire de travail actuel ne change pas.  Le fichier temporaire est ouvert en mode `w+b` \(lecture\/écriture binaire\).  
  
 L'erreur peut se produire si vous tentez plus de `TMP_MAX_S` \(voir STDIO.H\) appels avec `TMP_MAX_S`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`tmpfile_s`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
> [!NOTE]
>  Cet exemple requiert l'exécution des privilèges d'administrateur sous Windows Vista.  
  
```  
// crt_tmpfile_s.c  
// This program uses tmpfile_s to create a  
// temporary file, then deletes this file with _rmtmp.  
//  
  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   char tempstring[] = "String to be written";  
   int  i;  
   errno_t err;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      err = tmpfile_s(&stream);  
      if( err )  
         perror( "Could not open new temporary file\n" );  
      else  
         printf( "Temporary file %d was created\n", i );  
   }  
  
   // Remove temporary files.  
   printf( "%d temporary files deleted\n", _rmtmp() );  
}  
```  
  
  **Le fichier temporaire 1 a été créé**  
**Le fichier temporaire 2 a été créé**  
**Le fichier temporaire 3 a été créé**  
**3 fichiers temporaires supprimés**   
## Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d'informations, consultez [Exemples d'appel de plateforme](../Topic/Platform%20Invoke%20Examples.md).  
  
## Voir aussi  
 [E\/S de flux](../../c-runtime-library/stream-i-o.md)   
 [\_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [\_tempnam, \_wtempnam, tmpnam, \_wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)