---
title: les Restrictions de fonction principale | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-language
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: ed5be2df6e152b26bcade1970b35ad33655e8e02
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="main-function-restrictions"></a>Restrictions relatives à la fonction main
Plusieurs restrictions s’appliquent à la **principal** fonction qui ne s’appliquent pas à d’autres fonctions C++. Le **principal** fonction :  
  
-   Ne peut pas être surchargé (voir [surcharge de fonction](function-overloading.md)).  
  
-   Ne peut pas être déclaré en tant que **inline**.  
  
-   Ne peut pas être déclaré en tant que **statique**.  
  
-   son adresse ne peut pas être prise.  
  
-   Ne peut pas être appelé.  
  
## <a name="see-also"></a>Voir aussi  
 [main : démarrage du programme](../cpp/main-program-startup.md)