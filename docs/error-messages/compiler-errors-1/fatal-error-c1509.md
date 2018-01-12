---
title: "Erreur irrécupérable C1509 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1509
dev_langs: C++
helpviewer_keywords: C1509
ms.assetid: 40dd100d-c6ba-451c-bd26-2c99ec1c36d6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 22cb22ea2186b16fd98d2714779b2475c51d15bc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1509"></a>Erreur irrécupérable C1509
limite du compilateur : trop d’états de gestionnaire d’exception dans la fonction 'fonction'. Simplifiez la fonction.  
  
 Le code dépasse une limite interne sur les États de gestionnaire d’exceptions (32 768 états).  
  
 La cause la plus courante est que la fonction contient une expression complexe de variables de la classe définie par l’utilisateur et d’opérateurs arithmétiques.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Simplifiez les expressions en assignant des sous-expressions communes à des variables temporaires.  
  
2.  Fractionnez la fonction en fonctions plus petites.