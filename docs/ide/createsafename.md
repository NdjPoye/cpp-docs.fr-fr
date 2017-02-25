---
title: "CreateSafeName | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "CreateSafeName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CreateSafeName (méthode)"
ms.assetid: 3a0dd4af-776d-4c25-aff9-4c539f173cb8
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# CreateSafeName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Génère un nom convivial C\+\+.  
  
## Syntaxe  
  
```  
  
      function CreateSafeName(   
   strName    
);  
```  
  
#### Paramètres  
 `strName`  
 Ancien nom.  
  
## Valeur de retour  
 Nouveau nom sécurisé.  
  
## Notes  
 Appelez cette fonction pour créer un nom C\+\+ convivial à partir d'un nom qui contient des caractères que C\+\+ ne peut utiliser.  Un nom C\+\+ acceptable contient des lettres en majuscules ou en minuscules, des chiffres ou un trait de soulignement \(« \_ »\).  
  
 Cette fonction vérifie l'ancien nom caractère par caractère, en ignorant tous les caractères inutilisables.  Si l'ancien nom ne contient pas de caractères conviviaux, la fonction retourne le nouveau nom en tant que « My ».  Si le nouveau nom convivial commence par un chiffre, cette fonction fait précéder le nouveau nom de « My ».  
  
## Exemple  
  
```  
// Get the project name  
var strProjectName = wizard.FindSymbol("PROJECT_NAME");  
  
// Set the project name to the safe project name.   
var strSafeProjectName = CreateSafeName(strProjectName);  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)