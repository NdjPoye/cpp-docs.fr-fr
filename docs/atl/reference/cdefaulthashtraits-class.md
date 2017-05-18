---
title: Classe de CDefaultHashTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs:
- C++
helpviewer_keywords:
- CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 5191327e5e60935829750c7d1e04ba89fcddc771
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cdefaulthashtraits-class"></a>CDefaultHashTraits (classe)
Cette classe fournit une fonction statique pour le calcul des valeurs de hachage.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename T>  
class CDefaultHashTraits
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDefaultHashTraits::Hash](#hash)|(Statique) Appelez cette fonction pour calculer une valeur de hachage pour un élément donné.|  
  
## <a name="remarks"></a>Notes  
 Cette classe contient une seule fonction statique qui retourne une valeur de hachage pour un élément donné. Cette classe est utilisée par le [CDefaultElementTraits classe](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="hash"></a>CDefaultHashTraits::Hash  
 Appelez cette fonction pour calculer une valeur de hachage pour un élément donné.  
  
```
static ULONG Hash(const T& element) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `element`  
 Élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur de hachage.  
  
### <a name="remarks"></a>Notes  
 L’algorithme de hachage par défaut est très simple : la valeur de retour est le numéro d’élément. Remplacez cette fonction si un algorithme plus complexe est requis.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

