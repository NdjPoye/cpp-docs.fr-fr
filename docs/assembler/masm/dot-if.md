---
title: . IF | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .IF
dev_langs: C++
helpviewer_keywords: .IF directive
ms.assetid: dccc7615-8fc7-4829-9f39-0ee405f6c1e3
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 2416b73fa42f9cac629644ea624a9545f3988dc3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="if"></a>.IF
Génère du code qui teste `condition1` (par exemple, AX 7 >) et exécute la *instructions* si cette condition est vraie.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
   .IF condition1   
statements  
[[.ELSEIF condition2   
   statements]]  
[[.ELSE  
   statements]]  
.ENDIF  
```  
  
## <a name="remarks"></a>Remarques  
 Si un [. AUTRE](../../assembler/masm/dot-else.md) suit, ses instructions est exécutées si la condition d’origine a la valeur false. Notez que les conditions sont évaluées au moment de l’exécution.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)