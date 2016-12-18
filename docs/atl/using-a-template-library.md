---
title: "Using a Template Library | Microsoft Docs"
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
helpviewer_keywords: 
  - "template libraries"
ms.assetid: 5e80ec6e-a61c-41ce-b34b-9a6252c46265
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Using a Template Library
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un modèle ressemble une macro.  Comme avec une macro, appeler un modèle pour le développement \(avec la substitution de paramètres appropriée\) pour vous code ont entré.  Toutefois, un modèle devient plus loin que cela autoriser la création de nouvelles classes basé sur les types que vous passez en tant que paramètres.  Ces nouvelles classes implémentent des utilisations sécurisées d'exécuter l'opération exprimée dans votre code du modèle.  
  
 Les bibliothèques de modèles telles qu'ATL diffèrent des bibliothèques de classes traditionnelles C\+\+ dans la mesure où elles sont généralement fournis uniquement comme code source \(ou en tant que code source avec, moment de l'exécution de prise en charge\) et ne sont pas fondamentalement hiérarchiques ou nécessairement en nature.  Au lieu de dériver d'une classe pour vous accéder à la fonctionnalité, vous désirez instancient une classe à partir d'un modèle.  
  
## Voir aussi  
 [Introduction to ATL](../atl/introduction-to-atl.md)