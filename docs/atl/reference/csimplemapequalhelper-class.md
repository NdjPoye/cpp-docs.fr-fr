---
title: Classe de CSimpleMapEqualHelper | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelper::IsEqualValue
dev_langs:
- C++
helpviewer_keywords:
- CSimpleMapEqualHelper class
ms.assetid: 9bb2968a-d609-405c-8272-ff3b42df6164
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: ddb793889748446b9613c91ce6fcefe28da32eb3
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="csimplemapequalhelper-class"></a>CSimpleMapEqualHelper (classe)
Cette classe est une application d’assistance pour la [CSimpleMap](../../atl/reference/csimplemap-class.md) classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class TKey, class TVal>  
class CSimpleMapEqualHelper
```  
  
#### <a name="parameters"></a>Paramètres  
 `TKey`  
 L’élément clé.  
  
 `TVal`  
 L’élément de valeur.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleMapEqualHelper::IsEqualKey](#isequalkey)|(Statique) Teste l’égalité de deux clés.|  
|[CSimpleMapEqualHelper::IsEqualValue](#isequalvalue)|(Statique) Teste l’égalité de deux valeurs.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe de traits est un complément à la `CSimpleMap` classe. Il fournit des méthodes pour la comparaison de deux `CSimpleMap` éléments (en particulier, les composants clé et valeur) pour l’égalité d’objet. Par défaut, les clés et valeurs sont comparées à l’aide de `operator==()`, mais si le mappage contient des types de données complexes qui ne possèdent pas leur propre opérateur d’égalité, cette classe peut être substituée pour fournir la fonctionnalité supplémentaire requise.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsimpcoll.h  
  
##  <a name="isequalkey"></a>CSimpleMapEqualHelper::IsEqualKey  
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
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelper::IsEqualValue  
 Teste l’égalité de deux valeurs.  
  
```
static bool IsEqualValue(const TVal& v1, const TVal& v2);
```  
  
### <a name="parameters"></a>Paramètres  
 *V1*  
 Première valeur.  
  
 *v2*  
 Seconde valeur.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les valeurs sont égales.  
  
## <a name="see-also"></a>Voir aussi  
 [CSimpleMapEqualHelperFalse (classe)](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

