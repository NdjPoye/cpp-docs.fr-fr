---
title: "IsMFCProject | Microsoft Docs"
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
  - "IsMFCProject"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "IsMFCProject (méthode)"
ms.assetid: 98dd57df-9fdb-40d7-afcf-4b99e9d54dad
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# IsMFCProject
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vérifie si un projet est fondé sur MFC.  
  
## Syntaxe  
  
```  
  
      function IsMFCProject(   
   oProj,   
   bCWinAppRequired    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
 *bCWinAppRequired*  
 Indique si les DLL d'extension font partie de la vérification.  
  
## Valeur de retour  
 Retourne **true** si le projet est fondé sur MFC ; sinon **false**.  
  
## Notes  
 Utilisez cette fonction pour déterminer si le projet sélectionné est de type MFC.  
  
## Exemple  
  
```  
if (!IsMFCProject(selProj, true))  
   {  
      if (gbExceptionThrown)  
         return false;  
      var L_ErrMsg2_Text = "ATL support can only be added to MFC EXEs or MFC Regular DLLs.";  
      wizard.ReportError(L_ErrMsg2_Text);  
      return false;  
   }  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [IsATLProject](../ide/isatlproject.md)   
 [IsAttributedProject](../ide/isattributedproject.md)