---
title: "Évaluateur d’expression, erreur CXX0022 | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: CXX0022
dev_langs: C++
helpviewer_keywords:
- CXX0022
- CAN0022
ms.assetid: f6b299ac-a4ee-492c-bd9f-6fff005bc537
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 3ba715176ef5e1d7cece8c53adbf4c3d2daad628
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="expression-evaluator-error-cxx0022"></a>Évaluateur d'expression, erreur CXX0022
appel de fonction avant _main  
  
 L’évaluateur d’expression C ne peut pas évaluer une fonction avant que le débogueur est passé à la fonction **_main**. Le programme n’est pas initialisé correctement tant que **_main** a été appelée.  
  
 Cette erreur est identique à CAN0022.