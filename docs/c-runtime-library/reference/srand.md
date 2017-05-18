---
title: srand | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
apiname:
- srand
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
- srand
dev_langs:
- C++
helpviewer_keywords:
- random starting point
- random starting point, setting
- random numbers, generating
- srand function
- numbers, pseudorandom
- numbers, random
- pseudorandom numbers
- starting points, setting random
- starting points
ms.assetid: 7bf56dc5-5692-4182-a3c1-18af98d2dd1a
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: e257f037a05c45f5b98e64ea55bd125af443b0be
ms.openlocfilehash: e86ea8aa561af584a6825d4225820aca7baeced2
ms.contentlocale: fr-fr
ms.lasthandoff: 03/29/2017

---
# <a name="srand"></a>srand
Définit la valeur initiale de départ pour le générateur de nombres pseudo-aléatoires.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void srand(  
   unsigned int seed   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `seed`  
 Valeur initiale pour la génération de nombres pseudo-aléatoires  
  
## <a name="remarks"></a>Notes  
 La fonction `srand` définit le point de départ de la génération d’une série d’entiers pseudo-aléatoires dans le thread actif. Pour réinitialiser le générateur et créer la même séquence de résultats, appelez la fonction `srand` et réutilisez le même argument `seed`. Toute autre valeur pour `seed` attribue au générateur un autre point de départ dans la séquence pseudo-aléatoire. `rand` récupère les nombres pseudo-aléatoires qui sont générés. Le fait d’appeler `rand` avant `srand` a pour effet de générer la même séquence que si vous appelez `srand` en passant `seed` avec la valeur 1.  
  
## <a name="requirements"></a>Spécifications  
  
|Routine|En-tête requis|  
|-------------|---------------------|  
|`srand`|\<stdlib.h>|  
  
 Pour plus d’informations sur la compatibilité, consultez [Compatibilité](../../c-runtime-library/compatibility.md) dans l’introduction.  
  
## <a name="example"></a>Exemple  
 Consultez l’exemple relatif à [rand](../../c-runtime-library/reference/rand.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Prise en charge de la virgule flottante](../../c-runtime-library/floating-point-support.md)   
 [rand](../../c-runtime-library/reference/rand.md)
