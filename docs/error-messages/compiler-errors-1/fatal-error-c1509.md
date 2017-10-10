---
title: "Erreur irrécupérable C1509 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1509
dev_langs:
- C++
helpviewer_keywords:
- C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: 7
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 3d3fc7a7be867a7137dab4155984cf1844b661ea
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="fatal-error-c1509"></a>Erreur irrécupérable C1509
limite du compilateur : trop d’états de gestionnaire d’exception dans la fonction 'fonction'. Simplifiez la fonction.  
  
 Le code dépasse une limite interne sur les États de gestionnaire d’exceptions (32 768 états).  
  
 La cause la plus courante est que la fonction contient une expression complexe de variables de la classe définie par l’utilisateur et d’opérateurs arithmétiques.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Simplifiez les expressions en assignant des sous-expressions communes à des variables temporaires.  
  
2.  Fractionnez la fonction en fonctions plus petites.
