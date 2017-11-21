---
title: Classe de CAutoPtrArray | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray
- ATLCOLL/ATL::CAutoPtrArray::CAutoPtrArray
dev_langs: C++
helpviewer_keywords: CAutoPtrArray class
ms.assetid: 880a70da-8c81-4427-8ac6-49aa8d424244
caps.latest.revision: "21"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 952f6a6d9fa06c0f0c34e5769b4302c6230abb43
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cautoptrarray-class"></a>Classe de CAutoPtrArray
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
 Cette classe fournit un constructeur et dérive des méthodes à partir de [CAtlArray](../../atl/reference/catlarray-class.md) et [CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md) à l’aide de la création d’un objet de classe de collection le stockage des pointeurs intelligents.  
  
 Pour plus d’informations, consultez [Classes de Collection ATL](../../atl/atl-collection-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `CAtlArray`  
  
 `CAutoPtrArray`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcoll.h  
  
##  <a name="cautoptrarray"></a>CAutoPtrArray::CAutoPtrArray  
 Constructeur.  
  
```
CAutoPtrArray() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Initialise le tableau de pointeurs intelligents.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe CAtlArray](../../atl/reference/catlarray-class.md)   
 [Classe de CAutoPtrElementTraits](../../atl/reference/cautoptrelementtraits-class.md)   
 [Classe de CAutoPtrList](../../atl/reference/cautoptrlist-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
