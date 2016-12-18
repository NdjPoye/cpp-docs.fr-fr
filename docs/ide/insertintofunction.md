---
title: "InsertIntoFunction | Microsoft Docs"
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
  - "InsertIntoFunction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "InsertIntoFunction (méthode)"
ms.assetid: 50500c3c-bee3-4a9c-a403-7dcd752de23c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# InsertIntoFunction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Fonction utilisée par [AddATLSupportToProject](../ide/addatlsupporttoproject.md) pour insérer le code dans [InitInstance](../Topic/CWinApp::InitInstance.md).  
  
## Syntaxe  
  
```  
  
      function InsertIntoFunction(   
   oFunction,   
   strSearchString,   
   nStartLine,   
   nEndLine,   
   bInsideIfBlock    
);  
```  
  
#### Paramètres  
 *oFunction*  
 Objet de fonction dans lequel l'insertion est effectuée.  
  
 `strSearchString`  
 Chaîne à rechercher pour déterminer le point d'insertion.  
  
 *nStartLine*  
 Ligne de départ à passer à [GetCodeForInitInstance](../ide/getcodeforinitinstance.md).  
  
 *nEndLine*  
 Ligne de fin à passer à [GetCodeForInitInstance](../ide/getcodeforinitinstance.md).  
  
 *bInsideIfBlock*  
 Indique si l'insertion est réalisée dans un bloc de fonction.  
  
## Valeur de retour  
 Retourne **true** si l'insertion est réussie ; sinon **false**.  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [GetMemberfunction](../ide/getmemberfunction.md)