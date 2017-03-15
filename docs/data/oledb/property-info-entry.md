---
title: "PROPERTY_INFO_ENTRY | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY (macro)"
ms.assetid: f7bd23d6-52b4-4d6a-aa9a-1fca9834c8dc
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROPERTY_INFO_ENTRY
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une propriété spécifique dans un jeu de propriétés.  
  
## Syntaxe  
  
```  
  
PROPERTY_INFO_ENTRY(  
dwPropID   
)  
  
```  
  
#### Paramètres  
 *dwPropID*  
 \[in\] Valeur [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) qui peut être utilisée en combinaison avec le GUID du jeu de propriétés pour identifier une propriété.  
  
## Notes  
 Cette macro attribue à la propriété de type `DWORD` une valeur par défaut définie dans ATLDB.H. Pour attribuer à la propriété une valeur de votre choix, utilisez [PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md). Pour définir en même temps [VARTYPE](http://msdn.microsoft.com/fr-fr/317b911b-1805-402d-a9cb-159546bc88b4) et [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) pour la propriété, utilisez [PROPERTY\_INFO\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md).  
  
## Exemple  
 Consultez [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)