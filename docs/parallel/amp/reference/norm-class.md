---
title: "norm, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amp_short_vectors/Concurrency::graphics::norm"
dev_langs: 
  - "C++"
ms.assetid: 73002f3d-c25e-4119-bcd3-4c46c9b6abf1
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# norm, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Représentent un numéro de standard.  Chaque élément est un nombre à virgule flottante de la plage \[\- 1.0f, 1.0f\].  
  
## Syntaxe  
  
```  
class norm;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[norm::norm, constructeur](../Topic/norm::norm%20Constructor.md)|Surchargé.  Constructeur par défaut.  Initialise à 0.0f.|  
  
### Opérateurs publics  
  
|Name|Description|  
|----------|-----------------|  
|Opérateur norm::operator\-||  
|Opérateur norm::operator\-\-||  
|opérateur norm::operator float|Opérateurs de conversion  Convertissez le nombre standard en valeur à virgule flottante.|  
|Opérateur norm::operator\=\*||  
|Opérateur norm::operator\/\=||  
|Opérateur norm::operator\=\+\+||  
|Opérateur norm::operator\+\=||  
|Opérateur norm::operator\=||  
|Opérateur norm::operator\-\=||  
  
## Hiérarchie d'héritage  
 `norm`  
  
## Configuration requise  
 **En\-tête:** amp\_short\_vectors.h  
  
 **Espace de noms :** Concurrency::graphics  
  
## Voir aussi  
 [Concurrency::graphics, espace de noms](../../../parallel/amp/reference/concurrency-graphics-namespace.md)