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
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ecc32dc8e6e9b249b0b8b334ec3d08bf26cbd1ed
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplemapequalhelper-class"></a>Classe de CSimpleMapEqualHelper
Cette classe est une application d’assistance pour le [CSimpleMap](../../atl/reference/csimplemap-class.md) classe.  
  
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
  
## <a name="remarks"></a>Notes  
 Cette classe de traits est un supplément à la `CSimpleMap` classe. Il fournit des méthodes pour la comparaison de deux `CSimpleMap` éléments (plus précisément, les composants de clé et valeur) pour l’égalité de l’objet. Par défaut, les clés et valeurs sont comparées à l’aide de `operator==()`, mais si le mappage contient des types de données complexes qui n’ont pas leur propre opérateur d’égalité, cette classe peut être substituée pour fournir la fonctionnalité supplémentaire.  
  
## <a name="requirements"></a>Configuration requise  
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
 La seconde clé.  
  
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
 Retourne la valeur true si les valeurs sont égales, false dans le cas contraire.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CSimpleMapEqualHelperFalse](../../atl/reference/csimplemapequalhelperfalse-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
