---
title: "CXMLAccessor::GetXMLRowData | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "ATL::CXMLAccessor::GetXMLRowData"
  - "ATL.CXMLAccessor.GetXMLRowData"
  - "CXMLAccessor::GetXMLRowData"
  - "CXMLAccessor.GetXMLRowData"
  - "GetXMLRowData"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetXMLRowData (méthode)"
ms.assetid: 156b66e3-42fd-491c-8943-38cf5e36f687
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# CXMLAccessor::GetXMLRowData
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Récupère le contenu entier d'une table en tant que données de chaîne au format XML, par ligne.  
  
## Syntaxe  
  
```  
  
      HRESULT GetXMLRowData(   
   CSimpleStringW& strOutput,   
   bool bAppend = false    
) throw( );  
```  
  
#### Paramètres  
 `strOutput`  
 \[out\] référence à un tampon qui contient les données de table à récupérer.  Les données sont mises en forme en tant que données de chaîne avec le nom de la balise XML qui correspondent aux noms de colonne de magasin de données.  
  
 *bAppend*  
 \[in\] valeur booléenne qui spécifie s'il faut ajouter une chaîne à la fin de les données de production.  
  
## Valeur de retour  
 Une des valeurs standard `HRESULT`  
  
## Notes  
 L'exemple suivant indique comment les données de ligne est mise en forme en XML.  `DATA` ci\-dessous représente les données de ligne.  Utilisez les méthodes de déplacement pour déplacer dans la ligne de votre choix.  
  
 `<row>`  
  
 `<column name>DATA</column name>`  
  
 `</row>`  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CXMLAccessor, classe](../../data/oledb/cxmlaccessor-class.md)