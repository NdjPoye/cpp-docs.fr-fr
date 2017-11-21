---
title: Classe de CAtlFileMapping | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAtlFileMapping
- atlfile/ATL::CAtlFileMapping
dev_langs: C++
helpviewer_keywords: CAtlFileMapping class
ms.assetid: 899fc058-e05e-48b5-aca9-340403bb9e26
caps.latest.revision: "20"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a028c2458b0a5085a1f46bf31f377e6ed9e4d346
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="catlfilemapping-class"></a>Classe de CAtlFileMapping
Cette classe représente un fichier mappé en mémoire, l’ajout d’un opérateur de conversion pour les méthodes de [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <typename T = char>  
class CAtlFileMapping : public CAtlFileMappingBase
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de données utilisés pour l’opérateur de cast.  
  
## <a name="members"></a>Membres  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAtlFileMapping::operator T *](#operator_t_star)|Permet la conversion implicite de `CAtlFileMapping` objets `T`  **\*** .|  
  
## <a name="remarks"></a>Remarques  
 Cette classe ajoute un opérateur de conversion unique pour permettre une conversion implicite de `CAtlFileMapping` objets `T`  **\*** . D’autres membres sont fournis par la classe de base [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 [CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)  
  
 `CAtlFileMapping`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlfile.h  
  
##  <a name="operator_t_star"></a>CAtlFileMapping::operator T *  
 Permet la conversion implicite de `CAtlFileMapping` objets `T`  **\*** .  
  
```  
operator T*() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un `T`  **\***  pointeur au début du fichier mappé en mémoire.  
  
### <a name="remarks"></a>Remarques  
 Appels [CAtlFileMappingBase::GetData](../../atl/reference/catlfilemappingbase-class.md#getdata) et réinterprète le pointeur retourné comme un `T`  **\***  où *T* est le type utilisé comme modèle paramètre de cette classe.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CAtlFileMappingBase](../../atl/reference/catlfilemappingbase-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
