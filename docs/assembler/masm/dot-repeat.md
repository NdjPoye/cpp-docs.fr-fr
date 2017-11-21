---
title: ". RÉPÉTEZ | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .REPEAT
dev_langs: C++
helpviewer_keywords: .REPEAT directive
ms.assetid: cb8ad8c6-587b-42f9-a0ad-b5316a24918c
caps.latest.revision: "6"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: e60ae387ec619a0109b322902a4ad40c9ad73f1e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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