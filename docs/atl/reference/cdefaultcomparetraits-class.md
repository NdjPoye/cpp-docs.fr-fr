---
title: Classe de CDefaultCompareTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElements
- ATLCOLL/ATL::CDefaultCompareTraits::CompareElementsOrdered
dev_langs:
- C++
helpviewer_keywords:
- CDefaultCompareTraits class
ms.assetid: a17e2740-e7b4-48f2-aeb7-c80ce84b63f7
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 13c8bfd8ac02979f82e205ec86269b7ac40c8b08
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdefaultcomparetraits-class"></a>Classe de CDefaultCompareTraits
Cette classe fournit des fonctions de comparaison élément par défaut.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<typename T>  
class CDefaultCompareTraits
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données à stocker dans la collection.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CDefaultCompareTraits::CompareElements](#compareelements)|(Statique) Appelez cette fonction pour comparer deux éléments sont égaux.|  
|[CDefaultCompareTraits::CompareElementsOrdered](#compareelementsordered)|(Statique) Appelez cette fonction pour déterminer l’élément supérieur et inférieur.|  
  
## <a name="remarks"></a>Notes  
 Cette classe contient deux fonctions statiques pour comparer des éléments stockés dans un objet de classe de collection. Cette classe est utilisée par le [CDefaultElementTraits classe](../../atl/reference/cdefaultelementtraits-class.md).  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlcoll.h  
  
##  <a name="compareelements"></a>CDefaultCompareTraits::CompareElements  
 Appelez cette fonction pour comparer deux éléments sont égaux.  
  
```
static bool CompareElements(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Paramètres  
 `element1`  
 Premier élément.  
  
 `element2`  
 Le deuxième élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les éléments sont égaux, false dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut de cette fonction est l’égalité ( `==`) (opérateur). Pour les objets autres que les types de données simple, cette fonction devrez peut-être être remplacée.  
  
##  <a name="compareelementsordered"></a>CDefaultCompareTraits::CompareElementsOrdered  
 Appelez cette fonction pour déterminer l’élément supérieur et inférieur.  
  
```
static int CompareElementsOrdered(const T& element1, const T& element2);
```  
  
### <a name="parameters"></a>Paramètres  
 `element1`  
 Premier élément.  
  
 `element2`  
 Le deuxième élément.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un entier basé sur le tableau suivant :  
  
|Condition|Valeur de retour|  
|---------------|------------------|  
|`element1` < `element2`|<0|  
|`element1` == `element2`|0|  
|`element1` > `element2`|>0|  
  
### <a name="remarks"></a>Notes  
 L’implémentation par défaut de cette fonction utilise le `==`,  **\<** , et  **>**  opérateurs. Pour les objets autres que les types de données simple, cette fonction devrez peut-être être remplacée.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
