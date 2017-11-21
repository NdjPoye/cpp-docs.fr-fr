---
title: -LA PILE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: /stack
dev_langs: C++
helpviewer_keywords:
- -STACK editbin option
- STACK editbin option
- stack, setting size
- /STACK editbin option
ms.assetid: a39bcff0-c945-4355-80cc-8e4f24a5f142
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: ae6696123ffa016a1c3f64ed2310efe571b55978
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="stack"></a>/STACK
```  
/STACK:reserve[,commit]  
```  
  
## <a name="remarks"></a>Remarques  
 Cette option définit la taille de la pile en octets et accepte des arguments en notation décimale ou en langage C. L’option /STACK s’applique uniquement à un fichier exécutable.  
  
 Le *réserver* argument spécifie l’allocation de pile total dans la mémoire virtuelle. EDITBIN arrondit la valeur spécifiée aux plus proche de 4 octets.  
  
 Le paramètre facultatif `commit` argument est soumis à l’interprétation par le système d’exploitation. Dans Windows NT, Windows 95 et Windows 98, `commit` spécifie la quantité de mémoire physique à allouer à la fois. Mémoire virtuelle dédiée, espace à réserver dans le fichier d’échange. Un degré plus élevé `commit` valeur fait gagner du temps quand l’application requiert davantage d’espace de pile, mais augmente les besoins en mémoire et éventuellement les temps de démarrage.  
  
## <a name="see-also"></a>Voir aussi  
 [Options EDITBIN](../../build/reference/editbin-options.md)