---
title: Classe de CSimpleMapEqualHelperFalse | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
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
ms.openlocfilehash: 68a08ffc0ba126c523a779e3d1a72217dead6235
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemapequalhelperfalse-class"></a>CSimpleMapEqualHelperFalse (classe)
Cette classe est une application d’assistance pour la [CSimpleMap](../../atl/reference/csimplemap-class.md) classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelperFalse
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleMapEqualHelperFalse::IsEqualKey](#isequalkey)|(Statique) Teste l’égalité de deux clés.|  
|[CSimpleMapEqualHelperFalse::IsEqualValue](#isequalvalue)|(Statique) Retourne la valeur false.|  
  
## <a name="remarks"></a>Notes  
 Cette classe de traits est un complément à la `CSimpleMap` classe. Il fournit une méthode pour comparer deux éléments contenus dans le `CSimpleMap` objet, en particulier deux éléments de valeur ou les deux éléments clés.  
  
 La comparaison de la valeur retournera toujours la valeur false et en outre, appelez `ATLASSERT` avec un argument False s’il est déjà référencé. Dans les situations où le test d’égalité n’est pas suffisamment défini, cette classe permet à une carte contenant des paires clé/valeur pour fonctionner correctement pour la plupart des méthodes, mais échouer de façon bien définie pour les méthodes qui dépendent des comparaisons telles que [CSimpleMap::FindVal](../../atl/reference/csimplemap-class.md#findval).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>CSimpleMapEqualHelperFalse::IsEqualKey  
 Teste l’égalité de deux clés.  
  
```
static bool IsEqualKey(const TKey& k1, const TKey& k2);
```  
  
### <a name="parameters"></a>Paramètres  
 `k1`  
 La première clé.  
  
 `k2`  
 La deuxième clé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les clés sont égales.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode appelle [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).  
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue  
 Retourne false.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne false.  
  
### <a name="remarks"></a>Notes  
 Cette méthode retourne toujours false et appelle `ATLASSERT` avec un argument False s’il est déjà référencé. L’objectif de `CSimpleMapEqualHelperFalse::IsEqualValue` consiste à forcer les méthodes à l’aide de comparaisons échouer de façon bien définie lors de l’égalité des tests n’ont pas été correctement définies.  
  
## <a name="see-also"></a>Voir aussi  
 [CSimpleMapEqualHelper (classe)](../../atl/reference/csimplemapequalhelper-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

