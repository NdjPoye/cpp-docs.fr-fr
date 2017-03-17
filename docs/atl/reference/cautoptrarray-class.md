---
title: Classe de CAutoPtrArray | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs:
- C++
helpviewer_keywords:
- CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 58ee329c7a3925fe3a29cf9738670cfa71df6777
ms.lasthandoff: 02/24/2017

---
# <a name="cautoptrarray-class"></a>CAutoPtrArray (classe)
Cette classe fournit des méthodes utiles lors de la construction d’un tableau de pointeurs intelligents.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <typename E>
class CAutoPtrArray : public CAtlArray<
                        ATL::CAutoPtr<E>,
                        CAutoPtrElementTraits<E>>
```  
  
#### <a name="parameters"></a>Paramètres  
 `E`  
 Le type de pointeur.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoPtrArray::CAutoPtrArray](#cautoptrarray)|Constructeur.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe fournit un constructeur et est dérivée des méthodes à partir de [CAtlArray](../../atl/reference/catlarray-class.md) et [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) à l’aide de la création d’un objet de classe de collection le stockage des pointeurs intelligents.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray  
 Constructeur.  
  
```
CAutoPtrArray() throw();
```  
  
### <a name="remarks"></a>Notes  
 Initialise le tableau de pointeurs intelligents.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe CAtlArray](../../atl/reference/catlarray-class.md)   
 [CAutoPtrElementTraits (classe)](../../atl/reference/cautoptrelementtraits-class.md)   
 [CAutoPtrList (classe)](../../atl/reference/cautoptrlist-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

