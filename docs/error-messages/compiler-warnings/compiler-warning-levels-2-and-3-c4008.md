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
ms.workload: cplusplus
ms.openlocfilehash: afd45078ac75ec9da8343baa2c203e75b324fb6e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-2-and-3-c4008"></a>Avertissement du compilateur (niveaux 2 et 3) C4008
'identifier' : 'attribute' attribut ignoré  
  
 Le compilateur a ignoré l’attribut `__fastcall`, **static**ou **inline** pour une fonction (avertissement de niveau 3) ou des données (avertissement de niveau 2).  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Attribut`__fastcall` avec des données.  
  
2.  Attribut**static** ou **inline** avec la fonction **main** .