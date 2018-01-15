---
title: MxCsr | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: 4f3c229d-0862-4733-acc7-9ed7a0b870ce
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 7794cea8906440c0adca94791d08e3ced6af747e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="mxcsr"></a>MxCsr
L’état du Registre inclut également MxCsr. La convention d’appel divise ce Registre en une partie volatile et une partie non volatile. La partie volatile se compose des indicateurs de 6 état, MXCSR [0:5], alors que le reste du Registre, MXCSR [6:15], est considéré comme non volatile.  
  
 La partie non volatile est définie sur les valeurs standard suivantes au début de l’exécution du programme :  
  
```  
MXCSR[6]         : Denormals are zeros - 0  
MXCSR[7:12]      : Exception masks all 1's (all exceptions masked)  
MXCSR[13:14]   : Rounding  control - 0 (round to nearest)  
MXCSR[15]      : Flush to zero for masked underflow - 0 (off)  
```  
  
 Un appelant qui modifie l’un des champs non volatils dans MXCSR doit les restaurer avant de retourner à son appelant. En outre, un appelant qui a modifié l’un de ces champs doive restaurer leurs valeurs standard avant d’appeler un appelant, sauf si le contrat de l’appelé attend les valeurs modifiées.  
  
 Il existe deux exceptions aux règles relatives à la volatilité-non des indicateurs de contrôle :  
  
-   Dans les fonctions où documentée de la fonction donnée vise à modifier le MxCsr non volatile indicateurs.  
  
-   Lorsqu’il est prouvée corriger que les résultats de la violation de ces règles dans un programme qui se comporte ou a la même en tant que programme où ces règles ne sont pas violées, par exemple, via l’analyse de la totalité du programme.  
  
 Aucune hypothèse ne peut être effectuées sur l’état de la partie volatile de MXCSR au-delà des limites d’une fonction, sauf spécification contraire dans la documentation d’une fonction.  
  
## <a name="see-also"></a>Voir aussi  
 [Convention d’appel](../build/calling-convention.md)