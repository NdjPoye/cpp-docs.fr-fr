---
title: "M&#233;lange d&#39;exceptions C (structur&#233;es) et d&#39;exceptions C++ | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestion d'exceptions C++, à plusieurs langues"
  - "catch (mot clé) (C++), mixtes"
  - "exceptions, en C et C++"
  - "gestion structurée des exceptions, en C et C++"
  - "try-catch (mot clé) (C++), à plusieurs langues"
ms.assetid: a149154e-36dd-4d1a-980b-efde2a563a56
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# M&#233;lange d&#39;exceptions C (structur&#233;es) et d&#39;exceptions C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous voulez écrire du code plus portable, l'utilisation d'une gestion des exceptions structurées dans un programme C\+\+ n'est pas recommandée.  Toutefois, vous pouvez parfois souhaiter compiler avec **\/EHa** et associer des exceptions structurées et du code source C\+\+, et vous avez besoin d'une fonctionnalité pour gérer ces deux types d'exceptions.  Un gestionnaire d'exceptions structurées n'ayant aucun concept des objets ou des exceptions typées, il ne peut pas gérer les exceptions levées par du code C\+\+. Toutefois, les gestionnaires **catch** C\+\+ peuvent gérer les exceptions structurées.  Ainsi, la syntaxe de gestion des exceptions C\+\+ \(**try**, `throw`, **catch**\) n'est pas acceptée par le compilateur C, mais la syntaxe de gestion structurée des exceptions \(`__try`, `__except`, `__finally`\) est prise en charge par le compilateur C\+\+.  
  
 Consultez [\_set\_se\_translator](../c-runtime-library/reference/set-se-translator.md) pour plus d'informations sur la gestion des exceptions structurées en tant qu'exceptions C\+\+.  
  
 Si vous combinez des exceptions structurées et C\+\+, notez les éléments suivants :  
  
1.  Les exceptions C\+\+ et les exceptions structurées ne peuvent pas être mélangées dans la même fonction.  
  
2.  Les gestionnaires de terminaisons \(blocs `__finally`\) sont toujours exécutés, même pendant le déroulement après qu'une exception soit levée.  
  
3.  La gestion des exceptions C\+\+ peut intercepter et conserver les sémantiques de déroulement dans tous les modules compilés avec l'option du compilateur [\/EH](../build/reference/eh-exception-handling-model.md) \(cette option active les sémantiques de déroulement\).  
  
4.  Il peut exister des situations où les fonctions de destructeur ne sont pas appelées pour tous les objets.  Par exemple, si une exception structurée se produit lors d'une tentative d'appel de fonction via un pointeur fonction non initialisé, et si cette fonction prend comme paramètres des objets ayant été construits avant l'appel, ces objets n'auront pas leurs destructeurs appelés durant le déroulement de pile.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Utilisation de setjmp ou de longjmp dans les programmes C\+\+](../cpp/using-setjmp-longjmp.md)  
  
-   [Différences entre SEH et C\+\+ EH](../cpp/exception-handling-differences.md)  
  
## Voir aussi  
 [Gestion d'exceptions C\+\+](../cpp/cpp-exception-handling.md)