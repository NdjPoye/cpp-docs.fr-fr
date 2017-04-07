---
title: Classe de CComAutoDeleteCriticalSection | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComAutoDeleteCriticalSection
- atlcore/ATL::CComAutoDeleteCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComAutoDeleteCriticalSection class
ms.assetid: 2396dbea-1c60-4841-b50e-c4e18af311a3
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: eb53a0966d29759bbe7513f6042f72a280801707
ms.lasthandoff: 02/24/2017

---
# <a name="ccomautodeletecriticalsection-class"></a>CComAutoDeleteCriticalSection (classe)
Cette classe fournit des méthodes permettant d’obtenir et de libérer la possession d’un objet de section critique.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComAutoDeleteCriticalSection : public CComSafeDeleteCriticalSection
```  
  
## <a name="remarks"></a>Remarques  
 `CComAutoDeleteCriticalSection`dérive de la classe [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md). Toutefois, `CComAutoDeleteCriticalSection` remplace le [terme](ccomsafedeletecriticalsection-class.md#term) méthode `private` accès, ce qui force le nettoyage de mémoire interne se produit uniquement lorsque les instances de cette classe sont hors de portée ou soient explicitement supprimés de la mémoire.  

  
 Cette classe introduit des méthodes supplémentaires sur sa classe de base. Consultez la page [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md) et [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) pour plus d’informations sur les classes d’assistance de section critique.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)  
  
 [CComSafeDeleteCriticalSection](../../atl/reference/ccomsafedeletecriticalsection-class.md)  
  
 `CComAutoDeleteCriticalSection`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcore.h  
  
## <a name="see-also"></a>Voir aussi  
 [CComSafeDeleteCriticalSection (classe)](../../atl/reference/ccomsafedeletecriticalsection-class.md)   
 [CComCriticalSection (classe)](../../atl/reference/ccomcriticalsection-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

