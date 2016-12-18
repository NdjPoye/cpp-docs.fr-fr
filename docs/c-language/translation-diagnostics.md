---
title: "Translation&#160;: Diagnostics | Microsoft Docs"
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
  - "C"
ms.assetid: 3730ca7c-0147-452d-bd4a-6a1e97e9793e
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Translation&#160;: Diagnostics
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**ANSI 2.1.1.3** Comment un diagnostic est identifié  
  
 Microsoft C génère des messages d'erreur au format suivant :  
  
```  
  
filename( line-number ) : diagnostic Cnumber message  
```  
  
 où *filename* est le nom du fichier source dans lequel l'erreur est survenue. *line\-number* correspond au numéro de ligne auquel le compilateur a détecté l'erreur. `diagnostic` est une erreur ou un avertissement. `number` est un seul nombre à quatre chiffres \(précédé d'un **C**, comme indiqué dans la syntaxe\) qui identifie l'erreur ou l'avertissement. `message` est un message explicatif.  
  
## Voir aussi  
 [Comportement défini par l'implémentation](../c-language/implementation-defined-behavior.md)