---
title: "GetMemberfunction | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "GetMemberFunction"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetMemberfunction (méthode)"
ms.assetid: 1e610977-9bc7-4ff2-a79f-132c8e913b4d
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# GetMemberfunction
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelez cette fonction pour obtenir un objet de fonction fondé sur le nom donné.  
  
## Syntaxe  
  
```  
  
      function GetMemberfunction(   
   oClass,   
   strFuncName,   
   oProj    
);  
```  
  
#### Paramètres  
 *oClass*  
 Objet de classe sélectionné.  
  
 `strFuncName`  
 Nom de la fonction à récupérer.  
  
 `oProj`  
 Projet sélectionné.  
  
## Valeur de retour  
 Retourne la fonction indiquée par le paramètre `strFuncName`.  
  
## Notes  
 Appelez cette fonction pour obtenir un objet de fonction fondé sur le nom donné.  Pour plus d'informations, consultez <xref:Microsoft.VisualStudio.VCCodeModel.VCCodeModel.Functions%2A> dans le modèle de code Visual C\+\+.  
  
## Exemple  
  
```  
// Gets the function ExitInstance from the class CWinApp in the   
// current project.  
var oExitInstance = GetMemberFunction(oCWinApp, "ExitInstance", oProj);  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)