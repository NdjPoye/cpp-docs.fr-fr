---
title: "Les caract&#232;res de type ne sont pas autoris&#233;s pour les alias Imports | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc31398"
  - "BC31398"
helpviewer_keywords: 
  - "BC31398"
ms.assetid: 0620669d-b529-49f3-9deb-aeda4dacc58a
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les caract&#232;res de type ne sont pas autoris&#233;s pour les alias Imports
Un alias d’importation dans une instruction `Imports` contient au moins un caractère de type d’identificateur.  
  
 Un alias d’importation doit être un nom Visual Basic valide. Les caractères autorisés n’incluent pas les caractères de type d’identificateur \(`%`, `&`, `@`, `!`, `#` et `$`\). Consultez [Declared Element Names](../Topic/Declared%20Element%20Names%20\(Visual%20Basic\).md).  
  
 **ID d’erreur :** BC31398  
  
### Pour corriger cette erreur  
  
-   Supprimez les caractères de type d’identificateur de l’alias d’importation.  
  
## Voir aussi  
 [Type Characters](../Topic/Type%20Characters%20\(Visual%20Basic\).md)   
 [Declared Element Names](../Topic/Declared%20Element%20Names%20\(Visual%20Basic\).md)   
 [Imports Statement \(.NET Namespace and Type\)](../Topic/Imports%20Statement%20\(.NET%20Namespace%20and%20Type\).md)   
 [NOTINBUILD : Résolution d’une référence quand plusieurs variables portent le même nom](http://msdn.microsoft.com/fr-fr/9601e39f-1911-44e1-ace5-3f6e090408b9)