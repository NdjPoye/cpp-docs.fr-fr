---
title: Classe de CSimpleMapEqualHelperFalse | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualKey
- ATLSIMPCOLL/ATL::CSimpleMapEqualHelperFalse::IsEqualValue
dev_langs: C++
helpviewer_keywords: CSimpleMapEqualHelperFalse class
ms.assetid: a873eea3-e130-45cc-a476-61ee79511c3b
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c1418114233b59112fcffb58ef4ae7c437af5ab3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="csimplemapequalhelperfalse-class"></a>Classe de CSimpleMapEqualHelperFalse
Cette classe est une application d’assistance pour le [CSimpleMap](../../atl/reference/csimplemap-class.md) classe.  
  
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
 Cette classe de traits est un supplément à la `CSimpleMap` classe. Il fournit une méthode permettant de comparer deux éléments contenus dans le `CSimpleMap` objet, en particulier les deux éléments de valeur ou les deux éléments clés.  
  
 La comparaison de valeur retournera toujours false et en outre, appelez `ATLASSERT` avec un argument de la valeur false si elle n’est jamais référencée. Dans les situations où le test d’égalité n’est pas suffisamment défini, cette classe permet à une carte contenant des paires clé/valeur pour ne fonctionne pas correctement pour la plupart des méthodes, mais échouer de façon bien définie pour les méthodes qui dépendent des comparaisons telles que [CSimpleMap :: FindVal](../../atl/reference/csimplemap-class.md#findval).  
  
## <a name="requirements"></a>Configuration requise  
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
 La seconde clé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les clés sont égales.  
  
### <a name="remarks"></a>Notes  
 Cette méthode appelle [CSimpleArrayEqualHelper](../../atl/reference/csimplearrayequalhelper-class.md).  
  
##  <a name="isequalvalue"></a>CSimpleMapEqualHelperFalse::IsEqualValue  
 Retourne false.  
  
```
static bool IsEqualValue(const TVal&, const TVal&);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne false.  
  
### <a name="remarks"></a>Notes  
 Cette méthode retourne toujours false et appelle `ATLASSERT` avec un argument de la valeur false si elle n’est jamais référencée. L’objectif de `CSimpleMapEqualHelperFalse::IsEqualValue` consiste à forcer les méthodes à l’aide de comparaisons échouer de façon bien définie lors de tests d’égalité n’ont pas été définies correctement.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CSimpleMapEqualHelper](../../atl/reference/csimplemapequalhelper-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
