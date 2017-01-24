---
title: "BEGIN_PROPSET_MAP | Microsoft Docs"
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
  - "BEGIN_PROPSET_MAP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "BEGIN_PROPSET_MAP (macro)"
ms.assetid: c3a30618-6025-4d49-8688-a171294d2e93
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# BEGIN_PROPSET_MAP
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Marque le début des entrées de mappage de l'ensemble de propriété.  
  
## Syntaxe  
  
```  
  
BEGIN_PROPSET_MAP(  
Class   
)  
  
```  
  
#### Paramètres  
 *Classe*  
 \[in\] la classe dans laquelle cette propriété est spécifiée.  Un jeu de propriétés peut être spécifié dans les objets OLE DB suivants :  
  
-   [\<caps:sentence id\="tgt4" sentenceid\="75bbb794f21139fcd243c18fff6050d2" class\="tgtSentence"\>Données Source Objet\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms721278.aspx)  
  
-   [\<caps:sentence id\="tgt5" sentenceid\="e423b0fba10fc83bd76e01e3eee2fd69" class\="tgtSentence"\>Objet Session\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms711572.aspx)  
  
-   [\<caps:sentence id\="tgt6" sentenceid\="5f6bc08c46cee6f21bfcdd08aff6e8aa" class\="tgtSentence"\>Commandes\<\/caps:sentence\>](https://msdn.microsoft.com/en-us/library/ms724608.aspx)  
  
## Exemple  
 Voici un mappage de jeu de propriété d'exemple :  
  
 [!code-cpp[NVC_OLEDB_Provider#3](../../data/oledb/codesnippet/CPP/begin-propset-map_1.h)]  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)   
 [Modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-templates-cpp.md)   
 [Architecture des modèles du fournisseur OLE DB](../../data/oledb/ole-db-provider-template-architecture.md)   
 [Création d'un fournisseur OLE DB](../../data/oledb/creating-an-ole-db-provider.md)