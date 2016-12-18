---
title: "Directives de mod&#232;le | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "[!else] (directive de modèle)"
  - "[!endif] (directive de modèle)"
  - "[!endloop] (directive de modèle)"
  - "[!if] (directive de modèle)"
  - "[!loop] (directive de modèle)"
  - "[!output] (directive de modèle)"
  - "Assistants personnalisés, directives de modèle"
  - "directives, directives de modèle"
  - "directive [!else]"
  - "directive [!endif]"
  - "directive [!endloop]"
  - "directive [!if]"
  - "directive [!loop]"
  - "directive [!output]"
  - "directives de modèle"
ms.assetid: b6204153-813a-423c-b044-e39c352cc5af
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Directives de mod&#232;le
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser les directives de modèle ci\-dessous dans un [fichier modèle](../ide/template-files.md) d'Assistant et dans le [fichier Templates.inf](../ide/templates-inf-file.md) pour personnaliser l'Assistant.  
  
|Directive|Description|  
|---------------|-----------------|  
|\[\!  if \]|Commence une structure de contrôle qui vérifie une condition.|  
|\[\!  else \]|Composant  de la structure de contrôle \[\! if \].  Vérifie une autre condition.|  
|\[\!  endif \]|Termine la définition d'un \[ \!  de la structure de contrôle \[\! if \].|  
|\[\!  output \]|Utilisable de deux façons :<br /><br /> -   \[\!  output "string" \] donne la chaîne.<br />-   \[\!  output SYMBOL\_STRING \] donne la valeur du symbole SYMBOL\_STRING.|  
|\[\!  loop \]|Utilisable de deux façons :<br /><br /> -   \[\!  loop \= 5 \]<br />-   \[\!  loop \= *NUM\_OF\_PAGES* \] où *NUM\_OF\_PAGES* est un symbole avec une valeur numérique.|  
|\[\!  endloop \]|Termine une structure de boucle.|  
  
 Le crochet gauche \(\[\) suivi immédiatement d'un point d'exclamation \(\!\) indique le début d'une directive de modèle.  Le crochet droit indique la fin d'une directive de modèle.  La syntaxe requise est :  
  
```  
[!directive params]  
```  
  
 un espace ou un caractère non\-identificateur n'est obligatoire qu'entre *directive*  et  *params*.  
  
## Exemple  
  
```  
[!if SAMPLE_RADIO_OPTION1]  
You have checked the option 'Sample radio button option 1'  
[!else]  
You have checked the option 'Sample radio button option 2'  
[!endif]  
```  
  
 Vous pouvez utiliser les opérateurs suivants avec les directives ci\-dessus dans un fichier modèle.  
  
```  
+  
-     
=  
!=     
==     
||     
&&    
!  
```  
  
## Exemple  
  
```  
[!if SYMBOL_STRING != 0]  
```  
  
## Voir aussi  
 [Fichiers créés pour votre Assistant](../ide/files-created-for-your-wizard.md)   
 [Assistant personnalisé](../ide/custom-wizard.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)