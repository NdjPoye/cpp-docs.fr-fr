---
title: "tmpfile | Microsoft Docs"
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
  - "tmpfile"
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
  - "tmpfile"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "fichiers temporaires"
  - "tmpfile, fonction"
  - "fichiers temporaires, créer"
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
caps.handback.revision: 19
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# tmpfile
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Crée un fichier temporaire.  Cette fonction est déconseillée parce qu'une version plus sécurisée est disponible ; consultez [tmpfile\_s](../../c-runtime-library/reference/tmpfile-s.md).  
  
## Syntaxe  
  
```  
FILE *tmpfile( void );  
```  
  
## Valeur de retour  
 En cas de réussite, `tmpfile` retourne un pointeur de flux.  Sinon, retourne un pointeur`NULL` .  
  
## Notes  
 La fonction `tmpfile` crée un fichier temporaire et retourne un pointeur vers ce flux de données.  Le fichier temporaire est créé dans le répertoire racine.  Pour créer un fichier temporaire dans un répertoire autre que la racine, utilisez [tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) ou [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) conjointement avec [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Si le fichier ne peut pas être ouvert, `tmpfile` retourne un pointeur `NULL`.  Ce fichier temporaire est automatiquement supprimé lorsque le fichier est fermé, lorsque le programme se termine normalement, ou lorsque `_rmtmp` est appelé, en supposant que le répertoire de travail actuel ne change pas.  Le fichier temporaire est ouvert en mode `w+b` \(lecture\/écriture binaire\).  
  
 L'erreur peut se produire si vous tentez d'atteindre plus que ce que TMP\_MAX \(voir STDIO.H\) appelle avec `tmpfile`.  
  
## Configuration requise  
  
|Routine|En\-tête requis|  
|-------------|---------------------|  
|`tmpfile`|\<stdio.h\>|  
  
 Pour plus d'informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l'introduction.  
  
## Exemple  
  
> [!NOTE]
>  Cet exemple requiert l'exécution des privilèges d'administrateur sous Windows Vista.  
  
```  
// crt_tmpfile.c  
// compile with: /W3  
// This program uses tmpfile to create a  
// temporary file, then deletes this file with _rmtmp.  
#include <stdio.h>  
  
int main( void )  
{  
   FILE *stream;  
   int  i;  
  
   // Create temporary files.  
   for( i = 1; i <= 3; i++ )  
   {  
      if( (stream = tmpfile()) == NULL ) // C4996  
      // Note: tmpfile is deprecated; consider using tmpfile_s instead  
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