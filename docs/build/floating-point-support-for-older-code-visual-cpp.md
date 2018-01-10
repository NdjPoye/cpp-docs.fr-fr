---
title: "Prise en charge à virgule flottante pour le Code plus ancien (Visual C++) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
ms.assetid: a2a26b96-7bc2-418a-981a-51aa1a0294a2
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 130b6efb1c05775cd7859144d91a30051fb4ca53
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="floating-point-support-for-older-code-visual-c"></a>Prise en charge de la virgule flottante pour le code plus ancien (Visual C++)
Les registres MMX et pile à virgule flottante (MM0-MM7/ST0-ST7) sont conservés entre les commutateurs de contexte.  Il n’existe aucune convention d’appel explicite pour ces registres.  L’utilisation de ces registres est strictement interdite dans le code en mode noyau.  
  
## <a name="see-also"></a>Voir aussi  
 [Convention d’appel](../build/calling-convention.md)