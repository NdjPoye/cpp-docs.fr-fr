---
title: "CDynamicAccessor::SetBlobHandling | Microsoft Docs"
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
  - "CDynamicAccessor::SetBlobHandling"
  - "CDynamicAccessor.SetBlobHandling"
  - "ATL::CDynamicAccessor::SetBlobHandling"
  - "SetBlobHandling"
  - "ATL.CDynamicAccessor.SetBlobHandling"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetBlobHandling (méthode)"
ms.assetid: fa8b0bb3-a21b-4d64-aeef-e79bf61d079c
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CDynamicAccessor::SetBlobHandling
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Règle la valeur de gestion BLOB pour la ligne actuelle.  
  
## Syntaxe  
  
```  
  
      bool SetBlobHandling(  
   DBBLOBHANDLINGENUM eBlobHandling   
);  
```  
  
#### Paramètres  
 `eBlobHandling`  
 Spécifie comment les données BLOB doivent être gérées.  Cela peut prendre les valeurs suivantes :  
  
-   **DBBLOBHANDLING\_DEFAULT**: Traiter les données d'une colonne plus grandes que`nBlobSize` \(défini par `SetBlobSizeLimit`\) comme données d'objet BLOB et les récupérez\- via un objet `ISequentialStream` ou `IStream`.  Cette option essaie de lier chaque colonne qui contient des données plus grandes que `nBlobSize` ou répertoriées comme **DBTYPE\_IUNKNOWN** en tant que données BLOB.  
  
-   **DBBLOBHANDLING\_NOSTREAMS**: Traiter les données de colonne plus grandes que `nBlobSize` \(défini par `SetBlobSizeLimit`\) comme données d'objet BLOB et récupérez\-les par référence dans la mémoire allouée par le fournisseur et possédée par le consommateur.  Cette option est utile pour les tables qui ont plusieurs colonnes BLOB, et quand le fournisseur prend en charge uniquement un objet `ISequentialStream` par accesseur.  
  
-   **DBBLOBHANDLING\_SKIP**: Ignorez \(pas de liaison\) les colonnes qui se qualifient comme contenant des objets blob \(l'accesseur ne liera pas ou ne récupèrera pas la valeur de la colonne mais il récupère toujours l'état et la longueur de colonne\).  
  
## Notes  
 Vous devez appeler `SetBlobHandling` avant d'appeler **Ouvrir**.  
  
 La méthode de constructeur [CDynamicAccessor](../../data/oledb/cdynamicaccessor-class.md) définit la valeur de gestion BLOB à **DBBLOBHANDLING\_DEFAULT**.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)