---
title: "Erreur irrécupérable RC1120 du compilateur de ressources | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- RC1120
dev_langs:
- C++
helpviewer_keywords:
- RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 28a35cc2f932cdf655324d05c10bdb875aa895a6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Erreur irrécupérable RC1120 du compilateur de ressources 
la mémoire, si nécessaire le nombre d’octets  
  
 Le compilateur de ressources a manqué d’espace pour les éléments qu’il stocke dans le segment de mémoire. Cela est généralement le résultat d’avoir trop de symboles.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Augmentez l’espace de fichier d’échange Windows. Pour plus d’informations sur l’augmentation de l’espace de fichier d’échange, consultez la mémoire virtuelle dans l’aide de Windows.  
  
2.  Éliminer inutiles les fichiers include, en particulier les `#define`fonction et les prototypes.  
  
3.  Fractionnez le fichier en cours en deux ou plusieurs fichiers et de les compiler séparément.  
  
4.  Supprimer d’autres programmes ou les pilotes en cours d’exécution dans le système, qui utilisent des quantités importantes de mémoire.