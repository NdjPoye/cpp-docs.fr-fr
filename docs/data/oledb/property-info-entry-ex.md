---
title: "PROPERTY_INFO_ENTRY_EX | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "PROPERTY_INFO_ENTRY_EX"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "PROPERTY_INFO_ENTRY_EX (macro)"
ms.assetid: af32dfcd-4c50-449d-af3b-48d21bd67a04
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# PROPERTY_INFO_ENTRY_EX
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente une propriété spécifique dans un jeu de propriétés.  
  
## Syntaxe  
  
```  
  
PROPERTY_INFO_ENTRY_EX(  
dwPropID  
,  
vt  
,  
dwFlags  
,  
value  
,  
options  
)  
  
```  
  
#### Paramètres  
 *dwPropID*  
 \[in\] Valeur [DBPROPID](https://msdn.microsoft.com/en-us/library/ms723882.aspx) qui peut être utilisée en combinaison avec le GUID du jeu de propriétés pour identifier une propriété.  
  
 *vt*  
 \[in\] [VARTYPE](http://msdn.microsoft.com/fr-fr/317b911b-1805-402d-a9cb-159546bc88b4) de cette entrée de propriété.  
  
 `dwFlags`  
 \[in\] Valeur [DBPROPFLAGS](https://msdn.microsoft.com/en-us/library/ms724342.aspx) décrivant cette entrée de propriété.  
  
 *valeur*  
 \[in\] Valeur de propriété de type `DWORD`.  
  
 `options`  
 **DBPROPOPTIONS\_REQUIRED** ou **DBPROPOPTIONS\_SETIFCHEAP**. Normalement, un fournisseur n’a pas besoin de définir `options`, car celui\-ci est défini par le consommateur.  
  
## Notes  
 Avec cette macro, vous pouvez spécifier directement la valeur de propriété de type `DWORD`, ainsi que les options et les indicateurs. Pour affecter simplement à une propriété une valeur par défaut définie dans ATLDB.H, utilisez [PROPERTY\_INFO\_ENTRY](../../data/oledb/property-info-entry.md). Pour affecter à une propriété une valeur de votre choix, sans définir aucune option ou indicateur, utilisez [PROPERTY\_INFO\_ENTRY\_VALUE](../../data/oledb/property-info-entry-value.md).  
  
## Exemple  
 Voir [BEGIN\_PROPSET\_MAP](../../data/oledb/begin-propset-map.md).  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)