---
title: "CDynamicAccessor::CDynamicAccessor | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CDynamicAccessor::CDynamicAccessor"
  - "ATL::CDynamicAccessor::CDynamicAccessor"
  - "ATL.CDynamicAccessor.CDynamicAccessor"
  - "CDynamicAccessor.CDynamicAccessor"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CDynamicAccessor (classe), constructeur"
ms.assetid: bf40fe81-2c85-473e-9075-51ad9b060b39
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# CDynamicAccessor::CDynamicAccessor
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Instancie et initialise l'objet `CDynamicAccessor`.  
  
## Syntaxe  
  
```  
  
      CDynamicAccessor(   
   DBBLOBHANDLINGENUM eBlobHandling = DBBLOBHANDLING_DEFAULT,   
   DBLENGTH nBlobSize = 8000   
);  
```  
  
#### Paramètres  
 `eBlobHandling`  
 Spécifie comment les données d'objet binaire large \(BLOB\) doivent être gérées.  La valeur par défaut est **DBBLOBHANDLING\_DEFAULT**.  Voir [CDynamicAccessor::SetBlobHandling](../../data/oledb/cdynamicaccessor-setblobhandling.md) pour obtenir une description des valeurs de **DBBLOBHANDLINGENUM**.  
  
 `nBlobSize`  
 La taille maximale du BLOB en octets ; les données de la colonne à cette valeur sont traitées en tant que BLOB.  La valeur par défaut est 8,000.  Consultez [SetBlobSizeLimit](../../data/oledb/cdynamicaccessor-setblobsizelimit.md) pour plus de détails.  
  
## Notes  
 Si vous utilisez le constructeur pour initialiser l'objet de `CDynamicAccessor`, vous pouvez spécifier comment il liera des objets blob.  Les objets BLOB peuvent contenir des données binaires tels que les graphiques, le bruit, ou le code compilé.  Le comportement par défaut consiste à traiter les colonnes supérieure à 8.000 octets en tant qu'objets BLOB et essayer de les lier à un objet de `ISequentialStream`.  Toutefois, vous pouvez spécifier une autre valeur qui sera la taille BLOB.  
  
 Vous pouvez également spécifier comment `CDynamicAccessor` traite les données de la colonne éligibles de données BLOB : il peut traiter les données BLOB de façon par défaut ; il peut ignorer \(ne pas lier\) des données BLOB ; ou il peut lier les données BLOB en mémoire allouée par le fournisseur.  
  
## Configuration requise  
 **En\-tête :** atldbcli.h  
  
## Voir aussi  
 [CDynamicAccessor, classe](../../data/oledb/cdynamicaccessor-class.md)