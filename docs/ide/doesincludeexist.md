---
title: "DoesIncludeExist | Microsoft Docs"
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
  - "DoesIncludeExist"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "DoesIncludeExist (méthode)"
ms.assetid: 39751a3d-dfe5-423c-bd94-a53771c3e360
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# DoesIncludeExist
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Indique si une instruction `#include` pour un fichier d'en\-tête spécifié existe dans un fichier.  
  
## Syntaxe  
  
```  
  
      function DoesIncludeExist(   
   oProj,   
   strHeaderFile,   
   strInsertIntoFile    
);  
```  
  
#### Paramètres  
 `oProj`  
 Projet sélectionné.  
  
 *strHeaderFile*  
 Nom du fichier d'en\-tête à trouver.  
  
 `strInsertIntoFile`  
 Fichier source contenant l'instruction `#include` pour le fichier d'en\-tête \(à l'exclusion du chemin d'accès\).  
  
## Valeur de retour  
 Retourne **true** si le fichier d'en\-tête spécifié est inclus ; sinon **false**.  
  
## Notes  
 Indique si une instruction \#include pour un fichier d'en\-tête spécifique existe dans le fichier spécifié par `strInsertIntoFile`.  
  
## Exemple  
  
```  
// Check to see if #include for atlbase.h   
// is included in the project's stdafx.h.  
// and add it if it is not.  
if (!DoesIncludeExist(selProj, "<atlbase.h>", strSTDAFX))  
   oCM.AddInclude("<atlbase.h>", strSTDAFX, vsCMAddPositionEnd);  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)