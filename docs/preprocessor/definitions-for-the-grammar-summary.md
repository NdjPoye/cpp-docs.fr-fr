---
title: "Les définitions pour la synthèse de la grammaire | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- preprocessor, definitions
- preprocessor
ms.assetid: cc752dc8-6f4e-4347-a556-e0d9ef4c46bd
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 755533d59b9b893da4a657db6da2ea80f13138b5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="definitions-for-the-grammar-summary"></a>Résumé des définitions de grammaire
Les terminaux sont des points de terminaison dans une définition de syntaxe. Aucune autre résolution n'est possible. Les terminaux incluent l'ensemble des mots réservés et des identificateurs définis par l'utilisateur.  
  
Les éléments non terminaux sont des espaces réservés dans la syntaxe. La plupart de ces éléments sont définis ailleurs dans ce résumé de syntaxe. Les définitions peuvent être récursives. Les éléments non terminaux suivants sont définis dans le [Conventions lexicales](../cpp/lexical-conventions.md) section de la *référence du langage C++*:  
  
`constant`, *constant-expression*, *identifier*, *keyword*, `operator`, `punctuator`  
  
Un composant facultatif est indiqué par l'élément opt indicé. Par exemple, le code suivant indique une expression facultative entre accolades :  
  
**{** *expression*opt **}**  
  
## <a name="see-also"></a>Voir aussi  
[Résumé de la grammaire (C/C++)](../preprocessor/grammar-summary-c-cpp.md)