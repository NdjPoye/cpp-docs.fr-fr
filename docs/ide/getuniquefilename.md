---
title: "GetUniqueFileName | Microsoft Docs"
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
  - "GetUniqueFileName"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "GetUniqueFilename (méthode)"
ms.assetid: f9760e1a-82d0-4d8b-b00a-6f4c36f6b2c6
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetUniqueFileName
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne un nom de fichier unique.  
  
## Syntaxe  
  
```  
  
      function GetUniqueFileName(   
   strDirectory,   
   strFileName    
);  
```  
  
#### Paramètres  
 *strDirectory*  
 Répertoire dans lequel le nom du fichier doit être recherché.  
  
 `strFileName`  
 Nom du fichier à vérifier.  
  
## Valeur de retour  
 Cette fonction retourne le nom du fichier indiqué dans le paramètre `strFileName` s'il est unique ; sinon, elle retourne le paramètre `strFileName`, suivi d'un numéro allant de 1 à 9999999.  En l'absence du paramètre `strFileName`, cette fonction retourne un nom de fichier unique à l'aide de la [méthode GetTempName](jsmthGetTempName).  
  
## Notes  
 Retourne un nom de fichier unique.  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [GetProjectFile](../ide/getprojectfile.md)