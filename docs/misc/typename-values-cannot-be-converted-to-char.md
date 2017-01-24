---
title: "Impossible de convertir les valeurs &#39;&lt;nom_type&gt;&#39; en &#39;Char&#39; | Microsoft Docs"
ms.custom: ""
ms.date: "11/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-visual-basic"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "bc32007"
  - "vbc32007"
helpviewer_keywords: 
  - "BC32007"
ms.assetid: b04212da-57ac-4493-9480-04c12b50f875
caps.latest.revision: 8
caps.handback.revision: 8
author: "stevehoag"
ms.author: "shoag"
manager: "wpickett"
---
# Impossible de convertir les valeurs &#39;&lt;nom_type&gt;&#39; en &#39;Char&#39;
Impossible de convertir les valeurs '\<nom\_type\>' en Char. Utilisez Microsoft.VisualBasic.ChrW pour interpréter une valeur numérique en tant que caractère Unicode ou convertissez\-la d’abord en 'String' pour obtenir un chiffre.  
  
 Une expression tente de convertir un type de données autre que `String` ou `Object` en `Char`.  
  
 **ID d’erreur :** BC32007  
  
### Pour corriger cette erreur  
  
-   Utilisez la fonction `ChrW` pour convertir une valeur numérique en caractère Unicode ou convertissez d’abord la valeur en `String` puis en `Char`.  
  
## Voir aussi  
 [NOT IN BUILD : Chr, ChrW, fonctions](http://msdn.microsoft.com/fr-fr/37f3c707-8a6f-4c51-9b02-9e634c4299ab)   
 [Implicit and Explicit Conversions](../Topic/Implicit%20and%20Explicit%20Conversions%20\(Visual%20Basic\).md)   
 [Char Data Type](../Topic/Char%20Data%20Type%20\(Visual%20Basic\).md)