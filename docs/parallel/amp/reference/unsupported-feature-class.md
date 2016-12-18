---
title: "unsupported_feature, classe | Microsoft Docs"
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
  - "amprt/Concurrency::unsupported_feature"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unsupported_feature (classe)"
ms.assetid: 6b1ab917-df13-48c7-9648-7cb2465a0ff5
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# unsupported_feature, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

L'exception levée quand une fonctionnalité non prise en charge est utilisée.  
  
## Syntaxe  
  
```  
class unsupported_feature : public runtime_exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[unsupported\_feature::unsupported\_feature, constructeur](../Topic/unsupported_feature::unsupported_feature%20Constructor.md)|Construit une nouvelle instance de l'exception `unsupported_feature`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `runtime_exception`  
  
 `unsupported_feature`  
  
## Configuration requise  
 **En\-tête :** amprt.h  
  
 **Espace de noms d'accès :** Concurrency  
  
## Voir aussi  
 [Concurrency, espace de noms \(C\+\+ AMP\)](../../../parallel/amp/reference/concurrency-namespace-cpp-amp.md)