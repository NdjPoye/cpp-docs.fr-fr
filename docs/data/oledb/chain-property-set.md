---
title: "CHAIN_PROPERTY_SET | Microsoft Docs"
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
  - "CHAIN_PROPERTY_SET"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHAIN_PROPERTY_SET (macro)"
ms.assetid: 2bcf6d7d-f4e5-480d-9140-1e32a0994c94
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CHAIN_PROPERTY_SET
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette macro chaîne des groupes de propriétés ensemble.  
  
## Syntaxe  
  
```  
  
CHAIN_PROPERTY_SET(  
ChainClass   
)  
  
```  
  
#### Paramètres  
 *ChainClass*  
 \[in\] Le nom de la classe pour le chaînage des propriétés pour.  Il s'agit d'une classe générée par l'Assistant Projet ATL qui contient déjà une carte \(telle qu'une session, une commande, ou une classe d'objets source de données\).  
  
## Notes  
 Vous pouvez chaîner une propriété d'une classe à votre propre classe, puis accéder directement aux propriétés de la classe.  
  
> [!CAUTION]
>  Utilisez la macro avec parcimonie.  L'utilisation incorrecte risque de faire échouer un consommateur sur les tests de conformité OLE DB.  
  
## Configuration requise  
 **En\-tête :** atldb.h  
  
## Voir aussi  
 [Macros pour les modèles du fournisseur OLE DB](../../data/oledb/macros-for-ole-db-provider-templates.md)