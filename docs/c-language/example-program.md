---
title: Exemple de programme | Microsoft Docs
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
ms.assetid: fc22ef82-9caa-425f-b201-2891bc123d1f
caps.latest.revision: 8
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
ms.openlocfilehash: a26a09da1a1653c71ce299be94556eba2236aefd
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="example-program"></a>Exemple de programme
Le programme source C suivant se compose de deux fichiers sources. Il fournit une présentation de certaines des déclarations et définitions possibles dans un C programme. Les sections suivantes de cette documentation décrivent comment écrire ces déclarations, définitions et initialisations, et comment utiliser des mots clés C tels que **static** et `extern`. La fonction `printf` est déclarée dans le fichier d'en-tête C STDIO.H.  
  
 Les fonctions `main` et `max` sont supposés être dans des fichiers distincts et l'exécution du programme commence par la fonction `main`. Aucune fonction utilisateur explicite n'est exécutée avant `main`.  
  
```  
/*****************************************************************  
                    FILE1.C - main function  
*****************************************************************/  
  
#define ONE     1  
#define TWO     2  
#define THREE   3  
#include <stdio.h>  
  
int a = 1;                       // Defining declarations      
int b = 2;                       //  of external variables      
  
extern int max( int a, int b );  // Function prototype          
  
int main()                       // Function definition         
{                                //  for main function          
    int c;                       // Definitions for      
    int d;                       //  two uninitialized  
                                 //  local variables  
  
    extern int u;                // Referencing declaration     
                                 //  of external variable       
                                 //  defined elsewhere          
    static int v;                // Definition of variable      
                                 //  with continuous lifetime   
  
    int w = ONE, x = TWO, y = THREE;  
    int z = 0;  
  
    z = max( x, y );             // Executable statements      
    w = max( z, w );  
    printf_s( "%d %d\n", z, w );  
    return 0;  
}  
  
/****************************************************************  
            FILE2.C - definition of max function  
****************************************************************/  
  
int max( int a, int b )          // Note formal parameters are     
                                 //  included in function header   
{  
    if( a > b )  
        return( a );  
    else  
        return( b );  
}  
```  
  
 FILE1.C contient le prototype de la fonction `max`. Ce genre de déclaration est parfois appelé « déclaration anticipée », car la fonction est déclarée avant d'être utilisée. La définition de la fonction `main` inclut des appels à `max`.  
  
 Les lignes commençant par `#define` sont des directives de préprocesseur. Ces directives indiquent au préprocesseur qu'il faut remplacer les identificateurs `ONE`, `TWO` et `THREE` par les nombres `1`, `2` et `3`, respectivement, dans FILE1.C. En revanche, les directives ne s'appliquent pas à FILE2.C, qui est compilé séparément puis lié à FILE1.C. La ligne commençant par `#include` indique au compilateur qu'il faut inclure le fichier STDIO.H, qui contient le prototype de la fonction `printf`. Les [Directives de préprocesseur](../preprocessor/preprocessor-directives.md) sont expliquées dans *Référence de préprocesseur*.  
  
 FILE1.C utilise des déclarations de définition pour initialiser les variables globales `a` et `b`. Les variables locales `c` et `d` sont déclarées mais pas initialisées. Le stockage est alloué pour toutes ces variables. Les variables statiques et externes, `u` et `v`, sont initialisées automatiquement à la valeur 0. Par conséquent, seuls `a`, `b`, `u` et `v` contiennent des valeurs significatives lorsqu'elles sont déclarées, car elles sont initialisées (explicitement ou implicitement). FILE2.C contient la définition de fonction pour `max`. Cette définition satisfait les appels à `max` dans FILE1.C.  
  
 La durée de vie et la visibilité des identificateurs sont traitées dans [Durée de vie, portée, visibilité et liaison](../c-language/lifetime-scope-visibility-and-linkage.md). Pour plus d'informations sur les fonctions, consultez [Fonctions](../c-language/functions-c.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Fichiers sources et programmes sources](../c-language/source-files-and-source-programs.md)