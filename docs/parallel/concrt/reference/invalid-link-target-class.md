---
title: "invalid_link_target, classe | Microsoft Docs"
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
  - "concrt/concurrency::invalid_link_target"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "invalid_link_target (classe)"
ms.assetid: 33b64885-34d8-4d4e-a893-02e9f19c958e
caps.latest.revision: 19
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# invalid_link_target, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception levée lorsque la méthode d' `link_target` de bloc de messagerie est appelée et le bloc de messagerie ne peut pas créer de liaison à la cible.  Cela peut être le résultat de dépasser le nombre de liens le bloc de messagerie est laissé ou une tentative de lier une cible spécifique deux fois à la même source.  
  
## Syntaxe  
  
```  
class invalid_link_target : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[invalid\_link\_target::invalid\_link\_target, constructeur](../Topic/invalid_link_target::invalid_link_target%20Constructor.md)|Surchargé.  Construit un objet `invalid_link_target`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `invalid_link_target`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 Accès concurrentiel de**l'espace de noms :**  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)   
 [Blocs de messages asynchrones](../../../parallel/concrt/asynchronous-message-blocks.md)