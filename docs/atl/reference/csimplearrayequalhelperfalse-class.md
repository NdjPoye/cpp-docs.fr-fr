---
title: Classe de CSimpleArrayEqualHelperFalse | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
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
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: cd5ed7058194880ef1ceaebe788e3deb60d4ac8e
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelperfalse-class"></a>CSimpleArrayEqualHelperFalse (classe)
Cette classe est une application d’assistance pour la [CSimpleArray](../../atl/reference/csimplearray-class.md) classe.  
  
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
  
## <a name="remarks"></a>Remarques  
 Cette classe de traits est un complément à la `CSimpleArray` classe. Informatique toujours retourne false et, en outre, appellera `ATLASSERT` avec un argument False s’il est déjà référencé. Dans les situations où le test d’égalité n’est pas suffisamment défini, cette classe permet à un tableau contenant les éléments pour fonctionner correctement pour la plupart des méthodes, mais échouer de façon bien définie pour les méthodes qui dépendent des comparaisons telles que [CSimpleArray::Find](../../atl/reference/csimplearray-class.md#find).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelperFalse::IsEqual  
 Retourne false.  
  
```
static bool IsEqual(const T&, const T&);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne false.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode retourne toujours false et appelle `ATLASSERT` avec un argument False si référencé. L’objectif de `CSimpleArrayEqualHelperFalse::IsEqual` consiste à forcer les méthodes à l’aide de comparaisons échouer de façon bien définie lors de l’égalité des tests n’ont pas été correctement définies.  
  
## <a name="see-also"></a>Voir aussi  
 [CSimpleArrayEqualHelper (classe)](../../atl/reference/csimplearrayequalhelper-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

