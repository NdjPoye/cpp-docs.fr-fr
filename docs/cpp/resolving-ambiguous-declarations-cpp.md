---
title: "R&#233;solution d&#39;ambigu&#239;t&#233; | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
ms.assetid: 3d773ee7-bbea-47de-80c2-cb0a9d4ec0b9
caps.latest.revision: 6
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# R&#233;solution d&#39;ambigu&#239;t&#233;
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Pour exécuter des conversions explicites d'un type en un autre, vous devez utiliser des casts, en spécifiant le nom de type voulu.  Certains casts de type entraînent une ambiguïté syntaxique.  Le cast de type de style fonction suivant est ambigu :  
  
```  
char *aName( String( s ) );  
```  
  
 Il est difficile de savoir s'il s'agit d'une déclaration de fonction ou d'une déclaration d'objet avec un cast de style fonction comme initialiseur : il peut déclarer une fonction qui retourne le type **char \*** qui prend un argument de type `String` ou il peut déclarer l'objet `aName` et l'initialiser avec la valeur de `s` castée en type `String`.  
  
 Si une déclaration peut être considérée comme une déclaration de fonction valide, elle est traitée comme telle.  Une instruction est examinée pour voir s'il s'agit d'un cast de type de style fonction seulement si ce peut être une déclaration de fonction, c'est\-à\-dire si elle serait syntaxiquement incorrecte.  Par conséquent, le compilateur considère l'instruction comme une déclaration d'une fonction et ignore les parenthèses autour de l'identificateur `s`.  En revanche, les instructions :  
  
```  
char *aName( (String)s );  
```  
  
 et  
  
```  
char *aName = String( s );  
```  
  
 sont clairement des déclarations d'objets, et une conversion définie par l'utilisateur depuis le type `String` vers le type **char \*** est appelée pour effectuer l'initialisation d'`aName`.  
  
## Voir aussi  
 [C\+\+ Abstract Declarators](http://msdn.microsoft.com/fr-fr/e7e18c18-0cad-4450-942b-d27e1d4dd088)