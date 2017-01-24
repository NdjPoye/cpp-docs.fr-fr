---
title: "BEGIN_PROPERTY_SET_EX | Microsoft Docs"
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
  - "BEGIN_PROPERTY_SET_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROPERTY_SET_EX (macro)"
ms.assetid: c95e7fab-edce-47b8-b282-200e53a2ea8a
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_PROPERTY_SET_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marque le début d'un ensemble propriété dans un mappage d'ensemble de propriété.  
  
## Syntaxe  
  
```  
  
BEGIN_PROPERTY_SET_EX(  
guid  
, flags )  
```  
  
#### Paramètres  
 `guid`  
 \[in\] Le GUID de la propriété.  
  
 `flags`  
 \[in\] **UPROPSET\_HIDDEN** pour tous les jeux de propriétés que vous ne souhaitez pas à afficher, ou **UPROPSET\_PASSTHROUGH** pour un fournisseur qui expose les propriétés en dehors de l'étendue du fournisseur.  
  
## Exemple  
 Voir [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)