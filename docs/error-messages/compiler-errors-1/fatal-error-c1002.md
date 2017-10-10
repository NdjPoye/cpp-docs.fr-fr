---
title: "Erreur irrécupérable C1002 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C1002
dev_langs:
- C++
helpviewer_keywords:
- C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: cab0e1db2d84fb5ba84d773f28e70341faf10ac6
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="fatal-error-c1002"></a>Erreur irrécupérable C1002
espace du tas insuffisant pour le compilateur lors de la deuxième passe  
  
 Le compilateur a manqué d’espace mémoire dynamique, la deuxième phase, probablement en raison d’un programme avec trop de symboles ou d’expressions complexes.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Fractionnez le fichier source en plusieurs fichiers plus petits.  
  
2.  Fractionnez les expressions en sous-expressions plus petites.  
  
3.  Supprimer d’autres programmes ou les pilotes qui consomment de la mémoire.
