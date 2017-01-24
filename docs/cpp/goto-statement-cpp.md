---
title: "goto, instruction (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "goto_cpp"
  - "goto"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "goto (mot clé) (C++)"
ms.assetid: 724c5deb-2de1-42d8-8ef1-23589d9bf5ed
caps.latest.revision: 13
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# goto, instruction (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'instruction `goto` transfère sans condition le contrôle à l'instruction étiquetée par l'identificateur spécifié.  
  
## Syntaxe  
  
```  
goto identifier;  
```  
  
## Notes  
 L'instruction étiquetée indiquée par `identifier` doit se trouver dans la fonction actuelle.  Tous les noms `identifier` sont membres d'un espace de noms interne et, par conséquent, n'interfèrent pas avec d'autres identificateurs.  
  
 Une étiquette d'instruction est explicite uniquement pour une instruction `goto` ; sinon, les étiquettes d'instructions sont ignorées.  Les étiquettes ne peuvent pas être redéclarées.  
  
 Il est conseillé d'utiliser les instructions`break`, `continue` et `return` au lieu de l'instruction `goto` dès que possible.  Toutefois, comme l'instruction `break` ne termine qu'un seul niveau d'une boucle, vous devrez peut\-être utiliser une instruction `goto` pour quitter une boucle fortement imbriquée.  
  
 Pour plus d'informations sur les étiquettes et l'instruction `goto`, consultez [Instructions étiquetées](../cpp/labeled-statements.md) et [Utilisation d'étiquettes avec l'instruction goto](http://msdn.microsoft.com/fr-fr/6cd7c31a-9822-4241-8566-f79f51be48fe).  
  
## Exemple  
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
  
  **Exécution de la boucle externe.  i \= 0**  
 **Exécution de la boucle interne.  j \= 0**  
 **Exécution de la boucle interne.  j \= 1**  
**Exécution de la boucle externe.  i \= 1**  
 **Exécution de la boucle interne.  j \= 0**  
 **Exécution de la boucle interne.  j \= 1**  
**Exécution de la boucle externe.  i \= 2**  
 **Exécution de la boucle interne.  j \= 0**  
 **Exécution de la boucle interne.  j \= 1**  
**Exécution de la boucle externe.  i \= 3**  
 **Exécution de la boucle interne.  j \= 0**  
**Saut pour arrêter.  i \= 3**    
## Voir aussi  
 [Instructions de saut](../cpp/jump-statements-cpp.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)