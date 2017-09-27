---
title: "Vue d’ensemble de Translation de fichier | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs:
- C++
helpviewer_keywords:
- file translation [C++], about file translation
- translation [C++]
- translation phases
- files [C++], translation
- programs [C++], lexical conventions of
- preprocessing translation phase
ms.assetid: 5036c7b7-ccff-4e2c-b052-a9ea6c71af87
caps.latest.revision: 6
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 188574c43ca3650599fae58c0da1306ab49b5007
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="overview-of-file-translation"></a>Vue d'ensemble de la traduction de fichier
Les programmes C++, comme les programmes C, se composent d'un ou plusieurs fichiers. Chacun de ces fichiers est traduit dans l'ordre conceptuel suivant (l'ordre réel suit la règle « comme si » : la traduction doit avoir lieu comme si les étapes ci-dessous avaient été suivies) :  
  
1.  Génération de jetons lexicaux. Le mappage de caractère et le traitement de trigraphe, la ligne épissant et la génération de jetons sont exécutés dans cette phase de traduction.  
  
2.  Prétraitement. Cette phase de traduction apporte les fichiers sources auxiliaires référencés par `#include` directives, gère les « chaîne » et « charizing » les directives et effectue l’expansion de macro et de collage de jeton (consultez [Directives de préprocesseur](../preprocessor/preprocessor-directives.md) dans le *référence du préprocesseur* pour plus d’informations). Le résultat de la phase de prétraitement est une séquence de jetons qui, une fois combinés, définissent une unité de traduction.  
  
     Directives de préprocesseur commencent toujours par le signe dièse (**#**) caractère (autrement dit, le premier caractère d’un espace blanc sur la ligne doit être un signe dièse). Une seule directive de préprocesseur peut apparaître sur une ligne donnée. Exemple :  
  
    ```  
    #include <iostream>  // Include text of iostream in   
                         //  translation unit.  
    #define NDEBUG       // Define NDEBUG (NDEBUG contains empty   
                         //  text string).  
    ```  
  
3.  Génération de code. Cette phase de traduction utilise les jetons générés dans la phase de prétraitement pour générer le code objet.  
  
     Pendant cette phase, l'activation syntaxique et sémantique du code source est exécutée.  
  
 Consultez [Phases de traduction](../preprocessor/phases-of-translation.md) dans les *référence du préprocesseur* pour plus d’informations.  
  
 Le préprocesseur C++ est un sur-ensemble strict du préprocesseur ANSI C, mais le préprocesseur C++ diffère dans certaines instances. La liste suivante décrit plusieurs différences entre le préprocesseur ANSI C et le préprocesseurs C++ :  
  
-   Les commentaires sur une seule ligne sont pris en charge. Consultez [commentaires](../cpp/comments-cpp.md) pour plus d’informations.  
  
-   Une macro prédéfinie, **__cplusplus**, est défini uniquement pour C++. Consultez [Macros prédéfinies](../preprocessor/predefined-macros.md) dans les *référence du préprocesseur* pour plus d’informations.  
  
-   Le préprocesseur C ne reconnaît pas les opérateurs C++ : **.\* **, ** -> \* **, et `::`. Consultez [opérateurs](../cpp/cpp-built-in-operators-precedence-and-associativity.md) et [Expressions](../cpp/expressions-cpp.md), pour plus d’informations sur les opérateurs.  
  
## <a name="see-also"></a>Voir aussi  
 [Conventions lexicales](../cpp/lexical-conventions.md)
