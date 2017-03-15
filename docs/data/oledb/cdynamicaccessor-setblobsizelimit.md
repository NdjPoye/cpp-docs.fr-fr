---
title: "CDynamicAccessor::SetBlobSizeLimit | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::SetBlobSizeLimit"
  - "SetBlobSizeLimit"
  - "CDynamicAccessor.SetBlobSizeLimit"
  - "ATL.CDynamicAccessor.SetBlobSizeLimit"
  - "ATL::CDynamicAccessor::SetBlobSizeLimit"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobSizeLimit (méthode)"
ms.assetid: fb8cb85d-f841-408e-a344-37895b10993f
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::SetBlobSizeLimit
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Règle la taille maximale du BLOB en octets.  
  
## Syntaxe  
  
```  
  
      void SetBlobSizeLimit(  
   DBLENGTH nBlobSize   
);  
```  
  
#### Paramètres  
 `nBlobSize`  
 Spécifie la limite de taille BLOB.  
  
## Notes  
 Définit la taille maximale du BLOB en octets ; les données de colonne qui sont supérieures à cette valeur sont traitées en tant que BLOB.  Certains fournisseurs donnent des tailles très grandes pour des colonnes \(tels que 2 Go\).  Plutôt que la tentative d'allouer de la mémoire pour une colonne de cette taille, vous essayeriez généralement de lier les colonnes en tant qu'objets BLOB.  De cette façon vous ne devez pas allouer toute la mémoire, mais vous pouvez toujours lire les données sans crainte de troncation.  Toutefois, il existe des cas où vous pouvez forcer `CDynamicAccessor` à lier de grandes colonnes LOB dans leurs types de données natifs.  Pour cela, `SetBlobSizeLimit` appelez avant d'appeler **Ouvrir**.  
  
 La méthode de constructeur [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) définit la taille maximale BLOB avec une valeur par défaut de 8.000 octets.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)