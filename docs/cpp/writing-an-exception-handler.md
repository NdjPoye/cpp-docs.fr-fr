---
title: "&#201;criture d&#39;un gestionnaire d&#39;exceptions | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion des exceptions, gestionnaires d'exceptions"
  - "gestion structurée des exceptions, gestionnaires d'exceptions"
ms.assetid: 71473fee-f773-4a34-bf12-82a3af79579c
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# &#201;criture d&#39;un gestionnaire d&#39;exceptions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les gestionnaires d'exceptions sont généralement utilisés pour répondre à des erreurs spécifiques.  Vous pouvez utiliser la syntaxe de gestion des exceptions pour filtrer les exceptions autres que celles que vous savez gérer.  D'autres exceptions doivent être passées à d'autres gestionnaires \(éventuellement dans la bibliothèque Runtime ou dans le système d'exploitation\) écrits pour rechercher ces exceptions spécifiques.  
  
 Les gestionnaires d'exceptions utilisent l'instruction try\-except.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Instruction try\-except](../cpp/try-except-statement.md)  
  
-   [Écriture d'un filtre d'exception](../cpp/writing-an-exception-filter.md)  
  
-   [Déclenchement d'exceptions logicielles](../cpp/raising-software-exceptions.md)  
  
-   [Exceptions matérielles](../cpp/hardware-exceptions.md)  
  
-   [Restrictions applicables aux gestionnaires d'exceptions](../cpp/restrictions-on-exception-handlers.md)  
  
## Voir aussi  
 [Gestion structurée des exceptions](../cpp/structured-exception-handling-c-cpp.md)