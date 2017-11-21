---
title: Erreur BSCMAKE BK1509 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: BK1509
dev_langs: C++
helpviewer_keywords: BK1509
ms.assetid: 53df7037-1913-4b63-b425-c0bf44081792
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: f661152774c8d5313a294e243a0f5a0083b4e114
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="bscmake-error-bk1509"></a>Erreur BSCMAKE BK1509
espace du tas insuffisant  
  
 BSCMAKE n’a plus de mémoire, y compris la mémoire virtuelle.  
  
### <a name="to-fix-by-using-the-following-possible-solutions"></a>Pour résoudre ce problème, appliquez les solutions possibles suivantes.  
  
1.  Libérez de l’espace disque.  
  
2.  Augmentez la taille du fichier d’échange.  
  
3.  Augmentez la taille du fichier d’échange Windows.  
  
4.  Réduire la mémoire avec BSCMAKE, à l’aide de /Ei ou /Es à supprimer certains fichiers d’entrée ou /Em pour éliminer les corps de la macro.