---
title: "Liaison des noms avec portée de classe | Documents Microsoft"
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
- scope [C++], linkage rules
- linkage [C++], scope linkage rules
- names [C++], scope linkage rules
- classes [C++], scope
- external linkage, scope linkage rules
- class names [C++], linkage
- classes [C++], names
- scope [C++], class names
- class scope [C++], linkage in names with
ms.assetid: 45275ff3-6e94-4967-82c8-ba540ef4da28
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
ms.translationtype: HT
ms.sourcegitcommit: 6ffef5f51e57cf36d5984bfc43d023abc8bc5c62
ms.openlocfilehash: 37a0dcca1da0ae56a8144adf862eda89bfb1c4d6
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="linkage-in-names-with-class-scope"></a>Liaison des noms avec la portée de classe
Les règles de liaison suivantes s'appliquent aux noms avec la portée de classe :  
  
-   Les membres de classe statique ont une liaison externe.  
  
-   Les fonctions membres de classe ont une liaison externe.  
  
-   Les noms d'énumérateur et les noms `typedef` n'ont aucune liaison.  
  
 **Section spécifique à Microsoft**  
  
-   Les fonctions déclarées comme fonctions `friend` doivent avoir une liaison externe. La déclaration d'une fonction statique comme `friend` génère une erreur.  
  
 **FIN de la section spécifique à Microsoft**  
  
## <a name="see-also"></a>Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)
