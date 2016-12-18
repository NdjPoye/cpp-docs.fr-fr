---
title: "&#39;}&#39; attendu | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vbc30370"
  - "bc30370"
helpviewer_keywords: 
  - "BC30370"
ms.assetid: a4ce9be9-fc5d-46ec-a217-c3428bd0b97e
caps.latest.revision: 9
caps.handback.revision: 9
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# &#39;}&#39; attendu
Un initialiseur de tableau ou une liste de contraintes n’ont pas été terminés de façon valide.  
  
 Les valeurs d’éléments utilisées pour initialiser le tableau doivent être mises entre accolades \(`{}`\).  
  
```  
Dim demoArray() As Integer = New Integer() {1, 2, 3}   
```  
  
 De même, les contraintes d’une liste de contraintes appliquée à un paramètre de type générique doivent être mises entre accolades.  
  
```  
Public Class dictionaryMaker(Of t As {IComparable, IDisposable, New})   
```  
  
 **ID d’erreur :** BC30370  
  
### Pour corriger cette erreur  
  
-   Utilisez « } » pour terminer l’initialiseur de tableau ou la liste de contraintes.  
  
## Voir aussi  
 [Tableaux](../Topic/Arrays%20in%20Visual%20Basic.md)   
 [How to: Initialize an Array Variable in Visual Basic](../Topic/How%20to:%20Initialize%20an%20Array%20Variable%20in%20Visual%20Basic.md)   
 [Type List](../Topic/Type%20List%20\(Visual%20Basic\).md)   
 [Types génériques Visual Basic](../Topic/Generic%20Types%20in%20Visual%20Basic%20\(Visual%20Basic\).md)