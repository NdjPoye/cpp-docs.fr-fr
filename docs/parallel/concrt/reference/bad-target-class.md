---
title: "bad_target, classe | Microsoft Docs"
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
  - "concrt/concurrency::bad_target"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bad_target (classe)"
ms.assetid: e6dcddbf-9217-4fac-ac7f-7b8b4781d2f5
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# bad_target, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsqu'un bloc de messagerie reçoit un pointeur vers une cible valide pour l'opération effectuée.  
  
## Syntaxe  
  
```  
class bad_target : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[bad\_target::bad\_target, constructeur](../Topic/bad_target::bad_target%20Constructor.md)|Surchargé.  Construit un objet `bad_target`.|  
  
## Notes  
 Cette exception est généralement levée pour des raisons telles qu'une cible essayant de consommer un message réservé pour une cible différente ou annulant une réservation qu'il ne détient pas.  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `bad_target`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md)