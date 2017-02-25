---
title: "accelerator_view_removed, classe | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "amprt/Concurrency::accelerator_view_removed"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "amprt/Concurrency::accelerator_view_removed (classe)"
ms.assetid: 262446de-311c-454e-a5ed-e2aaced0d88a
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# accelerator_view_removed, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'exception levée lorsqu'un appel DirectX sous\-jacent échoue en raison du mécanisme de détection et de récupération du délai d'attente de Windows.  
  
## Syntaxe  
  
```  
class accelerator_view_removed : public runtime_exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Name|Description|  
|----------|-----------------|  
|[accelerator\_view\_removed::accelerator\_view\_removed, constructeur](../Topic/accelerator_view_removed::accelerator_view_removed%20Constructor.md)|Initialise une nouvelle instance de la classe `accelerator_view_removed`.|  
  
### Méthodes publiques  
  
|Name|Description|  
|----------|-----------------|  
|[accelerator\_view\_removed::get\_view\_removed\_reason, méthode](../Topic/accelerator_view_removed::get_view_removed_reason%20Method.md)|Retourne un code d'erreur HRESULT indiquant la cause de la suppression de l'objet `accelerator_view`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `runtime_exception`  
  
 `out_of_memory`  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)