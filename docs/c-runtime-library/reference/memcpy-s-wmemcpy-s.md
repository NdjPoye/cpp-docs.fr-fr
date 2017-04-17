---
title: memcpy_s, wmemcpy_s | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- memcpy_s
- wmemcpy_s
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
- api-ms-win-crt-string-l1-1-0.dll
apitype: DLLExport
f1_keywords:
- wmemcpy_s
- memcpy_s
dev_langs:
- C++
helpviewer_keywords:
- memcpy_s function
- wmemcpy_s function
ms.assetid: 5504e20a-83d9-4063-91fc-3f55f7dabe99
caps.latest.revision: 27
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.mt:
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 38381578b8a8bd66c857d26d12a775f2af702611
ms.lasthandoff: 02/24/2017

---
# <a name="memcpys-wmemcpys"></a>memcpy_s, wmemcpy_s
Copie des octets entre les mémoires tampon. Ces versions de [memcpy, wmemcpy](../../c-runtime-library/reference/memcpy-wmemcpy.md) intègrent les améliorations de sécurité décrites dans [Fonctionnalités de sécurité dans le CRT](../../c-runtime-library/security-features-in-the-crt.md).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
errno_t memcpy_s(  
   void *dest,  
   size_t destSize,  
   const void *src,  
   size_t count   
);  
errno_t wmemcpy_s(  
   wchar_t *dest,  
   size_t destSize,  
   const wchar_t *src,  
   size_t count  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `dest`  
 Nouvelle mémoire tampon.  
  
 `destSize`  
 Taille de la mémoire tampon de destination, en octets dans le cas de memcpy_s et en caractères larges (wchar_t) dans le cas de wmemcpy_s.  
  
 `src`  
 Mémoire tampon à partir de laquelle effectuer la copie.  
  
 `count`  
 Nombre de caractères à copier.  
  
## <a name="return-value"></a>Valeur de retour  
 Zéro si l'opération a réussi ; code d'erreur en cas de échec.  
  
### <a name="error-conditions"></a>Conditions d’erreur  
  
|`dest`|`destSize`|`src`|`count`|Valeur de retour|Contenu de `dest`|  
|------------|----------------|-----------|---|------------------|------------------------|  
|any|any|any|0|0|Non modifié|  
|`NULL`|any|any|Différent de zéro|`EINVAL`|Non modifié|  
|any|any|`NULL`|Différent de zéro|`EINVAL`|`dest` est effacé|  
|any|< `count`|any|Différent de zéro|`ERANGE`|`dest` est effacé|  
  
## <a name="remarks"></a>Notes  
 `memcpy_s` copie `count` octets de `src` vers `dest` ; `wmemcpy_s` copie `count` caractères larges (sur deux octets). Si la source et la destination se chevauchent, le comportement de `memcpy_s` n'est pas défini. Utilisez `memmove_s` pour gérer les régions qui se chevauchent.  
  
 Ces fonctions valident leurs paramètres. Si `count` est différent de zéro, que `dest` ou `src` est un pointeur Null ou que `destSize` est inférieur à `count`, ces fonctions appellent le gestionnaire de paramètres non valides, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, ces fonctions retournent `EINVAL` ou `ERANGE` et définissent `errno` sur la valeur de retour.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`memcpy_s`|\<memory.h> ou \<string.h>|  
|`wmemcpy_s`|\<wchar.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
  
```  
// crt_memcpy_s.c  
// Copy memory in a more secure way.  
  
#include <memory.h>  
#include <stdio.h>  
  
int main()  
{  
   int a1[10], a2[100], i;  
   errno_t err;  
  
   // Populate a2 with squares of integers  
   for (i = 0; i < 100; i++)  
   {  
      a2[i] = i*i;  
   }  
  
   // Tell memcpy_s to copy 10 ints (40 bytes), giving  
   // the size of the a1 array (also 40 bytes).  
   err = memcpy_s(a1, sizeof(a1), a2, 10 * sizeof (int) );      
   if (err)  
   {  
      printf("Error executing memcpy_s.\n");  
   }  
   else  
   {  
     for (i = 0; i < 10; i++)  
       printf("%d ", a1[i]);  
   }  
   printf("\n");  
}  
```  
  
```Output  
0 1 4 9 16 25 36 49 64 81   
```  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Manipulation de la mémoire tampon](../../c-runtime-library/buffer-manipulation.md)   
 [_memccpy](../../c-runtime-library/reference/memccpy.md)   
 [memchr, wmemchr](../../c-runtime-library/reference/memchr-wmemchr.md)   
 [memcmp, wmemcmp](../../c-runtime-library/reference/memcmp-wmemcmp.md)   
 [memmove, wmemmove](../../c-runtime-library/reference/memmove-wmemmove.md)   
 [memset, wmemset](../../c-runtime-library/reference/memset-wmemset.md)   
 [strcpy, wcscpy, _mbscpy](../../c-runtime-library/reference/strcpy-wcscpy-mbscpy.md)   
 [strncpy, _strncpy_l, wcsncpy, _wcsncpy_l, _mbsncpy, _mbsncpy_l](../../c-runtime-library/reference/strncpy-strncpy-l-wcsncpy-wcsncpy-l-mbsncpy-mbsncpy-l.md)   
 [strncpy_s, _strncpy_s_l, wcsncpy_s, _wcsncpy_s_l, _mbsncpy_s, _mbsncpy_s_l](../../c-runtime-library/reference/strncpy-s-strncpy-s-l-wcsncpy-s-wcsncpy-s-l-mbsncpy-s-mbsncpy-s-l.md)