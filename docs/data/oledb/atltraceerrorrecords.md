---
title: "AtlTraceErrorRecords | Microsoft Docs"
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
  - "ATL.AtlTraceErrorRecords"
  - "ATL::AtlTraceErrorRecords"
  - "AtlTraceErrorRecords"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AtlTraceErrorRecords (fonction)"
ms.assetid: b83970b3-dc2a-445c-9142-f52218719905
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# AtlTraceErrorRecords
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Vidages des informations sur les enregistrements d'erreur OLE DB dans l'unité de vidage si une erreur est retournée.  
  
## Syntaxe  
  
```  
  
      inline void AtlTraceErrorRecords(   
   HRESULT hrErr = S_OK    
);  
```  
  
#### Paramètres  
 `hErr`  
 \[in\] Un `HRESULT` retourné par une fonction membre du Modèle de Consommateur OLE DB.  
  
## Notes  
 Si `hErr` n'est pas `S_OK`, `AtlTraceErrorRecords` vide les informations des enregistrements d'erreur OLE DB sur l'unité de vidage \(onglet de **Déboguer** de la fenêtre Sortie ou d'un fichier\).  Les informations d'enregistrement d'erreur, qui sont obtenues à partir de le fournisseur, incluent notamment le numéro de ligne, la source, la description, le fichier d'aide, le contexte, et le GUID pour chaque entrée d'enregistrement d'erreur.  `AtlTraceErrorRecords` vide ces informations uniquement dans les versions de débogage.  Dans les versions releases, il s'agit d'un stub vide qui est optimisé.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [CDBErrorInfo, classe](../../data/oledb/cdberrorinfo-class.md)