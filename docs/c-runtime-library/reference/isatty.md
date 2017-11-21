---
title: _isatty | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname: _isatty
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
f1_keywords: _isatty
dev_langs: C++
helpviewer_keywords:
- isatty function
- character device checking
- _isatty function
- checking character devices
ms.assetid: 9f1b2e87-0cd7-4079-b187-f2b7ca15fcbe
caps.latest.revision: "18"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 39e8b9520672c676ffec470ab2e89fccdfaf3442
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="isatty"></a>_isatty
Détermine si un descripteur de fichier est associé à un périphérique de caractères.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      int _isatty(  
int fd   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `fd`  
 Descripteur de fichier qui fait référence au périphérique à tester.  
  
## <a name="return-value"></a>Valeur de retour  
 `_isatty` retourne une valeur différente de zéro si le descripteur est associé à un périphérique de caractères. Sinon, `_isatty` retourne 0.  
  
## <a name="remarks"></a>Notes  
 La fonction `_isatty` détermine si `fd` est associé à un périphérique de caractères (terminal, console, imprimante ou port série).  
  
 Cette fonction valide le paramètre `fd`. Si `fd` est un pointeur de fichier non valide, le gestionnaire de paramètres non valides est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, la fonction retourne 0 et définit `errno` sur `EBADF`.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_isatty`|\<io.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md).  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
  
```  
// crt_isatty.c  
/* This program checks to see whether  
 * stdout has been redirected to a file.  
 */  
  
#include <stdio.h>  
#include <io.h>  
  
int main( void )  
{  
   if( _isatty( _fileno( stdout ) ) )  
      printf( "stdout has not been redirected to a file\n" );  
   else  
      printf( "stdout has been redirected to a file\n");  
}  
```  
  
## <a name="sample-output"></a>Résultat de l'exemple  
  
```  
stdout has not been redirected to a file  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Gestion de fichiers](../../c-runtime-library/file-handling.md)