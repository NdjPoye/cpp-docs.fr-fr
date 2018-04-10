---
title: Erreur irrécupérable C1054 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-tools
ms.tgt_pltfrm: ''
ms.topic: error-reference
f1_keywords:
- C1054
dev_langs:
- C++
helpviewer_keywords:
- C1054
ms.assetid: 9cfb7307-b22a-4418-b7c0-2621b0ab5b1b
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c39ba89a36791c56c0b71637cac388b28dc372f8
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="fatal-error-c1054"></a>Erreur irrécupérable C1054
limite du compilateur : initialiseurs imbriqués trop profondément  
  
 Le code dépasse la limite d’imbrication des initialiseurs (10-15 niveaux, selon la combinaison de types initialisés).  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Simplifiez les types de données en cours d’initialisation pour réduire l’imbrication.  
  
2.  Initialiser les variables dans des instructions distinctes après la déclaration.