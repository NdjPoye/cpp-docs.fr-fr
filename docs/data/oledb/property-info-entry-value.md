---
title: "PROPERTY_INFO_ENTRY_VALUE | Microsoft Docs"
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
  - "PROPERTY_INFO_ENTRY_VALUE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_VALUE (macro)"
ms.assetid: 9690f7f3-fb20-4a7e-a75f-8a3a1cb1ce0d
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# PROPERTY_INFO_ENTRY_VALUE
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une propriété spécifique dans un jeu de propriétés.  
  
## Syntaxe  
  
```  
  
PROPERTY_INFO_ENTRY_VALUE(  
dwPropID  
, value )  
```  
  
#### Paramètres  
 *dwPropID*  
 \[in\] Une valeur de type [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) qui peut être utilisée conjointement avec le GUID du jeu de propriétés pour identifier une propriété.  
  
 *correspondante*  
 \[in\] La valeur de la propriété du type `DWORD`.  
  
## Notes  
 Avec la macro, vous pouvez spécifier directement la valeur de la propriété du type `DWORD`.  Pour définir la propriété avec la valeur par défaut définie dans ATLDB.H, utilisez [PROPERTY\_INFORMATION\_ENTRY](../../data/oledb/property-info-entry.md).  Pour définir la valeur, les balises, et les options de la propriété, utilisez [PROPERTY\_INFORMATION\_ENTRY\_EX](../../data/oledb/property-info-entry-ex.md).  
  
## Exemple  
 Voir [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)