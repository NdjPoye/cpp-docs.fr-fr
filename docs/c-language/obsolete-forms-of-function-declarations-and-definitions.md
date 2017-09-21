---
title: "Formes obsolètes des déclarations et définitions de fonctions | Microsoft Docs"
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
- old style function declarations
ms.assetid: 67c5038f-0529-4f29-9d0f-c27580977b50
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
ms.openlocfilehash: 7ef80d6a438118da00d8afaf67cf9317cc50b953
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="obsolete-forms-of-function-declarations-and-definitions"></a>Formes obsolètes des déclarations et définitions de fonctions
En comparaison à la syntaxe recommandée par la norme C ANSI, les anciennes définitions et déclarations de fonction utilisent des règles légèrement différentes pour déclarer des paramètres. Premièrement, les anciennes déclarations n'ont pas de liste de paramètres. Ensuite, dans la définition de fonction, les paramètres sont répertoriés, mais leurs types ne sont pas déclarés dans la liste de paramètres. Les déclarations de type précèdent l'instruction composée constituant le corps de la fonction. L'ancienne syntaxe est obsolète et ne doit pas être utilisée dans le nouveau code. Le code utilisant l'ancienne syntaxe est cependant toujours pris en charge. Cet exemple montre les formes obsolètes des déclarations et des définitions :  
  
```  
double old_style();           /* Obsolete function declaration */  
  
double alt_style( a , real )  /* Obsolete function definition */  
    double *real;   
    int a;   
{  
    return ( *real + a ) ;  
}  
```  
  
 Les fonctions qui retournent un entier ou un pointeur de même taille qu'un `int` ne doivent pas impérativement contenir une déclaration, mais cette dernière est recommandée.  
  
 En conformité avec la norme C ANSI, les anciennes déclarations de fonction utilisant des points de suspension génèrent désormais une erreur lors de la compilation avec l'option /Za et un avertissement de niveau 4 lors de la compilation avec /Ze. Exemple :  
  
```  
void funct1( a, ... )  /* Generates a warning under /Ze or */  
int a;                 /* an error when compiling with /Za */  
{  
}  
```  
  
 Vous devez réécrire cette déclaration en tant que prototype :  
  
```  
void funct1( int a, ... )  
{  
}  
```  
  
 Les anciennes déclarations de fonction génèrent également des avertissements si vous déclarez ou définissez ensuite la même fonction avec des points de suspension ou avec un paramètre d'un type qui n'est pas identiques au type promu.  
  
 La section suivante, [Définitions de fonctions C](../c-language/c-function-definitions.md), explique la syntaxe des définitions de fonctions, y compris l'ancienne syntaxe. L'élément non terminal pour la liste de paramètres dans l'ancienne syntaxe est *identifier-list*.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble des fonctions](../c-language/overview-of-functions.md)