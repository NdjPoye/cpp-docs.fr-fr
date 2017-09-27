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
ms.openlocfilehash: 10fe82b0bb7ad700164b05ba466854db7716ba76
ms.contentlocale: fr-fr
ms.lasthandoff: 09/25/2017

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
