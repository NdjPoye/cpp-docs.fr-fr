---
title: "Liaison des noms avec portée de fichier | Documents Microsoft"
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
- static modifier, file scope
- static names and file scope
- file scope [C++]
- declarations [C++], external
- external linkage, scope linkage rules
- static variables, external declarations
ms.assetid: 38d3fa5e-1861-466e-a590-84b86f7b184e
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
ms.openlocfilehash: c4d33071426eac428cc1728aa13b403953a99389
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

---
# <a name="linkage-in-names-with-file-scope"></a>Liaison des noms avec la portée du fichier
Les règles suivantes de liaison s'appliquent aux noms (autres que les noms de `typedef` et les noms d'énumérateur) avec la portée de fichier :  
  
-   Si un nom est déclaré explicitement comme **statique**, il a une liaison interne et identifie un élément de programme à l’intérieur de sa propre unité de traduction.  
  
-   Les noms d'énumérateur et les noms de `typedef` n'ont aucune liaison.  
  
-   Tous les autres noms avec la portée de fichier ont une liaison externe.  
  
 **Section spécifique à Microsoft**  
  
-   Si un nom de fonction avec portée de fichier est déclaré explicitement comme **inline**, il a une liaison externe si elle est instanciée, ou son adresse est référencée. Par conséquent, une fonction avec la portée de fichier peut avoir une liaison interne ou externe.  
  
 **FIN de la section spécifique à Microsoft**  
  
 Une classe a une liaison interne si elle :  
  
-   N'utilise pas de fonctionnalité C++ (par exemple, contrôle d'accès de membre, fonctions membres, constructeurs, destructeurs, etc.).  
  
-   N'est pas utilisée dans la déclaration d'un autre nom qui a une liaison externe. Cette contrainte signifie que les objets d'un type classe qui sont passés aux fonctions avec une liaison externe attribuent une liaison externe à cette classe.  
  
## <a name="see-also"></a>Voir aussi  
 [Programme et liaison](../cpp/program-and-linkage-cpp.md)
