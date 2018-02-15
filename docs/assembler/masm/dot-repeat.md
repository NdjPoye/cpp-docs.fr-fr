---
title: ". RÉPÉTEZ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .REPEAT
dev_langs:
- C++
helpviewer_keywords:
- .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: b5e2bee231ebbf1ec04e56a6cc3a2b2d8b03ecd2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="repeat"></a>.REPEAT
Génère du code qui répète l’exécution du bloc de *instructions* jusqu'à ce que `condition` prend la valeur true. [. UNTILCXZ](../../assembler/masm/dot-untilcxz.md), qui prend la valeur true lorsque CX est égal à zéro, peut être remplacé par [. Jusqu'à ce que](../../assembler/masm/dot-until.md). Le `condition` est facultatif avec **. UNTILCXZ**.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
   .REPEAT  
statements  
.UNTIL condition  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)