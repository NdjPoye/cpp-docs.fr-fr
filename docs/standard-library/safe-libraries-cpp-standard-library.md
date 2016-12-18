---
title: "Biblioth&#232;ques s&#233;curis&#233;es&#160;: biblioth&#232;que C++ standard | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "_SCL_SECURE_NO_DEPRECATE"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "bibliothèques sécurisées"
  - "bibliothèques sécurisées : bibliothèque C++ standard"
  - "bibliothèque C++ standard sécurisée"
ms.assetid: 3993340f-1f29-4d81-b3f5-52a52bc8e148
caps.latest.revision: 10
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Biblioth&#232;ques s&#233;curis&#233;es&#160;: biblioth&#232;que C++ standard
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Plusieurs améliorations ont été apportées aux bibliothèques fournies avec Visual C\+\+, notamment la bibliothèque C\+\+ standard, pour les rendre mieux sécurisées.  
  
 Plusieurs méthodes de la bibliothèque C\+\+ standard ont été identifiés comme potentiellement dangereuses, car elles peuvent entraîner un dépassement de mémoire tampon ou d’autre défauts dans le code. L’utilisation de ces méthodes est déconseillée : de nouvelles méthodes plus sécurisées des méthodes ont été créées pour les remplacer. Ces nouvelles méthodes se trouvent toutes dans `_s`.  
  
 Plusieurs améliorations ont également été apportées pour renforcer la sécurité des itérateurs et des algorithmes. Pour plus d’informations, consultez [Itérateurs vérifiés](../standard-library/checked-iterators.md), [Itérateurs de débogage, prise en charge](../standard-library/debug-iterator-support.md) et [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md).  
  
## Notes  
 Le tableau suivant répertorie les méthodes de la bibliothèque C\+\+ standard qui sont potentiellement dangereuses, ainsi que leur équivalent plus sécurisé :  
  
|Méthode potentiellement dangereuse|Équivalent plus sécurisé|  
|----------------------------------------|------------------------------|  
|[basic\_string::copy](../Topic/basic_string::copy.md)|[basic\_string::\_Copy\_s](../Topic/basic_string::_Copy_s.md)|  
|[char\_traits::copy](../Topic/char_traits::copy.md)|[char\_traits::\_Copy\_s](../Topic/char_traits::_Copy_s.md)|  
  
 Si vous appelez une des méthodes potentiellement dangereuses ci\-dessus, ou si vous utilisez incorrectement des itérateurs, le compilateur génère [Avertissement du compilateur \(niveau 3\) C4996](../error-messages/compiler-warnings/compiler-warning-level-3-c4996.md). Pour plus d’informations sur la désactivation de ces avertissements, consultez [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md).  
  
## Dans cette section  
 [\_ITERATOR\_DEBUG\_LEVEL](../standard-library/iterator-debug-level.md)  
  
 [\_SCL\_SECURE\_NO\_WARNINGS](../standard-library/scl-secure-no-warnings.md)  
  
 [Itérateurs vérifiés](../standard-library/checked-iterators.md)  
  
 [Itérateurs de débogage, prise en charge](../standard-library/debug-iterator-support.md)  
  
## Voir aussi  
 [Vue d'ensemble de la bibliothèque STL](../standard-library/cpp-standard-library-overview.md)