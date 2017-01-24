---
title: "CComObjectRoot Class | Microsoft Docs"
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
  - "CComObjectRoot"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComObjectRoot class"
ms.assetid: f8797c38-6e73-4f67-85c2-71654cffa8eb
caps.latest.revision: 17
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CComObjectRoot Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Ce typedef de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) est mis en modèle dans le modèle de thread par défaut du serveur.  
  
## Syntaxe  
  
```  
  
typedef CComObjectRootEx<CComObjectThreadModel> CComObjectRoot;  
  
```  
  
## Notes  
 `CComObjectRoot` est `typedef` de [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md) mis en modèle dans le modèle de thread par défaut du serveur.  Par conséquent [CComObjectThreadModel](../Topic/CComObjectThreadModel.md) référence [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ou [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md).  
  
 Gestion du nombre de référence d'objet de handles d'`CComObjectRootEx` pour non regroupé en agrégats et des objets regroupés en agrégats.  Il contient le nombre de référence d'objet si votre objet n'est pas regroupé, et contient le pointeur à l'extérieur inconnu si votre objet est regroupé.  Pour les objets regroupés en agrégats, des méthodes d' `CComObjectRootEx` peuvent être utilisées pour gérer l'échec de l'objet interne à l'élément, et protéger l'objet externe de la suppression lorsque les interfaces internes sont libérées ou l'objet interne est supprimé.  
  
## Configuration requise  
 **Header:** atlcom.h  
  
## Voir aussi  
 [CComObjectRootEx Class Members](http://msdn.microsoft.com/fr-fr/e3ce9c3d-9c8e-4fe5-b682-8e56740a0164)   
 [CComObjectRootEx Class](../../atl/reference/ccomobjectrootex-class.md)   
 [CComAggObject Class](../../atl/reference/ccomaggobject-class.md)   
 [CComObject Class](../../atl/reference/ccomobject-class.md)   
 [CComPolyObject Class](../../atl/reference/ccompolyobject-class.md)   
 [Class Overview](../../atl/atl-class-overview.md)