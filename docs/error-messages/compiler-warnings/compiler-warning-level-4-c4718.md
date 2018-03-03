---
title: Compilateur avertissement (niveau 4) C4718 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- C4718
dev_langs:
- C++
helpviewer_keywords:
- C4718
ms.assetid: 29507f8a-b024-42c1-a3b8-f35d1f2641f3
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 214c481f4ad77a7a67190cd7427e0cd5775ccc8c
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-4-c4718"></a>Avertissement du compilateur (niveau 4) C4718
'function call' : un appel récurrent n’a pas d’effets secondaires, suppression  
  
 Une fonction contient un appel récurrent, mais n’a pas d’effets secondaires. Un appel à cette fonction est en cours de suppression. L’exactitude du programme n’est pas affectée ; par contre, son comportement l’est. Si le fait de laisser l’appel peut provoquer une exception de dépassement de capacité de la pile d’exécution, la suppression de l’appel élimine ce risque.