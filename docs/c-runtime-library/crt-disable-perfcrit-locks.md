---
title: _CRT_DISABLE_PERFCRIT_LOCKS | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _CRT_DISABLE_PERFCRIT_LOCKS
- CRT_DISABLE_PERFCRIT_LOCKS
dev_langs:
- C++
helpviewer_keywords:
- CRT_DISABLE_PERFCRIT_LOCKS constant
- _CRT_DISABLE_PERFCRIT_LOCKS constant
ms.assetid: 36cc2d86-cdb1-4b2b-a03c-c0d3818e7c6f
caps.latest.revision: 4
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
ms.openlocfilehash: c88428931b84b996ee711eb17fd42190a2c20e15
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="crtdisableperfcritlocks"></a>_(CRT)_DISABLE_PERFCRIT_LOCKS
Désactive le verrouillage critique pour les performances dans les opérations d’E/S.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
#define _CRT_DISABLE_PERFCRIT_LOCKS  
```  
  
## <a name="remarks"></a>Remarques  
 Définir ce symbole peut améliorer les performances dans les programmes monothreads utilisant des E/S en forçant toutes les opérations d’E/S à considérer que le modèle d’E/S est monothread. Pour plus d'informations, consultez [Performances des bibliothèques multithreads](../c-runtime-library/multithreaded-libraries-performance.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Constantes globales](../c-runtime-library/global-constants.md)