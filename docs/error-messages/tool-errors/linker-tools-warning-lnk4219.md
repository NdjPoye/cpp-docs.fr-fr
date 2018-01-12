---
title: "LNK4219 d’avertissement des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK4219
dev_langs: C++
helpviewer_keywords: LNK4219
ms.assetid: 363fedf4-b10c-4985-811a-55a9fba688d6
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 1331931ba2fa7219a27b8f60b185dc3ab9310328
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-warning-lnk4219"></a>Avertissement des outils Éditeur de liens LNK4219
dépassement de la correction nom correction. Cible 'nom de symbole cible' est hors limites, insertion du thunk  
  
 L’éditeur de liens a inséré un thunk dans une situation où l’adresse ou le décalage n’a pas pu être contenue dans l’instruction donnée parce que le symbole cible est trop loin à partir de l’emplacement de l’instruction.  
  
 Vous pouvez souhaiter réorganiser l’image (à l’aide de la [/Order](../../build/reference/order-put-functions-in-order.md) option, par exemple) pour éviter le niveau supplémentaire d’indirection.