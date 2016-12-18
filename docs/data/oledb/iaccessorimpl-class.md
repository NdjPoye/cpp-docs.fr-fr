---
title: "IAccessorImpl, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IAccessorImpl"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IAccessorImpl (classe)"
ms.assetid: 768606da-8b71-417c-a62c-88069ce7730d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IAccessorImpl, classe
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit une implémentation de l'interface [IAccessor](https://msdn.microsoft.com/en-us/library/ms719672.aspx).  
  
## Syntaxe  
  
```  
template <  
   class T,   
   class BindType = ATLBINDINGS,   
   class BindingVector = CAtlMap <   
      HACCESSOR hAccessor,   
      BindType* pBindingsStructure   
   >   
>  
class ATL_NO_VTABLE IAccessorImpl : public IAccessorImplBase<BindType>  
```  
  
#### Paramètres  
 `T`  
 La classe d'ensemble de lignes ou de l'objet de commande.  
  
 `BindType`  
 Unité de stockage des informations de liaison.  La valeur par défaut est la structure **ATLBINDINGS** \(voir l'atldb.h\).  
  
 `BindingVector`  
 Unité de stockage réservée aux informations de colonne.  La valeur par défaut est [CAtlMap](../../atl/reference/catlmap-class.md) où l'élément clé est une valeur de **HACCESSOR** et l'élément valeur est un pointeur vers une structure `BindType`.  
  
## Membres  
  
### Méthodes  
  
|||  
|-|-|  
|[IAccessorImpl](../../data/oledb/iaccessorimpl-class.md)|Constructeur.|  
  
### Méthodes d'interface  
  
|||  
|-|-|  
|[AddRefAccessor](../../data/oledb/iaccessorimpl-addrefaccessor.md)|Ajoute un décompte de références à un accesseur existant.|  
|[CreerAccesseur](../../data/oledb/iaccessorimpl-createaccessor.md)|Crée un accesseur à partir d'un jeu de liaisons.|  
|[GetBindings](../../data/oledb/iaccessorimpl-getbindings.md)|Retourne les liaisons dans un accesseur.|  
|[ReleaseAccessors](../../data/oledb/iaccessorimpl-releaseaccessor.md)|Libère un accesseur.|  
  
## Notes  
 C'est obligatoire sur les ensembles de lignes et les commandes.  OLE DB requiert que les fournisseurs implémentent **HACCESSOR**, qui est une balise vers un tableau de structures [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx).  Les **HACCESSOR** fournis par `IAccessorImpl` sont des adresses des structures `BindType`.  Par défaut, `BindType` est défini comme **ATLBINDINGS** dans la définition du modèle `IAccessorImpl`.  `BindType` fournit un mécanisme utilisé par `IAccessorImpl` pour suivre le nombre d'éléments dans le tableau de **DBBINDING** ainsi qu'un nombre de références et les indicateurs d'accesseur.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)