---
title: "LineBeginsWith | Microsoft Docs"
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
  - "LineBeginsWith"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LineBeginsWith (méthode)"
ms.assetid: cbdd08ad-7309-4504-9f23-1c22bb3e4bd0
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# LineBeginsWith
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelée par [InsertIntoFunction](../ide/insertintofunction.md) pour déterminer si une ligne commence par la chaîne spécifiée.  
  
## Syntaxe  
  
```  
  
      function LineBeginsWith(   
   strBody,   
   strSearchString,   
   nStartPos    
);  
```  
  
#### Paramètres  
 *strBody*  
 Corps de la fonction.  
  
 `strSearchString`  
 Chaîne à rechercher.  
  
 *nStartPos*  
 Position de départ de la recherche.  
  
## Valeur de retour  
 Retourne **true** si la chaîne est trouvée ; sinon **false**.  
  
## Notes  
 Cette fonction est appelée par `InsertIntoFunction` pour déterminer si la ligne indiquée commence par la chaîne spécifiée.  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [OffsetToLineNumber](../ide/offsettolinenumber.md)