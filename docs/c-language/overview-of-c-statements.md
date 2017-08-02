---
title: "Vue d’ensemble des instructions C | Microsoft Docs"
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
- semicolon, in C statements
- statements, C
- semicolon
- statements, about statements
- Visual C, statements
ms.assetid: 0d49837a-5399-4881-b60c-af5f4e9720de
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
ms.openlocfilehash: 040cc7a1718975285088fb0d1a7474cc72a5c4d8
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="overview-of-c-statements"></a>Vue d'ensemble des instructions C
Les instructions C se composent de jetons, d'expressions et d'autres instructions. Une instruction qui forme un composant d'une autre instruction est qualifiée de « corps » de l'instruction englobante. Chaque type d'instruction donné par la syntaxe suivante est décrit dans cette section.  
  
## <a name="syntax"></a>Syntaxe  
 *instruction* :  
 [labeled-statement](../c-language/goto-and-labeled-statements-c.md)  
  
 [compound-statement](../c-language/compound-statement-c.md)  
  
 [expression-statement](../c-language/expression-statement-c.md)  
  
 [selection-statement](../c-language/if-statement-c.md)  
  
 [iteration-statement](../c-language/do-while-statement-c.md)  
  
 [jump-statement](../c-language/break-statement-c.md)  
  
 [try-except-statement](../c-language/try-except-statement-c.md)  
  
 /* Spécifique à Microsoft \*/[try-finally-statement](../c-language/try-finally-statement-c.md) /\* Spécifique à Microsoft \*/  
  
 Souvent, le corps de l'instruction est une « instruction composée ». Une instruction composée se compose d'autres instructions qui peuvent inclure des mots clés. L'instruction composée est délimitée par des accolades (**{ }**). Toutes les autres instructions C se terminent par un point-virgule (**;**). Le point-virgule est une marque de fin d'instruction.  
  
 Une instruction d'expression contient une expression C qui peut contenir les opérateurs arithmétiques ou logiques présentés dans [Expressions et assignations](../c-language/expressions-and-assignments.md). L'instruction null est une instruction vide.  
  
 Toute instruction C peut commencer par une étiquette d'identification composée d'un nom et d'un signe deux-points. Comme seule l'instruction `goto` identifie des étiquettes d'instruction, les étiquettes d'instruction sont présentées avec `goto`. Consultez [Instructions goto et étiquetées](../c-language/goto-and-labeled-statements-c.md) pour plus d'informations.  
  
## <a name="see-also"></a>Voir aussi  
 [Instructions](../c-language/statements-c.md)
