---
title: "no_dual_interfaces | Microsoft Docs"
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
  - "no_dual_interfaces"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "no_dual_interfaces (attribut)"
ms.assetid: 9acd5d9d-4a49-4cdc-9470-73a2c23cf512
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# no_dual_interfaces
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à C\+\+**  
  
 Modifie la façon dont le compilateur génère des fonctions wrapper pour les méthodes d'interface double.  
  
## Syntaxe  
  
```  
no_dual_interfaces  
```  
  
## Notes  
 Normalement, le wrapper appelle la méthode via la table de fonctions virtuelles pour l'interface.  Avec `no_dual_interfaces`, le wrapper utilise à la place **IDispatch::Invoke** pour appeler la méthode.  
  
 **FIN de la section spécifique à C\+\+**  
  
## Voir aussi  
 [Attributs \#import](../preprocessor/hash-import-attributes-cpp.md)   
 [\#import, directive](../preprocessor/hash-import-directive-cpp.md)