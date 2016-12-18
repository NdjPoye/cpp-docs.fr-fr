---
title: "Sp&#233;cifications de pr&#233;cision | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
apilocation: 
  - "msvcr100.dll"
  - "msvcr120.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr80.dll"
apitype: "DLLExport"
f1_keywords: 
  - "c.math"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "printf (fonction), champs de spécification de format"
ms.assetid: dc59ea4e-d23a-4f1f-9881-2c919ebefb82
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Sp&#233;cifications de pr&#233;cision
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans une spécification de format, le troisième champ facultatif est la spécification de précision.  Il se compose d'un point \(.\) suivi d'un entier décimal non négatif qui, selon le type de conversion, spécifie le nombre de caractères de chaîne, le nombre de décimales, ou le nombre de chiffres significatifs à obtenir en sortie.  
  
 Contrairement à la spécification de largeur, la spécification de précision peut entraîner soit la troncature de la valeur de sortie soit l'arrondi à une valeur flottante.  Si `precision` est spécifié comme 0 et que la valeur à convertir est 0, le résultat n'a aucun caractère de sortie, comme illustré dans l'exemple suivant :  
  
 `printf( "%.0d", 0 );      /* No characters output */`  
  
 Si la spécification de précision est un astérisque \(\*\), un argument `int` de la liste d'arguments fournit la valeur.  Dans la liste des arguments, l'argument de `precision` doit précéder la valeur qui est mise en forme, comme illustré dans l'exemple suivant :  
  
 `printf( "%.*f", 3, 3.14159265 );  /* 3.142 output */`  
  
 Le type détermine la traduction de`precision` ou la précision par défaut lorsque `precision` est omis, comme indiqué dans le tableau suivant.  
  
### Comment la valeur de precision affecte les types  
  
|Type|Signification|Valeur|  
|----------|-------------------|------------|  
|`a`, `A`|La précision spécifie le nombre de chiffres après le point.|La Précision par défaut est 6.  Si la précision est 0, aucune virgule n'est imprimée à moins que l'indicateur `#` ne soit utilisé.|  
|`c`, `C`|La précision n'a aucun effet.|Le Caractère est imprimé.|  
|`d`, `i`, `u`, `o`, `x`, `X`|La précision spécifie le nombre minimal de chiffres à imprimer.  Si le nombre de chiffres dans l'argument est inférieur à `precision`, la valeur de sortie est terminée à gauche par des zéros.  La valeur n'est pas tronqué lorsque le nombre de chiffres dépasse `precision`.|La Précision par défaut est 1.|  
|`e`, `E`|La précision indique le nombre de chiffres à etre imprimé après la virgule.  Le dernier chiffre imprimé est arrondi.|La Précision par défaut est 6.  Si `precision` est 0 et que le point \(.\) apparaît sans qu'un chiffre le suive, aucune virgule n'est imprimée.|  
|`f`|Le spécificateur de précision indique le nombre de chiffres voulu après la virgule décimale.  Si une virgule décimale s'affiche, au moins un chiffre apparaît avant celle\-ci.  La valeur est arrondie au nombre approprié de chiffres.|La Précision par défaut est 6.  Si `precision` est 0, ou que le point \(.\) apparaît sans qu'un chiffre le suive, aucune virgule n'est imprimée.|  
|`g`, `G`|La précision spécifie le nombre maximal de chiffres significatifs imprimés.|Six chiffres significatifs sont imprimés, et les zéros à droite sont tronqués.|  
|`s`, `S`|La précision spécifie le nombre maximal de caractères à imprimer.  Les caractères excédant `precision` ne sont pas imprimés.|Les caractères sont imprimés jusqu'à ce qu'un caractère NULL soit rencontré.|  
  
## Voir aussi  
 [printf, \_printf\_l, wprintf, \_wprintf\_l](../c-runtime-library/reference/printf-printf-l-wprintf-wprintf-l.md)   
 [Syntaxe de spécification de format : fonctions printf et wprintf](../c-runtime-library/format-specification-syntax-printf-and-wprintf-functions.md)   
 [Directives de balise](../c-runtime-library/flag-directives.md)   
 [Spécification de largeur printf](../c-runtime-library/printf-width-specification.md)   
 [Spécification de taille](../c-runtime-library/size-specification.md)   
 [Caractères du champ de type printf](../c-runtime-library/printf-type-field-characters.md)