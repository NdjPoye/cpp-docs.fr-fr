---
title: "scoped_d3d_access_lock, classe | Microsoft Docs"
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
ms.assetid: 0ad333e6-9839-4736-a722-16d95d70c4b1
caps.latest.revision: 8
caps.handback.revision: 2
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# scoped_d3d_access_lock, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Wrapper RAII pour un verrou d'accès D3D sur un objet accelerator\_view.  
  
## Syntaxe  
  
```  
class scoped_d3d_access_lock;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[scoped\_d3d\_access\_lock::scoped\_d3d\_access\_lock, constructeur](../Topic/scoped_d3d_access_lock::scoped_d3d_access_lock%20Constructor.md)|Surchargé.  Construit un objet `scoped_d3d_access_lock`.  Le verrouillage est annulé lorsque cet objet est hors de portée.|  
|[scoped\_d3d\_access\_lock::~scoped\_d3d\_access\_lock, destructeur](../Topic/scoped_d3d_access_lock::~scoped_d3d_access_lock%20Destructor.md)|Libère le verrou d'accès D3D sur l'objet `accelerator_view` associé.|  
  
### Opérateurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[scoped\_d3d\_access\_lock::operator\=, opérateur](../Topic/scoped_d3d_access_lock::operator=%20Operator.md)|Prend possession d'un verrou à partir d'un autre `scoped_d3d_access_lock`.|  
  
## Hiérarchie d'héritage  
 `scoped_d3d_access_lock`  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms :** concurrency::direct3d  
  
## Voir aussi  
 [Concurrency::direct3d, espace de noms](../../../parallel/amp/reference/concurrency-direct3d-namespace.md)