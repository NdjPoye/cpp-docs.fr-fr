---
title: _swab | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _swab
- stdlib/_swab
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
- api-ms-win-crt-utility-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- _swab
- stdlib/_swab
dev_langs:
- C++
helpviewer_keywords:
- _swab function
- swapping bytes
- swab function
- bytes, swapping
ms.assetid: 017142f2-050c-4f6a-8b49-6b094f58ec94
caps.latest.revision: 18
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 0c7e2bdc77ff1dc91847e02ec9e5a92363b64c2c
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="swab"></a>_swab
Échange des octets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void _swab(  
   char *src,  
   char *dest,  
   int n   
);  
```  
  
## <a name="parameters"></a>Paramètres  
 `src`  
 Données à copier et échanger.  
  
 `dest`  
 Emplacement de stockage des données échangées.  
  
 `n`  
 Nombre d’octets à copier et échanger.  
  
## <a name="return-value"></a>Valeur de retour
 La fonction `swab` ne retourne pas de valeur. La fonction affecte à `errno` la valeur `EINVAL` si le pointeur `src` ou `dest` a la valeur Null ou si `n` est inférieur à zéro, et le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md).  
  
 Pour plus d’informations sur ce code de retour et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).
 
## <a name="remarks"></a>Notes  
 Si `n` est pair, la fonction `_swab` copies `n` octets à partir de `src`, échange chaque paire d’octets adjacents et stocke le résultat au niveau de `dest`. Si `n` est impair, `_swab` copie et échange les `n-1` premiers octets de `src`, et le dernier octet n’est pas copié. La fonction `_swab` sert généralement à préparer le transfert de données binaires vers un ordinateur qui utilise un ordre d’octet différent.  
  
## <a name="requirements"></a>Spécifications  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_swab`|C : \<stdlib.h> C++ : \<cstdlib> ou \<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
```C 
// crt_swab.c  
  
#include <stdlib.h>  
#include <stdio.h>  
  
char from[] = "BADCFEHGJILKNMPORQTSVUXWZY";  
char to[] =   "...........................";  
  
int main()  
{  
    printf("Before: %s  %d bytes\n        %s\n\n", from, sizeof(from), to);  
    _swab(from, to, sizeof(from));  
    printf("After:  %s\n        %s\n\n", from, to);  
}  
```  
  
```Output  
Before: BADCFEHGJILKNMPORQTSVUXWZY  27 bytes  
        ...........................  
  
After:  BADCFEHGJILKNMPORQTSVUXWZY  
        ABCDEFGHIJKLMNOPQRSTUVWXYZ.  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de la mémoire tampon](../../c-runtime-library/buffer-manipulation.md)
