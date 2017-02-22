---
title: "Sp&#233;cification de largeur printf | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr110.dll"
  - "msvcr80.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr90.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "printf (fonction), champs de spécification de format"
  - "printf (fonction), spécification de largeur"
ms.assetid: 8b4a1b1e-bf6e-414f-a1b6-a9b6f1b6ce92
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Sp&#233;cification de largeur printf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans une spécification de format, le deuxième champ facultatif est la spécification de la largeur.  L'argument `width` est un entier décimal non négatif qui contrôle le nombre minimal de caractères qui sont générés.  Si le nombre de caractères dans la valeur de sortie est inférieure à la longueur spécifiée, des espaces sont ajoutés à gauche ou à droite des valeurs , selon que l'indicateur gauche d'alignement \(`-`\) est spécifié ou non\- jusqu'à ce que la largeur minimale soit atteinte.  Si `width` est préfixé par 0, des zéros non significatifs sont ajoutés aux conversions de type entier ou de type nombre à virgule flottante, jusqu'à ce que la largeur minimale soit atteinte, sauf lorsque la conversion est vers un infini ou vers un NAN.  
  
 La spécification de largeur ne provoque jamais la troncature d'une valeur.  Si le nombre de caractères dans la valeur de sortie est supérieur à la longueur spécifiée, ou si `width` n'est pas spécifié, tous les caractères de la valeur sont générés, en fonction de la spécification de [précision](../c-runtime-library/precision-specification.md).  
  
 Si la spécification de largeur est un astérisque \(`*`\), un argument `int` de la liste d'arguments fournit la valeur.  Dans la liste des arguments, l'argument de `width` doit précéder la valeur qui est mise en forme, comme illustré dans l'exemple suivant :  
  
 `printf("%0*f", 5, 3);  /* 00003 is output */`  
  
 Une valeur `width` manquante ou petite dans une spécification de format n'entraîne pas la troncation d'une valeur de sortie.  Si le résultat d'une conversion est plus important que la valeur `width`, le champ peut être développé pour contenir le résultat de conversion.  
  
## Voir aussi  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Directives de balise](../c-runtime-library/flag-directives.md)   
 [Spécifications de précision](../c-runtime-library/precision-specification.md)   
 [Spécification de taille](../c-runtime-library/size-specification.md)   
 [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md)