---
title: IAccessorImpl, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- IAccessorImpl
dev_langs:
- C++
helpviewer_keywords:
- IAccessorImpl class
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 7cfc33432d12ac00c834d16f83cc26404e92c63e
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="iaccessorimpl-class"></a>IAccessorImpl, classe
Fournit une implémentation de la [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx) interface.  
  
## <a name="syntax"></a>Syntaxe

```cpp
template <class T, 
          class BindType = ATLBINDINGS,
          class BindingVector = CAtlMap <HACCESSOR hAccessor, BindType* pBindingsStructure>>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe d’objet ensemble de lignes ou de la commande.  
  
 `BindType`  
 Unité de stockage pour les informations de liaison. La valeur par défaut est la **ATLBINDINGS** structure (voir atldb.h).  
  
 `BindingVector`  
 Unité de stockage pour les informations de colonne. La valeur par défaut est [CAtlMap](../../atl/reference/catlmap-class.md) où l’élément clé est un **HACCESSOR** valeur et l’élément de valeur est un pointeur vers un `BindType` structure.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|Constructeur.|  
  
### <a name="interface-methods"></a>Méthodes d’interface  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|Ajoute un décompte de références à un accesseur existant.|  
|[CreateAccessor](../../data/oledb/iaccessorimpl-createaccessor.md)|Crée un accesseur à partir d’un jeu de liaisons.|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|Retourne les liaisons dans un accesseur.|  
|[ReleaseAccessor](../../data/oledb/iaccessorimpl-releaseaccessor.md)|Libère un accesseur.|  
  
## <a name="remarks"></a>Notes  
 Ce champ est obligatoire sur les commandes et les ensembles de lignes. OLE DB requiert que les fournisseurs implémenter un **HACCESSOR**, qui est une balise à un tableau de [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) structures. **HACCESSOR**s fournie par `IAccessorImpl` sont des adresses de la `BindType` structures. Par défaut, `BindType` est défini comme un **ATLBINDINGS** dans `IAccessorImpl`de définition de modèle. `BindType` fournit un mécanisme utilisé par `IAccessorImpl` pour suivre le nombre d’éléments dans son **DBBINDING** ainsi qu’un indicateur de nombre et d’accesseur de référence de tableau.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)