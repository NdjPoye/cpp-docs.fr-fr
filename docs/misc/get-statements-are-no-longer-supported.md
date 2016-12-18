---
title: "Les instructions &#39;Get&#39; ne sont plus prises en charge | Microsoft Docs"
ms.custom: ""
ms.date: "12/15/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30829"
  - "bc30829"
helpviewer_keywords: 
  - "BC30829"
ms.assetid: 8d798357-7efb-4423-9808-8b20777b97ba
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Les instructions &#39;Get&#39; ne sont plus prises en charge
Les instructions `Get` ne sont plus prises en charge. La fonctionnalité d’E\/S de fichier est disponible dans l’espace de noms `Microsoft.VisualBasic`.  
  
 `Get` n’est pas pris en charge pour les opérations de fichier et peut être utilisé uniquement dans la syntaxe de procédure de propriété.  
  
 **ID d’erreur :** BC30829  
  
### Pour corriger cette erreur  
  
1.  Effectuez des opérations de fichiers à l’aide des membres des fonctions d’exécution `System.IO`, `FileSystemObject` et [!INCLUDE[vbprvb](../dotnet/includes/vbprvb_md.md)].  
  
## Voir aussi  
 [Processing Drives, Directories, and Files](../Topic/Processing%20Drives,%20Directories,%20and%20Files%20\(Visual%20Basic\).md)   
 [Get Statement](../Topic/Get%20Statement.md)   
 [File Access with Visual Basic](../Topic/File%20Access%20with%20Visual%20Basic.md)