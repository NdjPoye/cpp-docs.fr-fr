---
title: tmpfile | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpfile
apilocation:
- msvcrt.dll
- msvcr80.dll
- msvcr90.dll
- msvcr100.dll
- msvcr100_clr0400.dll
- msvcr110.dll
- msvcr110_clr0400.dll
- msvcr120.dll
- msvcr120_clr0400.dll
- ucrtbase.dll
- api-ms-win-crt-stdio-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- tmpfile
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile function
- temporary files, creating
ms.assetid: c4a4dc24-70da-438d-ae4e-98352d88e375
caps.latest.revision: 21
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- ru-ru
- zh-cn
- zh-tw
translation.priority.mt:
- cs-cz
- pl-pl
- pt-br
- tr-tr
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 05edefa97701ebd70d86ff4fc78dc6cee7f083fa
ms.lasthandoff: 02/24/2017

---
# <a name="tmpfile"></a>tmpfile
Crée un fichier temporaire. Cette fonction est dépréciée, car il en existe une version plus sécurisée. Consultez [tmpfile_s](../../c-runtime-library/reference/tmpfile-s.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
FILE *tmpfile( void );  
```  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, `tmpfile` retourne un pointeur de flux. Sinon, elle retourne un pointeur `NULL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `tmpfile` crée un fichier temporaire et retourne un pointeur désignant ce flux. Le fichier temporaire est créé dans le répertoire racine. Pour créer un fichier temporaire dans un répertoire autre que la racine, utilisez [tmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) ou [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) en association avec [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Si le fichier ne peut pas être ouvert, `tmpfile` retourne un pointeur `NULL`. Ce fichier temporaire est supprimé automatiquement à la fermeture du fichier, quand le programme se termine normalement ou lorsque la fonction `_rmtmp` est appelée, dans la mesure où le répertoire de travail actif ne change pas. Le fichier temporaire est ouvert en mode `w+b` (lecture/écriture binaire).  
  
 Un échec peut se produire si vous tentez plus de TMP_MAX (voir STDIO.H) appels avec `tmpfile`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`tmpfile`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
> [!NOTE]
>  L’exécution de cet exemple sur Windows Vista nécessite des privilèges d’administrateur.  
  
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
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)
