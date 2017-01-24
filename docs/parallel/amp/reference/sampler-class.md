---
title: "sampler, classe | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
ms.assetid: 9a6a9807-497d-402d-b092-8c4d86275b80
caps.latest.revision: 7
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# sampler, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

La classe d'échantillonnage regroupe des données de configuration d'échantillonnage à utiliser pour l'échantillonnage texturée.  
  
## Syntaxe  
  
```  
class sampler;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[sampler::sampler, constructeur](../Topic/sampler::sampler%20Constructor.md)|Surchargé.  Construit une instance d'échantillonnage.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[sampler::get\_address\_mode, méthode](../Topic/sampler::get_address_mode%20Method.md)|Retourne l'objet `address_mode` qui est associé à l'objet échantillonneur.|  
|[sampler::get\_border\_color, méthode](../Topic/sampler::get_border_color%20Method.md)|Retourne la couleur de bordure associée à l'objet d'échantillonnage.|  
|[sampler::get\_filter\_mode, méthode](../Topic/sampler::get_filter_mode%20Method.md)|Retourne l'objet `filter_mode` qui est associé à l'objet échantillonneur.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[sampler::operator\=, opérateur](../Topic/sampler::operator=%20Operator.md)|Surchargé.  Opérateur d'assignation|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[sampler::address\_mode, membre de données](../Topic/sampler::address_mode%20Data%20Member.md)|Obtient le mode d'adresse de l'objet `sampler`.|  
|[sampler::border\_color, membre de données](../Topic/sampler::border_color%20Data%20Member.md)|Obtient la couleur de bordure de l’objet `sampler`.|  
|[sampler::filter\_mode, membre de données](../Topic/sampler::filter_mode%20Data%20Member.md)|Obtient le mode de filtre de l'objet `sampler`.|  
  
## Hiérarchie d'héritage  
 `sampler`  
  
## Configuration requise  
 **En\-tête :** amp\_graphics.h  
  
 **Espace de noms :** concurrency::graphics  
  
## Voir aussi  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)