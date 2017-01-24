---
title: "OnWizFinish | Microsoft Docs"
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
  - "OnWizFinish"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OnWizFinish (méthode)"
ms.assetid: 5e0790c3-c5b4-43de-b9db-b18d07c19f41
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OnWizFinish
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelée à partir du script HTML de l'Assistant lorsque l'utilisateur clique sur **Terminer**.  Cette fonction appelle à son tour la fonction **Finish** du contrôle de l'Assistant.  
  
## Syntaxe  
  
```  
  
      function OnWizFinish(   
   document    
);  
```  
  
#### Paramètres  
 `document`  
 Objet de document HTML.  
  
## Notes  
 Cette fonction est appelée à partir du script HTML de l'Assistant lorsque l'utilisateur clique sur **Terminer**.  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)