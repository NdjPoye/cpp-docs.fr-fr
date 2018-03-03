---
title: les Restrictions de fonction principale | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords:
- Main
dev_langs:
- C++
helpviewer_keywords:
- main function, restrictions on using
ms.assetid: 7b3df731-344b-44a8-850c-11cbcbfbfa83
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 8a94844a0d5636c58a764114ed6f413923d69950
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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