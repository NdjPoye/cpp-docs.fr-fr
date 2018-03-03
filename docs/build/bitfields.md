---
title: Champs de bits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- bitfields
ms.assetid: e9a1010d-1e1b-487f-9943-3c574e08f544
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 231d84e5d99cd9e6c1238ae12c143636f62ce80d
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="bitfields"></a>Champs de bits
Structure les champs de bits sont limités à 64 bits et peut être de type signé int, int non signé, int64 ou unsigned int64. Les champs de bits qui dépassent la limite de type ignorent les bits pour aligner le champ de bits de l’alignement du type suivant. Par exemple, les champs de bits entier ne peuvent pas dépasser une limite de 32 bits.  
  
## <a name="see-also"></a>Voir aussi  
 [Types et stockage](../build/types-and-storage.md)