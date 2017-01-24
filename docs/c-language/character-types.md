---
title: "Types caract&#232;re | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "types de données caractère (C)"
  - "types (C), caractère"
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Types caract&#232;re
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une constante caractère entière non précédée de la lettre **L** est de type `int`.  La valeur d'une constante caractère entière contenant un seul caractère est la valeur numérique du caractère interprété comme un entier.  Par exemple, la valeur numérique du caractère `a` est 97 au format décimal et 61 au format hexadécimal.  
  
 Syntaxiquement, une « constante à caractères larges » est une constante caractère préfixée de la lettre **L**.  Une constante à caractères larges est de type `wchar_t`, un type entier défini dans le fichier d'en\-tête STDDEF.H.  Par exemple :  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Les constantes à caractères larges font 16 bits et spécifient des membres du jeu de caractères d'exécution étendu.  Elles vous permettent d'exprimer des caractères dans des alphabets qui sont trop étendus pour être représentés par le type `char`.  Consultez [Caractères multioctets et larges](../c-language/multibyte-and-wide-characters.md) pour plus d'informations sur les caractères larges.  
  
## Voir aussi  
 [Constantes caractère C](../c-language/c-character-constants.md)