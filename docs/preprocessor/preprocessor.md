---
title: Préprocesseur | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-tools
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor
ms.assetid: e120eda3-b413-49f1-a07c-e9fb128cf500
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 3bb5a9740bab3f69ff66a51cd58e6e1378e178f0
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/07/2018
---
# <a name="preprocessor"></a>Préprocesseur
Le préprocesseur est un processeur de texte qui manipule le texte d'un fichier source dans le cadre de la première phase de traduction. Le préprocesseur n'analyse pas le texte source, mais il le divise en jetons en vue de localiser les appels de macros. Bien que le compilateur appelle normalement le préprocesseur lors de sa première passe, le préprocesseur peut également être appelé séparément pour traiter du texte sans compilation.  
  
 La documentation de référence sur le préprocesseur comprend les sections suivantes :  
  
-   [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)  
  
-   [Opérateurs de préprocesseur](../preprocessor/preprocessor-operators.md)  
  
-   [Macros prédéfinies](../preprocessor/predefined-macros.md)  
  
-   [Pragmas](../preprocessor/pragma-directives-and-the-pragma-keyword.md)  
  
 **Section spécifique à Microsoft**  
  
 Vous pouvez obtenir une liste de votre code source après le prétraitement à l’aide de la [/E](../build/reference/e-preprocess-to-stdout.md) ou [/EP](../build/reference/ep-preprocess-to-stdout-without-hash-line-directives.md) option du compilateur. Les deux options appellent le préprocesseur et génèrent le texte résultant sur le périphérique de sortie standard qui, dans la plupart des cas, est la console. La différence entre ces deux options est que /E inclut les directives `#line`, tandis que /EP les supprime.  
  
 **FIN de la section spécifique à Microsoft**  
  
##  <a name="_predir_special_terminology"></a> Terminologie spéciale  
 Dans la documentation du préprocesseur, le terme « argument » fait référence à l’entité passée à une fonction. Dans certains cas, il est modifié par l'adjectif « réel » ou « formel », qui décrit respectivement l'expression d'argument spécifiée dans l'appel de fonction et la déclaration d'argument spécifiée dans la définition de fonction.  
  
 Le terme « variable » fait référence à un objet de données simple de type C. Le terme « objet » fait référence aux objets et aux variables C++ ; il s'agit d'un terme inclusif.  
  
## <a name="see-also"></a>Voir aussi  
 [Référence du préprocesseur C/C++](../preprocessor/c-cpp-preprocessor-reference.md)   
 [Phases de traduction](../preprocessor/phases-of-translation.md)