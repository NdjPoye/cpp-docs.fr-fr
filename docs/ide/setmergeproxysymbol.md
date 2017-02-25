---
title: "SetMergeProxySymbol | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SetMergeProxySymbol"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetMergeProxySymbol (méthode)"
ms.assetid: d6a9db59-2d5b-4431-98bc-785675e0eafe
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# SetMergeProxySymbol
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette fonction est appelée par l'Assistant pour ajouter le symbole \_MERGE\_PROXYSTUB, si nécessaire.  
  
## Syntaxe  
  
```  
  
      function SetMergeProxySymbol(   
   oProj    
);  
```  
  
#### Paramètres  
 `oProj`  
 Objet projet sélectionné.  
  
## Notes  
 Cette fonction est appelée par l'Assistant pour ajouter le symbole \_MERGE\_PROXYSTUB, si nécessaire.  
  
## Exemple  
  
```  
SetMergeProxySymbol (selproj);  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)