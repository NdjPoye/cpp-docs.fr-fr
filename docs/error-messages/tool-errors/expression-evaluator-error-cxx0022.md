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
ms.openlocfilehash: 7ce3565258d7aa79a308cadcffaa2ef3d2626944
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="expression-evaluator-error-cxx0022"></a>Évaluateur d'expression, erreur CXX0022
appel de fonction avant _main  
  
 L’évaluateur d’expression C ne peut pas évaluer une fonction avant que le débogueur est passé à la fonction **_main**. Le programme n’est pas initialisé correctement tant que **_main** a été appelée.  
  
 Cette erreur est identique à CAN0022.