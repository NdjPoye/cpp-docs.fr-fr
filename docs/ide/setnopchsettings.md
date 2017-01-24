---
title: "SetNoPchSettings | Microsoft Docs"
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
  - "SetNoPchSettings"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SetNoPchSettings (méthode)"
ms.assetid: 52373c98-ad5e-4e9b-9e0f-9f58ddb2a636
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# SetNoPchSettings
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Définit les propriétés de configuration d'un projet lorsque aucun en\-tête précompilé n'est utilisé.  
  
## Syntaxe  
  
```  
  
      function SetNoPchSettings(   
   oProj    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
## Notes  
 Appelez cette fonction pour configurer le projet lorsque celui\-ci n'utilise aucun paramètre d'en\-tête précompilé.  
  
## Exemple  
 Consultez l'option [SetCommonPchSettings](../ide/setcommonpchsettings.md).  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [SetCommonPchSettings](../ide/setcommonpchsettings.md)   
 [AddCommonConfig](../ide/addcommonconfig.md)