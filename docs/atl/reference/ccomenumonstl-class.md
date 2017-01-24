---
title: "CComEnumOnSTL Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComEnumOnSTL"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComEnumOnSTL class"
ms.assetid: befe1a44-7a00-4f28-9a2e-cc0fa526643c
caps.latest.revision: 21
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComEnumOnSTL Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette classe définit un objet énumérateur COM selon une collection STL.  
  
## Syntaxe  
  
```  
  
      template <  
   class Base,  
   const IID* piid,  
   class T,  
   class Copy,  
   class CollType,  
   class ThreadModel = CComObjectThreadModel  
>  
class ATL_NO_VTABLE CComEnumOnSTL :  
   public IEnumOnSTLImpl<Base, piid, T, Copy, CollType>,  
   public CComObjectRootEx< ThreadModel >  
```  
  
#### Paramètres  
 `Base`  
 Une interface d'énumérateur COM \([IEnumXXXX](https://msdn.microsoft.com/en-us/library/ms680089.aspx)\).  
  
 `piid`  
 Pointeur vers l'ID d'interface de l'interface d'énumérateur.  
  
 `T`  
 Le type d'élément exposé par l'interface d'énumérateur.  
  
 `Copy`  
 Une classe de [stratégie de copie](../../atl/atl-copy-policy-classes.md) .  
  
 `CollType`  
 Une classe de conteneur STL.  
  
## Notes  
 `CComEnumOnSTL` définit un objet énumérateur COM selon une collection STL.  Cette classe peut être utilisée seule ou conjointement avec [ICollectionOnSTLImpl](../../atl/reference/icollectiononstlimpl-class.md).  Les étapes standard pour l'utilisation de cette classe sont dessinées les grandes lignes ci\-dessous.  Pour plus d'informations, consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md).  
  
## Pour utiliser cette classe avec ICollectionOnSTLImpl :  
  
-   `typedef` une spécialisation de cette classe.  
  
-   Utilisez `typedef` comme argument template final dans une spécialisation d' `ICollectionOnSTLImpl`.  
  
 Consultez [Collections et énumérateurs ATL](../../atl/atl-collections-and-enumerators.md) pour un exemple.  
  
## Pour utiliser cette classe indépendamment de ICollectionOnSTLImpl :  
  
-   `typedef` une spécialisation de cette classe.  
  
-   Utilisez `typedef` comme argument template dans une spécialisation d' `CComObject`.  
  
-   Créez une instance de la spécialisation d' `CComObject` .  
  
-   Initialisez l'objet énumérateur en appelant [IEnumOnSTLImpl::Init](../Topic/IEnumOnSTLImpl::Init.md).  
  
-   Retourne l'interface de l'énumérateur au client.  
  
## Hiérarchie d'héritage  
 `CComObjectRootBase`  
  
 `Base`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)  
  
 `CComEnumOnSTL`  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Exemple  
 Le code indiqué ci\-dessous fournit une fonction générique pour traiter la création et l'initialisation d'un objet énumérateur :  
  
 [!code-cpp[NVC_ATL_COM#34](../../atl/codesnippet/CPP/ccomenumonstl-class_1.h)]  
  
 Cette fonction de modèle peut être utilisée pour implémenter la propriété d' `_NewEnum` d'une interface de collection comme indiqué ci\-dessous :  
  
 [!code-cpp[NVC_ATL_COM#35](../../atl/codesnippet/CPP/ccomenumonstl-class_2.h)]  
  
 Ce code crée `typedef` pour `CComEnumOnSTL` qui expose un vecteur d' `CComVariant`s au moyen de l'interface d' **IEnumVariant** .  La classe de **CVariantCollection** spécialise simplement **CreateSTLEnumerator** pour utiliser les objets énumérateurs de ce type.  
  
## Voir aussi  
 [IEnumOnSTLImpl](../../atl/reference/ienumonstlimpl-class.md)   
 [ATLCollections : Illustre ICollectionOnSTLImpl, CComEnumOnSTL, et classes personnalisées de stratégie de copie](../../top/visual-cpp-samples.md)   
 [Class Overview](../../atl/atl-class-overview.md)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComObjectThreadModel](../Topic/CComObjectThreadModel.md)   
 [IEnumOnSTLImpl Class](../../atl/reference/ienumonstlimpl-class.md)