---
title: "Évaluateur d’expression, erreur CXX0019 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0019
dev_langs: C++
helpviewer_keywords:
- CXX0019
- CAN0019
ms.assetid: 4c6431fd-3310-4a61-934d-58b070b330fe
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: c62391bb770a49810a87c52b2f75d5a0d4426fbd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0019"></a>Évaluateur d'expression, erreur CXX0019
cast de type incorrect  
  
 L’évaluateur d’expression C ne peut pas effectuer la conversion lors de l’écriture du type.  
  
 Cette erreur est identique à CAN0019.  
  
### <a name="to-fix-by-checking-the-following-possible-causes"></a>Pour corriger en vérifiant les causes possibles suivantes  
  
1.  Le type spécifié est inconnu.  
  
2.  Trop de niveaux de types pointeur a été effectuée. Par exemple, la conversion de type  
  
    ```  
    (char **)h_message  
    ```  
  
     ne peut pas être évaluée par l’évaluateur d’expression C.