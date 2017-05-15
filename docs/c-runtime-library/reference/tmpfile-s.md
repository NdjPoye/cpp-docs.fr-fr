---
title: tmpfile_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- tmpfile_s
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
- tmpfile_s
dev_langs:
- C++
helpviewer_keywords:
- temporary files
- tmpfile_s function
- temporary files, creating
ms.assetid: 50879c69-215e-425a-a2a3-8b5467121eae
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e66ffa5fdbb1785191865eba92c9d673fb847ada
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="tmpfiles"></a>tmpfile_s
Crée un fichier temporaire. Il s’agit d’une version de [tmpfile](../../c-runtime-library/reference/tmpfile.md) assortie des améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t tmpfile_s(  
   FILE** pFilePtr  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [out] `pFilePtr`  
 Adresse d’un pointeur pour stocker l’adresse du pointeur généré désignant un flux.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne 0 si l’opération aboutit et un code d’erreur en cas d’échec.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`pFilePtr`|**Valeur de retour**|**Contenu de**  `pFilePtr`|  
|----------------|----------------------|---------------------------------|  
|`NULL`|`EINVAL`|inchangé|  
  
 Si l’erreur de validation de paramètre ci-dessus se produit, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, `errno` prend la valeur `EINVAL` et la valeur de retour est `EINVAL`.  
  
## <a name="remarks"></a>Notes  
 La fonction `tmpfile_s` crée un fichier temporaire et place un pointeur vers ce flux dans l’argument `pFilePtr`. Le fichier temporaire est créé dans le répertoire racine. Pour créer un fichier temporaire dans un répertoire autre que la racine, utilisez [tmpnam_s](../../c-runtime-library/reference/tmpnam-s-wtmpnam-s.md) ou [tempnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md) en association avec [fopen](../../c-runtime-library/reference/fopen-wfopen.md).  
  
 Si le fichier ne peut pas être ouvert, `tmpfile_s` écrit `NULL` dans le paramètre `pFilePtr`. Ce fichier temporaire est supprimé automatiquement à la fermeture du fichier, quand le programme se termine normalement ou lorsque la fonction `_rmtmp` est appelée, dans la mesure où le répertoire de travail actif ne change pas. Le fichier temporaire est ouvert en mode `w+b` (lecture/écriture binaire).  
  
 Un échec peut se produire si vous tentez plus de `tmpfile_s.` (consultez STDIO.H) appels avec `TMP_MAX_S`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`tmpfile_s`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
> [!NOTE]
>  L’exécution de cet exemple sur Windows Vista nécessite des privilèges d’administrateur.  
  
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
  
```Output  
Temporary file 1 was created  
Temporary file 2 was created  
Temporary file 3 was created  
3 temporary files deleted  
```  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)   
 [_rmtmp](../../c-runtime-library/reference/rmtmp.md)   
 [_tempnam, _wtempnam, tmpnam, _wtmpnam](../../c-runtime-library/reference/tempnam-wtempnam-tmpnam-wtmpnam.md)
