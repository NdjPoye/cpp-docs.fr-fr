---
title: Constantes de tas | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-standard-libraries
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- _HEAPBADPTR
- _HEAPEMPTY
- _HEAPBADBEGIN
- _HEAPOK
- _HEAPBADNODE
- _HEAPEND
dev_langs:
- C++
helpviewer_keywords:
- _HEAPOK constants
- _HEAPEND constants
- HEAPBADBEGIN constants
- _HEAPBADNODE constants
- HEAPBADNODE constants
- HEAPBADPTR constants
- _HEAPEMPTY constants
- HEAPEND constants
- HEAPOK constants
- HEAPEMPTY constants
- _HEAPBADBEGIN constants
- _HEAPBADPTR constants
- heap constants
ms.assetid: 3f751bb9-2dc4-486f-b5f5-9061c96d3754
caps.latest.revision: 6
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
ms.openlocfilehash: 378df280df8255b8a8e94656425da1b3c3468dd2
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="heap-constants"></a>Constantes de tas
## <a name="syntax"></a>Syntaxe  
  
```  
  
#include <malloc.h>  
  
```  
  
## <a name="remarks"></a>Remarques  
 Ces constantes donnent la valeur de retour indiquant l’état du tas.  
  
|Constante|Signification|  
|--------------|-------------|  
|`_HEAPBADBEGIN`|Les informations d’en-tête initiales sont introuvables ou ne sont pas valides.|  
|`_HEAPBADNODE`|Un nœud incorrect a été trouvé, ou un segment de mémoire est endommagé.|  
|`_HEAPBADPTR`|Le champ **_pentry** de la structure **_HEAPINFO** ne contient pas de pointeur valide dans le tas (routine `_heapwalk` uniquement).|  
|`_HEAPEMPTY`|Le tas n’a pas été initialisé.|  
|`_HEAPEND`|Fin du segment de mémoire atteinte avec succès (routine `_heapwalk` uniquement).|  
|`_HEAPOK`|Le tas est cohérent (routines `_heapset` et `_heapchk` uniquement). Aucune erreur jusqu'à présent ; la structure **_HEAPINFO** contient des informations sur l’entrée suivante (routine `_heapwalk` uniquement).|  
  
## <a name="see-also"></a>Voir aussi  
 [_heapchk](../c-runtime-library/reference/heapchk.md)   
 [_heapset](../c-runtime-library/heapset.md)   
 [_heapwalk](../c-runtime-library/reference/heapwalk.md)   
 [Constantes globales](../c-runtime-library/global-constants.md)