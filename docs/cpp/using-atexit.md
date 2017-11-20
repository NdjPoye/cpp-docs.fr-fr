---
title: "Utilisation d’atexit | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
f1_keywords: atexit
dev_langs: C++
helpviewer_keywords: atexit function
ms.assetid: d28fda17-c3d4-4af6-ba44-f44886bbb237
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 271dee456d47f9ef6286b4a9543583145f69bc41
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="using-atexit"></a>Utilisation d'atexit
Avec la [atexit](../c-runtime-library/reference/atexit.md) (fonction), vous pouvez spécifier une fonction de sortie de traitement qui s’exécute avant l’arrêt du programme. Aucun objet statique global initialisé avant l'appel à `atexit` n'est détruit avant l'exécution de la fonction de sortie de traitement.  
  
## <a name="see-also"></a>Voir aussi  
 [Considérations supplémentaires sur la terminaison](../cpp/additional-termination-considerations.md)