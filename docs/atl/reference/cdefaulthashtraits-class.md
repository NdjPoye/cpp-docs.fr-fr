---
title: Classe de CDefaultHashTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits
- ATLCOLL/ATL::CDefaultHashTraits::Hash
dev_langs: C++
helpviewer_keywords: CDefaultHashTraits class
ms.assetid: d8ec4b37-6d58-447b-a0c1-8580c5b1ab85
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 383cdc49f9ac78447186a677bc712287b71b3994
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cdefaulthashtraits-class"></a>Classe de CDefaultHashTraits
Cette classe fournit une fonction statique pour le calcul de valeurs de hachage.  
  
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
  
## <a name="remarks"></a>Remarques  
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
  
### <a name="remarks"></a>Remarques  
 L’algorithme de hachage par défaut est très simple : la valeur de retour est le numéro d’élément. Remplacez cette fonction si un algorithme plus complexe est requis.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
