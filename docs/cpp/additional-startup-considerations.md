---
title: "Considérations sur le démarrage supplémentaires | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords:
- program startup [C++]
- startup code
- initializing before main
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 57b1de8fbbdb3d969dca8e84e57e18b81749d944
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="additional-startup-considerations"></a>Considérations supplémentaires sur le démarrage
En langage C++, la construction et la destruction d'objets peuvent impliquer l'exécution de code utilisateur. Par conséquent, il est important de comprendre quelles initialisations ont lieu avant l’entrée dans **principal** et les destructeurs sont appelés après la sortie de **principal**. (Pour plus d’informations sur la construction et la destruction d’objets, consultez [constructeurs](../cpp/constructors-cpp.md) et [destructeurs](../cpp/destructors-cpp.md).)  
  
 Les initialisations suivantes ont lieu avant l’entrée à **principal**:  
  
-   Mise à zéro par défaut des données statiques. Toutes les données statiques sans initialiseurs explicites sont mises à zéro avant d'exécuter tout autre code, y compris l'initialisation du runtime. Les données membres statiques doivent encore être définies explicitement.  
  
-   Initialisation des objets statiques globaux dans une unité de traduction. Cela peut se produire avant l’entrée dans **principal** ou avant la première utilisation d’une fonction ou un objet dans l’unité de traduction de l’objet.  
  
 **Section spécifique à Microsoft**  
  
 Dans Microsoft C++, les objets statiques globaux sont initialisés avant l’entrée dans **principal**.  
  
 **FIN de la section spécifique à Microsoft**  
  
 Des objets statiques globaux mutuellement interdépendants mais figurant dans des unités de traduction distinctes peuvent provoquer un comportement incorrect.  
  
## <a name="see-also"></a>Voir aussi  
 [Démarrage et arrêt](../cpp/startup-and-termination-cpp.md)