---
title: "Champs de sp&#233;cification de format&#160;: fonctions scanf et wscanf | Microsoft Docs"
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
  - "msvcr80.dll"
  - "msvcr110.dll"
  - "msvcr90.dll"
  - "msvcr100.dll"
  - "msvcr110_clr0400.dll"
  - "msvcr120.dll"
apitype: "DLLExport"
f1_keywords: 
  - "wscanf"
  - "scanf"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "largeur, spécifications dans fonction scanf"
  - "spécification de format scanf"
  - "spécification de largeur scanf"
  - "caractères du champ de type scanf"
  - "champs de type, fonction scanf"
  - "champs de spécification de formation pour la fonction scanf"
  - "champs de type"
ms.assetid: 7e95de1b-0b71-4de3-9f81-c9560c78e039
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Champs de sp&#233;cification de format&#160;: fonctions scanf et wscanf
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les informations ici appliquent à toute la famille `scanf` de fonctions, y compris les versions sécurisées et décrivent les symboles utilisés pour dire aux fonctions `scanf` comment analyser le flux d'entrée, tel que le flux d'entrée `stdin` pour `scanf`, dans les valeurs insérées dans des variables de programme.  
  
 Une spécification de format se présente au format suivant.  
  
 `%`\[`*`\] \[[largeur](../c-runtime-library/scanf-width-specification.md)\] \[{[h &#124; l &#124; ll &#124; I64 &#124; L](../c-runtime-library/scanf-width-specification.md)}\][type](../c-runtime-library/scanf-type-field-characters.md)  
  
 L'argument `format` spécifie la traduction de l'entrée et peut contenir un ou plusieurs des éléments suivants :  
  
-   Espaces blancs : espace \(' '\) ; tabulation \('\\t'\) ; ou saut de ligne \('\\n'\).  Un espace blanc engendre que `scanf` lit, mais sans stocker, tous les espaces blancs consécutifs dans l'entrée jusqu'au caractère suivant qui n'est pas un espace blanc.  Un espace blanc au format correspond à tout nombre \(y compris 0\) et toute combinaison d'espaces blancs dans l'entrée.  
  
-   Les caractères qui ne sont pas des espaces blancs, sauf le signe de pourcentage \(`%`\).  Un caractère qui n'est pas un espace blanc engendre que `scanf` lit, mais sans stocker, le caractère correspondant qui n'est pas un espace blanc .  Si le caractère suivant dans le flux d'entrée ne correspond pas, `scanf` se termine.  
  
-   Spécifications de format, introduites par le symbole de pourcentage \(`%`\).  Une spécification de format fait que `scanf` lit et convertit des caractères de l'entrée dans les valeurs d'un type spécifié.  La valeur est affectée à un argument dans la liste d'arguments.  
  
 Le format est lu de gauche à droite.  Il est prévu que les caractères en dehors des spécifications de format correspondent à la séquence de caractères dans le flux d'entrée ; les caractères correspondants dans le flux d'entrée sont analysés mais pas stockés.  Si un caractère du flux d'entrée est en conflit avec la spécification de format, `scanf` se termine, et le caractère doit être conservé dans le flux d'entrée comme s'il n'a pas été lu.  
  
 Lorsque la première spécification de format est produite, la valeur du premier champ d'entrée est convertie selon cette condition et stockée dans l'emplacement spécifié par le premier `argument`.  La deuxième spécification du format fait que le deuxième champ d'entrée est converti et stocké dans le deuxième `argument`, et ainsi de suite jusqu'à la fin de la chaîne de format.  
  
 Un champ d'entrée est défini comme tous les caractères jusqu'au premier espace blanc \(espace, tabulation, ou saut de ligne\), ou jusqu'au premier caractère qui ne peut pas être converti en fonction de la spécification de format, ou jusqu'à ce que la largeur du champ \(le cas échéant\) soit atteinte.  S'il y a trop d'arguments pour les caractéristiques données, des arguments supplémentaires sont évalués mais ignorés.  Les résultats sont imprévisibles s'il n'y a pas assez d'arguments pour la spécification de format.  
  
 Chaque champ de la spécification de format est un caractère unique ou un nombre signifiant une option de mise en forme spécifique.  Le caractère `type`, qui apparaît après le dernier champ facultatif de format, détermine si le champ d'entrée est interprété comme un caractère, une chaînes, ou un nombre.  
  
 La spécification de format la plus simple contient uniquement le signe de pourcentage et un caractère `type` \(par exemple, `%s`\).  Si un pourcentage \(`%`\) est suivi par un caractère qui n'a aucune signification en tant que caractère de format\- contrôle, ce caractère et les caractères suivants \(jusqu'au pourcentage ci\-dessous\) sont traités comme séquence ordinaire de caractères, c. \- à\-d., une séquence de caractères qui doivent correspondre à l'entrée.  Par exemple, pour spécifier qu'un caractère de pourcentage doit être inséré, utilisez `%%`.  
  
 Un astérisque \(`*`\) suivant un pourcentage supprime l'attribution du champ d'entrée suivant, qui est interprété comme un champ du type spécifié.  Le champ est analysé mais pas stocké.  
  
 Les versions sécurisées \(celles avec le suffixe `_s` \) de la famille `scanf` de fonctions requièrent qu'un paramètre de taille de mémoire tampon soit transmis juste après chaque paramètre de type `c`, `C`, `s`, `S` ou `[`.  Pour plus d'informations sur les versions sécurisées de la famille `scanf` de fonctions, consultez [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md).  
  
## Voir aussi  
 [Spécification de largeur scanf](../c-runtime-library/scanf-width-specification.md)   
 [Caractères du champ de type scanf](../c-runtime-library/scanf-type-field-characters.md)   
 [scanf, \_scanf\_l, wscanf, \_wscanf\_l](../c-runtime-library/reference/scanf-scanf-l-wscanf-wscanf-l.md)   
 [scanf\_s, \_scanf\_s\_l, wscanf\_s, \_wscanf\_s\_l](../c-runtime-library/reference/scanf-s-scanf-s-l-wscanf-s-wscanf-s-l.md)