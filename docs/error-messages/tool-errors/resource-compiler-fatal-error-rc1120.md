---
title: "Erreur irrécupérable RC1120 du compilateur de ressources | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: RC1120
dev_langs: C++
helpviewer_keywords: RC1120
ms.assetid: 4e462931-e42e-42e3-8bfc-847677194286
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 9cc1006dad4b0427a4254f4798b206d975e89e03
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="resource-compiler-fatal-error-rc1120"></a>Erreur irrécupérable RC1120 du compilateur de ressources 
la mémoire, si nécessaire le nombre d’octets  
  
 Le compilateur de ressources a manqué d’espace pour les éléments qu’il stocke dans le segment de mémoire. Cela est généralement le résultat d’avoir trop de symboles.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Augmentez l’espace de fichier d’échange Windows. Pour plus d’informations sur l’augmentation de l’espace de fichier d’échange, consultez la mémoire virtuelle dans l’aide de Windows.  
  
2.  Éliminer inutiles les fichiers include, en particulier les `#define`fonction et les prototypes.  
  
3.  Fractionnez le fichier en cours en deux ou plusieurs fichiers et de les compiler séparément.  
  
4.  Supprimer d’autres programmes ou les pilotes en cours d’exécution dans le système, qui utilisent des quantités importantes de mémoire.