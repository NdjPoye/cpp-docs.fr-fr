---
title: Compilateur avertissement (niveaux 2 et 3) C4008 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: C4008
dev_langs: C++
helpviewer_keywords: C4008
ms.assetid: fb45e535-cb68-4743-80e9-a6e34cfffeca
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: da08cbd68cc1044ac62fbcdc20d3e5aa326c63ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Avertissement du compilateur (niveaux 2 et 3) C4008
'identifier' : 'attribute' attribut ignoré  
  
 Le compilateur a ignoré l’attribut `__fastcall`, **static**ou **inline** pour une fonction (avertissement de niveau 3) ou des données (avertissement de niveau 2).  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Attribut`__fastcall` avec des données.  
  
2.  Attribut**static** ou **inline** avec la fonction **main** .