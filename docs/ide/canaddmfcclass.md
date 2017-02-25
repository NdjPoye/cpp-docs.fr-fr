---
title: "CanAddMFCClass | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CanAddMFCClass"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CanAddMFCClass (méthode)"
ms.assetid: 6a97a410-b028-4aad-9b06-04c12cf481eb
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CanAddMFCClass
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'Assistant appelle cette fonction pour vérifier que l'utilisateur peut ajouter une classe MFC au projet.  
  
## Syntaxe  
  
```  
  
      function CanAddMFCClass(   
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
 Retourne la valeur **true** si la classe peut être ajoutée et la valeur **false** si l'utilisateur appelle la fonction pour un projet qui n'est pas un projet MFC et ne prend pas en charge MFC.  
  
## Notes  
 L'Assistant appelle cette fonction pour vérifier si le projet est compatible avec l'Assistant Code sur le point d'être exécuté \(en d'autres termes, s'il peut accepter une classe MFC\).  
  
 L'Assistant appelle cette fonction lorsque le paramètre PREPROCESS\_FUNCTION figure dans le [fichier .vsz du contrôle du projet](../ide/dot-vsz-file-project-control.md) et vérifie si le [modèle de code Visual C\+\+](http://msdn.microsoft.com/fr-fr/dd6452c2-1054-44a1-b0eb-639a94a1216b) est disponible.  Si ce n'est pas le cas, la fonction signale une erreur et retourne **false**.  
  
## Exemple  
  
```  
// Determine if an MFC class can be added to the project  
if (CanAddMFCClass(selProj, selObj))  
{  
   return true;  
}  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [CanAddClass](../ide/canaddclass.md)   
 [CanAddATLClass](../ide/canaddatlclass.md)   
 [IsMFCProject](../ide/ismfcproject.md)