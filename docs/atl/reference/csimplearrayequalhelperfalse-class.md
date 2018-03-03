---
title: Classe de CSimpleArrayEqualHelperFalse | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelperFalse::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelperFalse class
ms.assetid: 6918af6f-d23d-49eb-8482-c44272f5ffeb
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28d43b6a83842373c2fc169ce43022f1912c4e0f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplearrayequalhelperfalse-class"></a>Classe de CSimpleArrayEqualHelperFalse
Cette classe est une application d’assistance pour le [CSimpleArray](../../atl/reference/csimplearray-class.md) classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
class CSimpleArrayEqualHelperFalse
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Une classe dérivée.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleArrayEqualHelperFalse::IsEqual](#isequal)|(Statique) Retourne la valeur false.|  
  
## <a name="remarks"></a>Notes  
 Cette classe de traits est un complément à la `CSimpleArray` classe. Informatique toujours retourne false et, en outre, appellera `ATLASSERT` avec un argument de la valeur false si elle n’est jamais référencée. Dans les situations où le test d’égalité n’est pas suffisamment défini, cette classe permet à un tableau contenant les éléments pour ne fonctionne pas correctement pour la plupart des méthodes, mais échouer de façon bien définie pour les méthodes qui dépendent des comparaisons telles que [CSimpleArray :: Rechercher](../../atl/reference/csimplearray-class.md#find).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual  
 Retourne false.  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne false.  
  
### <a name="remarks"></a>Notes  
 Cette méthode retourne toujours false et appelle `ATLASSERT` avec un argument de la valeur false si référencé. L’objectif de `CSimpleArrayEqualHelperFalse::IsEqual` consiste à forcer les méthodes à l’aide de comparaisons échouer de façon bien définie lors de tests d’égalité n’ont pas été définies correctement.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
