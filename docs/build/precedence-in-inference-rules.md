---
title: "Priorité dans les règles d’inférence | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inference rules in NMAKE
- rules, inference
- precedence, inference rule
ms.assetid: 69e3dc02-0815-4c3a-b02b-1cb85fceaf24
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: d22db9de1fc1941798c73c3c1c05a8ccd8571525
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="precedence-in-inference-rules"></a>Priorité dans les règles d'inférence
Si une règle d’inférence est définie plusieurs fois, NMAKE utilise la définition de la priorité la plus élevée. La liste suivante indique l’ordre de priorité, du plus élevé au plus bas :  
  
1.  Une règle d’inférence définie dans un makefile ; définitions les plus récentes ont une priorité.  
  
2.  Une règle d’inférence définie dans Tools.ini ; définitions les plus récentes ont une priorité.  
  
3.  Règle d’inférence prédéfinie.  
  
## <a name="see-also"></a>Voir aussi  
 [Règles d’inférence](../build/inference-rules.md)