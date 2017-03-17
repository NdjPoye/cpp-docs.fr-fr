---
title: Classe de CSimpleArrayEqualHelper | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper
- ATLSIMPCOLL/ATL::CSimpleArrayEqualHelper::IsEqual
dev_langs:
- C++
helpviewer_keywords:
- CSimpleArrayEqualHelper class
ms.assetid: a2b55d89-78c9-42ef-842c-5304c6d20ad6
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
ms.sourcegitcommit: 5a0c6a1062330f952bb8fa52bc934f6754465513
ms.openlocfilehash: 4a87879683257c66de5fe4e720dd29fa4c47031d
ms.lasthandoff: 02/24/2017

---
# <a name="csimplearrayequalhelper-class"></a>CSimpleArrayEqualHelper (classe)
Cette classe est une application d’assistance pour la [CSimpleArray](../../atl/reference/csimplearray-class.md) classe.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T>  
class CSimpleArrayEqualHelper
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Une classe dérivée.  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSimpleArrayEqualHelper::IsEqual](#isequal)|(Statique) Teste si deux `CSimpleArray` éléments pour l’égalité d’objet.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe de traits est un complément à la `CSimpleArray` classe. Il fournit une méthode de comparaison de deux éléments stockés dans un `CSimpleArray` objet. Par défaut, les éléments sont comparés à l’aide de **operator=()**, mais si le tableau contient les types de données complexes qui ne possèdent pas leur propre opérateur d’égalité, vous devez substituer cette classe.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsimpcoll.h  
  
##  <a name="isequal"></a>CSimpleArrayEqualHelper::IsEqual  
 Teste si deux `CSimpleArray` éléments pour l’égalité d’objet.  
  
```
static bool IsEqual(
    const T& t1,
    const T& t2);
```  
  
### <a name="parameters"></a>Paramètres  
 *T1*  
 Un objet de type T.  
  
 *T2*  
 Un objet de type T.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si les éléments sont égaux.  
  
## <a name="see-also"></a>Voir aussi  
 [CSimpleArray (classe)](../../atl/reference/csimplearray-class.md)   
 [CSimpleArrayEqualHelperFalse (classe)](../../atl/reference/csimplearrayequalhelperfalse-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

