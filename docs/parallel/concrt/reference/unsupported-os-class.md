---
title: "unsupported_os, classe | Microsoft Docs"
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
  - "concrt/concurrency::unsupported_os"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "unsupported_os (classe)"
ms.assetid: 6fa57636-341b-4b51-84cc-261d283ff736
caps.latest.revision: 20
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# unsupported_os, classe
[!INCLUDE[vs2017banner](../../../assembler/inline/includes/vs2017banner.md)]

Cette classe décrit une exception qui est renvoyée dès qu'un système d'exploitation non pris en charge est utilisé.  
  
## Syntaxe  
  
```  
class unsupported_os : public std::exception;  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[unsupported\_os::unsupported\_os, constructeur](../Topic/unsupported_os::unsupported_os%20Constructor.md)|Surchargé.  Construit un objet `unsupported_os`.|  
  
## Hiérarchie d'héritage  
 `exception`  
  
 `unsupported_os`  
  
## Configuration requise  
 **En\-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
## Voir aussi  
 [concurrency, espace de noms](../../../parallel/concrt/reference/concurrency-namespace.md)