---
title: "GetRuntimeErrorDesc | Microsoft Docs"
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
  - "GetRuntimeErrorDesc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ConversionError (méthode)"
  - "GetRuntimeErrorDesc (méthode)"
  - "RangeError (méthode)"
  - "ReferenceError (méthode)"
  - "RegExpError (méthode)"
  - "SyntaxError (méthode)"
  - "TypeError (méthode)"
  - "URIError (méthode)"
ms.assetid: d56fdd2e-6ad0-4c49-9e98-bcf0105e1b12
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# GetRuntimeErrorDesc
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Retourne une description du type d'exception.  
  
## Syntaxe  
  
```  
  
      function GetRuntimeErrorDesc(   
   strRuntimeErrorName    
);  
```  
  
#### Paramètres  
 *strRuntimeErrorName*  
 Nom du type de l'exception qui s'est produite.  
  
## Valeur de retour  
 Retourne une description du type d'exception.  
  
## Notes  
 Retourne une description du type d'exception.  Il peut s'agir de l'un des types suivants :  
  
|Types d'exception|Description|  
|-----------------------|-----------------|  
|ConversionError|Cette erreur se produit lorsque vous essayez d'effectuer une conversion impossible à réaliser pour un objet.|  
|RangeError|Cette erreur se produit lorsqu'une fonction est spécifiée avec un argument qui est en dehors de la plage autorisée.  Elle se produit, par exemple, si vous tentez de créer un objet `Array` avec une longueur définie par une valeur autre qu'un entier positif.|  
|ReferenceError|Cette erreur se produit en présence d'une référence non valide.  Elle se produit si par exemple la référence attendue a la valeur null.|  
|RegExpError|Cette erreur se produit en présence d'une erreur de compilation avec une expression régulière.  Toutefois, une fois que l'expression régulière est compilée, cette erreur ne peut plus se produire.  Ceci peut arriver, par exemple, lorsqu'une expression régulière est déclarée avec un modèle comportant une syntaxe non valide, avec des indicateurs autres que *i*, *g* ou *m*, ou si le même indicateur est défini plusieurs fois.|  
|SyntaxError|Cette erreur se produit lorsque le texte source est analysé et que sa syntaxe est incorrecte.  Elle se produit, par exemple, si la fonction `eval` est appelée avec un argument ne constituant pas un texte de programme correct.|  
|TypeError|Cette erreur se produit lorsque le type réel d'opérande ne correspond pas au type attendu.  Ce peut être le cas, par exemple, lorsqu'un appel de fonction est effectué sur un élément autre qu'un objet ou ne gérant pas l'appel.|  
|URIError|Cette erreur se produit lorsqu'un indicateur URI \(Uniform Resource Indicator\) non conforme a été détecté.  Elle se produit, par exemple, lorsqu'un caractère non conforme est trouvé dans une chaîne en cours d'encodage ou de décodage.|  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)