---
title: "Vue d’ensemble de fonctions | Microsoft Docs"
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
- functions [C++]
- control flow, function calls
ms.assetid: b6f4637f-02b9-49d8-8601-1f886bd2cfb9
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
ms.openlocfilehash: 16612a32a0e5cb2294f4b74f46c14c206c1cbcbc
ms.contentlocale: fr-fr
ms.lasthandoff: 05/18/2017

---
# <a name="overview-of-functions"></a>Vue d'ensemble des fonctions
Les fonctions doivent avoir une définition et une déclaration, même si une définition peut servir de déclaration si celle-ci apparaît avant l'appel de la fonction. La définition de fonction comprend le corps de la fonction, c'est-à-dire le code qui s'exécute lorsque la fonction est appelée.  
  
 Une déclaration de fonction génère le nom, le type de retour et les attributs d'une fonction qui est définie ailleurs dans le programme. Une déclaration de fonction doit précéder l'appel à la fonction. C'est pourquoi les fichiers d'en-tête contenant les déclarations pour les fonctions runtime sont inclus dans votre code avant un appel à une fonction runtime. Si la déclaration comporte des informations sur les types et le nombre de paramètres, il s'agit d'un prototype. Pour plus d'informations, consultez [Prototypes de fonction](../c-language/function-prototypes.md).  
  
 Le compilateur utilise le prototype pour comparer les types d’argument dans les appels suivants à la fonction avec les paramètres de la fonction et convertir ces types d’argument en types de paramètre chaque fois que nécessaire.  
  
 Un appel de fonction transmet le contrôle d'exécution à la fonction appelée à partir de la fonction appelante. Les arguments, le cas échéant, sont transmis par valeur à la fonction appelée. L'exécution d'une instruction `return` dans la fonction appelée retourne le contrôle et éventuellement une valeur à la fonction appelante.  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../c-language/functions-c.md)
