---
title: "Assignation de caract&#232;re | Microsoft Docs"
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
helpviewer_keywords: 
  - "caractères (C++), assignations"
  - "MBCS (C++), assignation de caractère"
ms.assetid: dcc329cd-92df-4e20-817d-364be62ff28f
caps.latest.revision: 9
caps.handback.revision: 9
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# Assignation de caract&#232;re
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans l'exemple suivant la boucle `while` analyse une chaîne et copie tous les caractères à l'exception de « X » dans une autre chaîne :  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
        *sz1++ = *sz2++;  
    else  
        sz2++;  
}  
```  
  
 Le code copie l'octet situé au niveau `sz2` à l'emplacement vers lequel pointe `sz1`, puis incrémente `sz1` pour recevoir l'octet suivant.  Mais si le caractère suivant dans `sz2` est un caractère codé sur deux octets, l'assignation à `sz1` copie uniquement le premier octet.  Le code suivant utilise une fonction portable pour copier le caractère et une autre pour incrémenter `sz1` et `sz2` correctement :  
  
```  
while( *sz2 )  
{  
    if( *sz2 != 'X' )  
    {  
        _mbscpy_s( sz1, 1, sz2 );  
        sz1 = _mbsinc( sz1 );  
        sz2 = _mbsinc( sz2 );  
    }  
    else  
        sz2 = _mbsinc( sz2 );  
}  
```  
  
## Voir aussi  
 [Conseils de programmation MBCS](../text/mbcs-programming-tips.md)   
 [Comparaison de caractères](../text/character-comparison.md)