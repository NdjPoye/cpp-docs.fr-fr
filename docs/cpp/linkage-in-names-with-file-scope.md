---
title: "Liaison des noms avec portée de fichier | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
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
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 581d7798f4f3aaa409d843f8b7f3b5869b47407e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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