---
title: "IncludeCodeElementDeclaration | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "IncludeCodeElementDeclaration"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IncludeCodeElementDeclaration (méthode)"
ms.assetid: 714e76e4-76bc-439a-982a-cf9d4ada7677
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# IncludeCodeElementDeclaration
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ajoute l'instruction d'inclusion au paramètre `strInFile`, notamment l'en\-tête dans lequel le paramètre `strCodeElemName` est implémenté, si un en\-tête de ce type est trouvé dans le paramètre `oProj`.  
  
## Syntaxe  
  
```  
  
      function IncludeCodeElementDeclaration(   
   oProj,   
   strCodeElemName,   
   strInFile    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
 `strCodeElemName`  
 Nom complet de l'élément de code pour lequel vous recherchez l'en\-tête de définition.  
  
 `strInFile`  
 Fichier incluant l'en\-tête de définition, si celui\-ci existe.  
  
## Notes  
 Ajoute l'instruction d'inclusion au paramètre `strInFile`, notamment l'en\-tête dans lequel le paramètre `strCodeElemName` est implémenté, si un en\-tête de ce type est trouvé dans le paramètre `oProj`.  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)