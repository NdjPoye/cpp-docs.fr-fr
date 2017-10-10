---
title: Erreur du compilateur C2439 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2439
dev_langs:
- C++
helpviewer_keywords:
- C2439
ms.assetid: 3c5dbe5c-b7d3-4bb0-8619-92f6e280461e
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 6aa5c0dcfd12be6979b0872f001bf0bf26a6e6e7
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="compiler-error-c2439"></a>Erreur du compilateur C2439
'identificateur' : membre n’a pas pu être initialisé.  
  
 Une classe, une structure ou un membre d’union ne peut pas être initialisé.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  La tentative d’initialiser une classe de base indirecte ou une structure.  
  
2.  Tentative d’initialisation d’un membre hérité d’une classe ou structure. Un membre hérité doit être initialisé par le constructeur de la classe ou structure.
