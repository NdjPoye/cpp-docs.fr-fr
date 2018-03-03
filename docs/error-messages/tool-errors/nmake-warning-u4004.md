---
title: Avertissement NMAKE U4004 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- U4004
dev_langs:
- C++
helpviewer_keywords:
- U4004
ms.assetid: 5086bbcb-42d7-4677-a877-1a02202a86a2
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fcbda9dd9d7ca5ecb99e46b9916fb95c2c560e49
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="nmake-warning-u4004"></a>Avertissement NMAKE U4004
règles trop nombreuses pour la cible 'targetname'  
  
 Plusieurs blocs de description a été spécifiée pour la cible de donnée unique comprenant les signes deux-points (**:**) comme séparateurs. NMAKE exécuté les commandes dans le premier bloc de description et ignoré les blocs.  
  
 Pour spécifier la même cible dans plusieurs dépendances, utilisez des signes deux-points doubles (`::`) comme séparateur dans chaque ligne de dépendance.