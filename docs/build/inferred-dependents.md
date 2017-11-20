---
title: "Dépendants inférés | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- inferred dependents in NMAKE
- dependents, inferred
ms.assetid: 9303045c-69b3-4f35-bffc-19d5cd6ea3c3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: eaf75c067b2e96e5ae4a893b56376bfc1b9bd1e7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="inferred-dependents"></a>Dépendants inférés
Un dépendant déduit est dérivé d’une règle d’inférence et est évalué avant les dépendants explicites. Si un dépendant déduit est obsolète par rapport à sa cible, NMAKE appelle le bloc de commandes de la dépendance. Si un dépendant déduit n’existe pas ou est obsolète par rapport à ses propres dépendants, NMAKE met à jour le dépendant déduit en premier. Pour plus d’informations sur les dépendants inférés, consultez [les règles d’inférence](../build/inference-rules.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Dépendants](../build/dependents.md)