---
title: offsetof Macro | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
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
f1_keywords: offsetof
dev_langs: C++
helpviewer_keywords:
- structure members, offset
- offsetof macro
ms.assetid: f3b4eb16-a882-4d38-afc9-eebd976a7352
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 47243b64519540397573a47180dca5eed25f4c57
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="offsetof-macro"></a>offsetof, macro
Récupère le décalage d'un membre au début de sa structure parent.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      size_t offsetof(  
   structName,  
   memberName   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 *structName*  
 Nom de la structure de données parent.  
  
 `memberName`  
 Nom du membre dans la structure de données parent pour lequel le décalage doit être déterminé.  
  
## <a name="return-value"></a>Valeur de retour  
 `offsetof` retourne le décalage en octets du membre spécifié au début de sa structure de données parent. Il n'est pas défini pour les champs de bits.  
  
## <a name="remarks"></a>Notes  
 La macro `offsetof` retourne le décalage en octets de `memberName` à partir du début de la structure spécifiée par *structName* sous forme de valeur de type `size_t`. Vous pouvez spécifier les types avec le mot clé `struct`.  
  
> [!NOTE]
>  `offsetof` n'est pas une fonction et ne peut pas être décrite à l'aide d'un prototype C.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`offsetof`|\<stddef.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="libraries"></a>Bibliothèques  
 Toutes les versions des [bibliothèques Runtime C](../../c-runtime-library/crt-library-features.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Allocation de mémoire](../../c-runtime-library/memory-allocation.md)