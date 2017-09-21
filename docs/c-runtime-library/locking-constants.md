---
title: Constantes _locking | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _LK_RLCK
- _LK_NBLCK
- _LK_LOCK
- _LK_NBRLCK
- _LK_UNLCK
dev_langs:
- C++
helpviewer_keywords:
- LK_UNLCK constant
- LK_NBRLCK constant
- _LK_NBRLCK constant
- _LK_NBLCK constant
- _LK_LOCK constant
- LK_NBLCK constant
- _LK_UNLCK constant
- LK_RLCK constant
- _LK_RLCK constant
- LK_LOCK constant
ms.assetid: c3dc92c8-60e3-4d29-9f50-5d217627c8ad
caps.latest.revision: 7
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
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: 6e023de61dac5679d6c46c89b57255eef0b34c76
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="locking-constants"></a>_locking, constantes
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <sys/locking.h>  
  
```  
  
## <a name="remarks"></a>Remarques  
 L’argument *mode* dans l’appel à la fonction `_locking` spécifie l’action de verrouillage à effectuer.  
  
 L’argument *mode* doit être une des constantes manifestes suivantes.  
  
 `_LK_LOCK`  
 Verrouille les octets spécifiés. Si les octets ne peuvent pas être verrouillés, le la fonction réessaye après 1 seconde. Si, après 10 tentatives, les octets ne peuvent pas être verrouillés, la fonction retourne une erreur.  
  
 `_LK_RLCK`  
 Comme pour `_LK_LOCK`.  
  
 `_LK_NBLCK`  
 Verrouille les octets spécifiés. Si les octets ne peuvent pas être verrouillés, la fonction retourne une erreur.  
  
 `_LK_NBRLCK`  
 Comme pour `_LK_NBLCK`.  
  
 `_LK_UNLCK`  
 Déverrouille les octets spécifiés. (Les octets doivent avoir été préalablement verrouillés.)  
  
## <a name="see-also"></a>Voir aussi  
 [_locking](../c-runtime-library/reference/locking.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)