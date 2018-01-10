---
title: "Erreur irrécupérable C1002 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C1002
dev_langs: C++
helpviewer_keywords: C1002
ms.assetid: bd6d274a-c7b4-43af-8bf2-23c5e442aa22
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: d299c6793e106ce516a81a9a81312ef0a09c25bf
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1002"></a>Erreur irrécupérable C1002
espace du tas insuffisant pour le compilateur lors de la deuxième passe  
  
 Le compilateur a manqué d’espace mémoire dynamique, la deuxième phase, probablement en raison d’un programme avec trop de symboles ou d’expressions complexes.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Fractionnez le fichier source en plusieurs fichiers plus petits.  
  
2.  Fractionnez les expressions en sous-expressions plus petites.  
  
3.  Supprimer d’autres programmes ou les pilotes qui consomment de la mémoire.