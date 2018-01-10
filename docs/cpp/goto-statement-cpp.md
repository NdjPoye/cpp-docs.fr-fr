---
title: GoTo, instruction (C++) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: goto_cpp
dev_langs: C++
helpviewer_keywords: goto keyword [C++]
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: "13"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a002071bdb4e271df525b138647b0544cfe9f3c0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="goto-statement-c"></a>goto, instruction (C++)
L'instruction `goto` transfère sans condition le contrôle à l'instruction étiquetée par l'identificateur spécifié.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
goto identifier;  
```  
  
## <a name="remarks"></a>Notes  
 L'instruction étiquetée indiquée par `identifier` doit se trouver dans la fonction actuelle. Tous les noms `identifier` sont membres d'un espace de noms interne et, par conséquent, n'interfèrent pas avec d'autres identificateurs.  
  
 Une étiquette d'instruction est explicite uniquement pour une instruction `goto` ; sinon, les étiquettes d'instructions sont ignorées. Les étiquettes ne peuvent pas être redéclarées.  
  
 Il est conseillé d'utiliser les instructions`break`, `continue` et `return` au lieu de l'instruction `goto` dès que possible. Toutefois, comme l'instruction `break` ne termine qu'un seul niveau d'une boucle, vous devrez peut-être utiliser une instruction `goto` pour quitter une boucle fortement imbriquée.  
  
 Pour plus d’informations sur les étiquettes et les `goto` instruction, consultez [instructions étiquetées](../cpp/labeled-statements.md) et [à l’aide d’étiquettes avec l’instruction goto](http://msdn.microsoft.com/en-us/6cd7c31a-9822-4241-8566-f79f51be48fe).  
  
## <a name="example"></a>Exemple  
 Dans cet exemple, une instruction `goto` transfère le contrôle au point étiqueté `stop` quand `i` est égal à 3.  
  
```  
// goto_statement.cpp  
#include <stdio.h>  
int main()  
{  
    int i, j;  
  
    for ( i = 0; i < 10; i++ )  
    {  
        printf_s( "Outer loop executing. i = %d\n", i );  
        for ( j = 0; j < 2; j++ )  
        {  
            printf_s( " Inner loop executing. j = %d\n", j );  
            if ( i == 3 )  
                goto stop;  
        }  
    }  
  
    // This message does not print:   
    printf_s( "Loop exited. i = %d\n", i );  
  
    stop:   
    printf_s( "Jumped to stop. i = %d\n", i );  
}  
```  
  
```Output  
Outer loop executing. i = 0  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 1  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 2  
 Inner loop executing. j = 0  
 Inner loop executing. j = 1  
Outer loop executing. i = 3  
 Inner loop executing. j = 0  
Jumped to stop. i = 3  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions de saut](../cpp/jump-statements-cpp.md)   
 [Mots clés](../cpp/keywords-cpp.md)