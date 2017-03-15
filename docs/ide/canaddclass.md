---
title: "CanAddClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddClass (méthode)"
ms.assetid: 76739742-1e34-470c-910d-8784f0adfbf0
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette fonction est appelée par l'Assistant pour vérifier si le projet est compatible avec l'Assistant code que l'utilisateur essaie d'exécuter.  
  
## Syntaxe  
  
```  
  
      function CanAddClass(   
   oProj,   
   oObject    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
 `oObject`  
 Objet sélectionné.  Dans ce cas, le projet en cours.  
  
## Valeur de retour  
 Retourne **true** si la classe peut être ajoutée ; sinon **false**  
  
## Notes  
 L'Assistant appelle cette fonction lorsqu'il trouve le paramètre PREPROCESS\_FUNCTION dans le [fichier .vsz du contrôle du projet](../ide/dot-vsz-file-project-control.md).  
  
 Il vérifie si l'objet du [modèle de code Visual C\+\+](http://msdn.microsoft.com/fr-fr/dd6452c2-1054-44a1-b0eb-639a94a1216b) est disponible.  Si ce n'est pas le cas, la fonction signale une erreur et retourne **false**.  
  
## Exemple  
  
```  
// Determine if a class can be added to the project  
if (CanAddClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [CanAddMFCClass](../ide/canaddmfcclass.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)