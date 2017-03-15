---
title: "OffsetToLineNumber | Microsoft Docs"
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
  - "OffsetToLineNumber"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "OffsetToLineNumber (fonction)"
ms.assetid: ac7e3c22-6b3b-432c-85cc-b50bbef9ce8c
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# OffsetToLineNumber
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Appelée par [InsertIntoFunction](../ide/insertintofunction.md) pour convertir un index dans le corps d'une fonction en numéro de ligne.  
  
## Syntaxe  
  
```  
  
      function OffsetToLineNumber(   
   strString,   
   nPos    
);  
```  
  
#### Paramètres  
 `strString`  
 Chaîne contenant le corps de la fonction.  Le corps de la fonction est une chaîne multiligne dans laquelle les lignes sont déterminées par des paires de caractères CR\-LF.  
  
 `nPos`  
 Position dans la chaîne.  
  
## Valeur de retour  
 Retourne la ligne dans le corps de la fonction où se trouve `nPos`.  La première ligne de la fonction commence en principe à la ligne 1 \(et non 0\).  
  
## Notes  
 Recherche le numéro de ligne pour une position donnée dans le corps d'une fonction.  
  
 Cette fonction est appelée par `InsertIntoFunction` pour convertir l'index situé à la position `nPos` dans le corps d'une fonction en numéro de ligne.  
  
## Exemple  
  
```  
strString = "function DelFile(fso,  
 strWizTempFile)\r\n{\r\n\ttry\r\n\t{\r\nif   
(fso.FileExists(strWizTempFile))\r\nreturn true;\r\n";  
  
nLine =  OffsetToLineNumber(strString, 60);  
  
// The return value for the above is 5, because character 60 in the string   
// occurs in the 5th line within the string.  
```  
  
## Voir aussi  
 [Personnalisation des Assistants C\+\+ à l'aide des fonctions JScript classiques](../ide/customizing-cpp-wizards-with-common-jscript-functions.md)   
 [Fonctions JScript des Assistants C\+\+](../ide/jscript-functions-for-cpp-wizards.md)   
 [Création d’un Assistant personnalisé](../ide/creating-a-custom-wizard.md)   
 [Conception d'un Assistant](../ide/designing-a-wizard.md)   
 [LineBeginsWith](../ide/linebeginswith.md)