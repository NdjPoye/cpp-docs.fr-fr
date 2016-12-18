---
title: "IsATLProject | Microsoft Docs"
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
  - "IsATLProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsATLProject (méthode)"
ms.assetid: 811115af-5bcd-4ce2-a514-34de4c7419ea
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IsATLProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si le projet est fondé sur ATL.  
  
## Syntaxe  
  
```  
  
      function IsATLProject(   
   oProj    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
## Valeur de retour  
 Retourne **true** si le projet est de type ATL ; sinon **false**.  
  
## Notes  
 Indique si le projet est fondé sur ATL.  
  
## Exemple  
  
```  
function CanAddATLSupport(selProj, selObj)  
{  
   if (IsATLProject(selProj))  
   {  
      var L_ErrMsg1_Text = "Current project already has ATL support.";  
      wizard.ReportError(L_ErrMsg1_Text);  
      return false;  
   }  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [IsAttributedProject](../ide/isattributedproject.md)