---
title: _CrtIsMemoryBlock | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- _CrtIsMemoryBlock
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
apitype: DLLExport
f1_keywords:
- CrtlsMemoryBlock
- _CrtIsMemoryBlock
dev_langs:
- C++
helpviewer_keywords:
- _CrtIsMemoryBlock function
- CrtIsMemoryBlock function
ms.assetid: f7cbbc60-3690-4da0-a07b-68fd7f250273
caps.latest.revision: 14
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
ms.openlocfilehash: e884526e45e4bb8fbf1070fca8fd740d692dc285
ms.lasthandoff: 02/24/2017

---
# <a name="crtismemoryblock"></a>_CrtIsMemoryBlock
Vérifie qu’un bloc de mémoire spécifié est dans le tas local et qu’il a un identificateur de type de bloc de tas de débogage valide (version de débogage uniquement).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int _CrtIsMemoryBlock(   
   const void *userData,  
   unsigned int size,  
   long *requestNumber,  
   char **filename,  
   int *linenumber   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 [in] `userData`  
 Pointeur indiquant le début d’un bloc de mémoire à vérifier.  
  
 [in] `size`  
 Taille du bloc spécifié (en octets).  
  
 [out] `requestNumber`  
 Pointeur désignant le numéro d’allocation du bloc ou `NULL`.  
  
 [out] `filename`  
 Pointeur désignant le nom du fichier source qui a demandé le bloc ou `NULL`.  
  
 [out] `linenumber`  
 Pointeur désignant le numéro de ligne dans le fichier source ou `NULL`.  
  
## <a name="return-value"></a>Valeur de retour  
 `_CrtIsMemoryBlock` retourne `TRUE` si le bloc de mémoire spécifié se trouve dans le tas local et qu’il a un identificateur de type de bloc de tas de débogage valide ; sinon, la fonction retourne `FALSE`.  
  
## <a name="remarks"></a>Notes  
 La fonction `_CrtIsMemoryBlock` vérifie qu’un bloc de mémoire spécifié est dans le tas local de l’application et qu’il a un identificateur de type de bloc valide. Cette fonction peut également être utilisée pour obtenir le numéro d’ordre d’allocation d’objet et le numéro de ligne/nom du fichier source où l’allocation de bloc de mémoire a été initialement demandée. Si des valeurs non NULL sont passées pour les paramètres `requestNumber`, `filename` ou `linenumber`, `_CrtIsMemoryBlock` définit ces paramètres sur les valeurs dans l’en-tête de débogage du bloc de mémoire, s’il trouve le bloc dans le tas local. Quand [_DEBUG](../../c-runtime-library/debug.md) n’est pas défini, les appels à `_CrtIsMemoryBlock` sont supprimés durant le prétraitement.  
  
 Si `_CrtIsMemoryBlock` échoue, il retourne `FALSE` et les paramètres de sortie sont initialisés aux valeurs par défaut : `requestNumber` et `lineNumber` sont définis sur 0 et `filename` est défini sur `NULL`.  
  
 Comme cette fonction retourne `TRUE` ou `FALSE`, elle peut être passée à l’une des macros [_ASSERT](../../c-runtime-library/reference/assert-asserte-assert-expr-macros.md) pour créer un mécanisme de gestion des erreurs de débogage simple. L'exemple suivant provoque un échec d'assertion si l'adresse spécifiée n'est pas située dans le tas local :  
  
```  
_ASSERTE( _CrtIsMemoryBlock( userData, size, &requestNumber,   
&filename, &linenumber ) );  
```  
  
 Pour plus d’informations sur la façon dont `_CrtIsMemoryBlock` peut être utilisé avec d’autres macros et fonctions de débogage, consultez [Macros pour la création de rapports](/visualstudio/debugger/macros-for-reporting). Pour plus d’informations sur la façon dont les blocs de mémoire sont alloués, initialisés et gérés dans la version de débogage du tas de base, consultez [Détails du tas de débogage CRT](/visualstudio/debugger/crt-debug-heap-details).  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`_CrtIsMemoryBlock`|\<crtdbg.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Uniquement les versions de débogage des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="example"></a>Exemple  
 Voir l’exemple pour la rubrique [_CrtIsValidHeapPointer](../../c-runtime-library/reference/crtisvalidheappointer.md).  
  
## <a name="net-framework-equivalent"></a>Équivalent .NET Framework  
 Non applicable. Pour appeler la fonction C standard, utilisez `PInvoke`. Pour plus d’informations, consultez [Exemples d’appel de plateforme](http://msdn.microsoft.com/Library/15926806-f0b7-487e-93a6-4e9367ec689f).  
  
## <a name="see-also"></a>Voir aussi  
 [Routines de débogage](../../c-runtime-library/debug-routines.md)