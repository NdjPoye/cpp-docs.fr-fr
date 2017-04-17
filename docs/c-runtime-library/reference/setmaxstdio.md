---
title: _setmaxstdio | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _setmaxstdio
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
- setmaxstdio
- _setmaxstdio
dev_langs:
- C++
helpviewer_keywords:
- maximum open files
- _setmaxstdio function
- setmaxstdio function
- open files, maximum
ms.assetid: 9e966875-9ff5-47c4-9b5f-e79e83b70249
caps.latest.revision: 12
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
translationtype: Machine Translation
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 7947bb8de34b5e80321ddacf03e4606a53b5dc90
ms.lasthandoff: 02/24/2017

---
# <a name="setmaxstdio"></a>_setmaxstdio
Définit un nombre maximal de fichiers ouverts simultanément au niveau `stdio`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _setmaxstdio(  
   int newmax   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `newmax`  
 Nouveau nombre maximal de fichiers ouverts simultanément au niveau `stdio`.  
  
## <a name="return-value"></a>Valeur de retour  
 Retourne `newmax` en cas de réussite ; -1 dans un autre cas.  
  
 Si `newmax` est inférieur à `_IOB_ENTRIES` ou supérieur au nombre maximal de descripteurs disponibles dans le système d’exploitation, le gestionnaire de paramètre non valide est appelé, comme décrit dans [Validation de paramètre](../../c-runtime-library/parameter-validation.md). Si l’exécution est autorisée à se poursuivre, cette fonction retourne -1 et affecte à `errno` la valeur `EINVAL`.  
  
 Pour obtenir des informations sur ces codes d’erreur et les autres, consultez [_doserrno, errno, _sys_errlist et _sys_nerr](../../c-runtime-library/errno-doserrno-sys-errlist-and-sys-nerr.md).  
  
## <a name="remarks"></a>Notes  
 La fonction `_setmaxstdio` modifie la valeur maximale pour le nombre de fichiers pouvant être ouverts simultanément au niveau `stdio`.  
  
 Les E/S du Runtime C prennent désormais en charge beaucoup plus de fichiers ouverts sur les plateformes Win32 que dans les versions précédentes. Jusqu’à 2 048 fichiers peuvent être ouverts simultanément au [niveau lowio](../../c-runtime-library/low-level-i-o.md) (autrement dit, leur ouverture et leur accès s’effectue par le biais de la famille de fonctions d’E/S `_open`, `_read`, `_write`, etc.). Jusqu’à 512 fichiers peuvent être ouverts simultanément au [niveau stdio](../../c-runtime-library/stream-i-o.md) (autrement dit, leur ouverture et leur accès s’effectue par le biais de la famille de fonctions `fopen`, `fgetc`, `fputc`, etc.). La limite de 512 fichiers ouverts au niveau `stdio` peut être portée à un maximum de 2 048 par le biais de la fonction `_setmaxstdio`.  
  
 Sachant que les fonctions de niveau `stdio`, telles que `fopen`, s’appuient sur les fonctions `lowio`, le maximum de 2 048 est une limite supérieure stricte pour le nombre de fichiers ouverts simultanément accessibles via la bibliothèque Runtime C.  
  
> [!NOTE]
>  Il est possible que cette limite supérieure soit au-delà de ce qu’une plateforme et une configuration Win32 particulières peuvent prendre en charge.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_setmaxstdio`|\<stdio.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Pour obtenir un exemple d’utilisation de `_setmaxstdio`, consultez [_getmaxstdio](../../c-runtime-library/reference/getmaxstdio.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [E/S de flux](../../c-runtime-library/stream-i-o.md)