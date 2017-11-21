---
title: "retourner l’instruction (C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: return_cpp
dev_langs: C++
helpviewer_keywords:
- return keyword [C++], syntax
- return keyword [C++]
ms.assetid: a498903a-056a-4df0-a6cf-72f633a62210
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: db65a7762659bfc71f7ef33dc9f8b9b732fda091
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="return-statement-c"></a>return, instruction (C++)
Termine l'exécution d'une fonction et retourne le contrôle à la fonction d'appel (ou au système d'exploitation si vous transférez le contrôle à partir de la fonction `main`). L'exécution reprend dans la fonction d'appel au point immédiatement après l'appel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
return [expression];  
```  
  
## <a name="remarks"></a>Remarques  
 La clause `expression`, si elle est présente, est convertie dans le type spécifié dans la déclaration de fonction, comme si une initialisation était exécutée. La conversion du type de l'expression au type `return` de la fonction peut créer des objets temporaires. Pour plus d’informations sur comment et quand les objets temporaires sont créées, consultez [des objets temporaires](../cpp/temporary-objects.md).  
  
 La valeur de la clause `expression` est retournée à la fonction d'appel. Si l'expression est omise, la valeur de retour de la fonction n'est pas définie. Constructeurs et des destructeurs et des fonctions de type `void`, ne peut pas spécifier une expression dans la `return` instruction. Les fonctions de tous les autres types doivent spécifier une expression dans l'instruction `return`.  
  
 Lorsque l'ordre d'exécution quitte le bloc englobant la définition de fonction, le résultat est le même que si une instruction `return` sans expression avait été exécutée. Ceci n'est pas valable pour les fonctions déclarées comme retournant une valeur.  
  
 Une fonction peut comporter plusieurs instructions `return`.  
  
 L'exemple suivant utilise une expression avec une instruction `return` pour obtenir la plus grande valeur de deux entiers.  
  
## <a name="example"></a>Exemple  
  
```  
// return_statement2.cpp  
#include <stdio.h>  
  
int max ( int a, int b )  
{  
   return ( a > b ? a : b );  
}  
  
int main()  
{  
    int nOne = 5;  
    int nTwo = 7;  
  
    printf_s("\n%d is bigger\n", max( nOne, nTwo ));  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions de saut](../cpp/jump-statements-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)