---
title: "Types de caractères | Microsoft Docs"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- character data types [C]
- types [C], character
ms.assetid: d3ca8cda-c0d7-43af-9472-697e8ef015ce
caps.latest.revision: 7
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Human Translation
ms.sourcegitcommit: d6eb43b2e77b11f4c85f6cf7e563fe743d2a7093
ms.openlocfilehash: f0f8639e90787ddcc90b7a302f226d305f29dce1
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="character-types"></a>Types caractère
Une constante caractère entière non précédée de la lettre **L** est de type `int`. La valeur d'une constante caractère entière contenant un seul caractère est la valeur numérique du caractère interprété comme un entier. Par exemple, la valeur numérique du caractère `a` est 97 au format décimal et 61 au format hexadécimal.  
  
 Syntaxiquement, une « constante à caractères larges » est une constante caractère préfixée de la lettre **L**. Une constante à caractères larges est de type `wchar_t`, un type entier défini dans le fichier d'en-tête STDDEF.H. Exemple :  
  
```  
char    schar =  'x';   /* A character constant          */  
wchar_t wchar = L'x';   /* A wide-character constant for   
                            the same character           */  
```  
  
 Les constantes à caractères larges font 16 bits et spécifient des membres du jeu de caractères d'exécution étendu. Elles vous permettent d'exprimer des caractères dans des alphabets qui sont trop étendus pour être représentés par le type `char`. Consultez [Caractères multioctets et larges](../c-language/multibyte-and-wide-characters.md) pour plus d'informations sur les caractères larges.  
  
## <a name="see-also"></a>Voir aussi  
 [Constantes caractère C](../c-language/c-character-constants.md)