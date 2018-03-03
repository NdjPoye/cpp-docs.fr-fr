---
title: Erreur BSCMAKE BK1509 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- BK1509
dev_langs:
- C++
helpviewer_keywords:
- BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: e4d5fe0a83c5fbc3c4793699975d2045df5fbd8f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="bscmake-error-bk1509"></a>Erreur BSCMAKE BK1509
espace du tas insuffisant  
  
 BSCMAKE n’a plus de mémoire, y compris la mémoire virtuelle.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Libérez de l’espace disque.  
  
2.  Augmentez la taille du fichier d’échange.  
  
3.  Augmentez la taille du fichier d’échange Windows.  
  
4.  Réduire la mémoire avec BSCMAKE, à l’aide de /Ei ou /Es à supprimer certains fichiers d’entrée ou /Em pour éliminer les corps de la macro.