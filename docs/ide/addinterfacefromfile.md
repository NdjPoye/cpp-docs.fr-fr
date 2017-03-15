---
title: "AddInterfaceFromFile | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "AddInterfaceFromFile"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AddInterfaceFromFile (méthode)"
ms.assetid: fa848690-ad98-4fb4-bbcf-dffcaad05df2
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# AddInterfaceFromFile
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère le rendu et insère un fichier modèle qui contient une interface.  
  
## Syntaxe  
  
```  
  
      function AddInterfaceFromFile(   
   oCM,   
   strInterfaceFile    
);  
```  
  
#### Paramètres  
 `oCM`  
 Objet [Visual C\+\+ Code Model](http://msdn.microsoft.com/fr-fr/dd6452c2-1054-44a1-b0eb-639a94a1216b).  
  
 *strInterfaceFile*  
 Nom du fichier modèle uniquement, sans le chemin d'accès.  
  
## Notes  
 Appelez cette fonction pour afficher et insérer dans le fichier .idl du projet un fichier modèle qui contient une interface.  
  
 Si l'interface n'est pas ajoutée correctement, cette fonction affiche un message d'erreur.  
  
## Exemple  
  
```  
// Render myint.idl and insert into strProject.idl  
AddInterfaceFromFile(oCM, "myint.idl");  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)