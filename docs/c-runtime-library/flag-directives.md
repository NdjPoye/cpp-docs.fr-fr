---
title: "Directives de balise | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr120.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr90.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c.flags"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "directives de balise printf (fonction)"
  - "champs de spécification de formation pour la fonction printf"
  - "directives de balise d'impression"
  - "printf (fonction), champs de spécification de format"
ms.assetid: b00cbdc9-1e5c-4b30-9f56-c1ef8d383767
caps.latest.revision: 12
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 12
---
# Directives de balise
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans une spécification de format, le premier champ facultatif est `flags`.  Une directive de balise est un caractère qui spécifie la justification de sortie et la sortie des signes, des espaces, des zéros non significatifs, des chiffres, et les préfixes octals et hexadécimaux.  Plusieurs indicateurs peuvent apparaître dans une spécification de format, et les indicateurs peuvent apparaître dans n'importe quel ordre.  
  
### Caractères d'indicateur  
  
|Indicateur|Signification|Valeur|  
|----------------|-------------------|------------|  
|`–`|Aligner à gauche le résultat en respectant la largeur disponible.|Aligner les côtés droits|  
|`+`|Utilisez un signe \(\+ ou \-\) pour préfixer la valeur de sortie s'il s'agit d'un type signé.|Le symbole apparaît uniquement pour les valeurs signées négatives \(–\).|  
|`0`|Si `width` est préfixé par `0`, des zéros non significatifs sont ajoutés jusqu'à ce que la largeur minimale soit atteinte.  Si `0` et `–` apparaissent, le`0` est ignoré.  Si `0` est spécifié comme entier \(format`i`, `u`, `x`, `X`, `o`, `d`\) et qu'une spécification de précision est également présente\- par exemple, `%04.d`— `0` est ignoré.|Aucun remplissage.|  
|espace \(' '\)|Utilisez un espace pour préfixer la valeur de sortie si elle est signée positif.  L'espace est ignoré si à la fois l'espace et des indicateurs \+ apparaissent.|Aucun espace ne s'affiche.|  
|`#`|Lorsqu'il est utilisé avec `o`, `x`, ou le format `X`, l'indicateur`#` utilise 0, 0x et 0X, respectivement, pour préfixer une valeur de sortie différente de zéro.|Aucun espace ne s'affiche.|  
||Lorsqu'elle est utilisée avec `e`, `E`, `f`, `a` ou le format `A`, l'indicateur `#` impose à la valeur de sortie de contenir une virgule décimale.|La virgule décimale apparaît uniquement si des chiffres la suivent.|  
||Lorsqu'elle est utilisée avec le format `g` ou `G`, l'indicateur `#` force la valeur de sortie à contenir une virgule et empêché la troncature des zéros de fin.<br /><br /> Ignorés lorsqu'ils sont utilisés avec `c`, `d`, `i`, `u`, ou `s`.|La virgule décimale apparaît uniquement si des chiffres la suivent.  Les zéros à droite sont tronqués.|  
  
## Voir aussi  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Spécification de largeur printf](../c-runtime-library/printf-width-specification.md)   
 [Spécifications de précision](../c-runtime-library/precision-specification.md)   
 [Spécification de taille](../c-runtime-library/size-specification.md)   
 [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md)