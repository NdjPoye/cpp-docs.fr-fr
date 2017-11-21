---
title: IF (MASM) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: if
dev_langs: C++
helpviewer_keywords: IF directive
ms.assetid: 82e43712-4f0c-4bf6-90ce-0663e81af707
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b6ddb2c9d9ec6e39a0147d513fb452685d8e7213
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="if-masm"></a>IF (MASM)
Accorde l’assembly de *ifstatements* si *expression1* a la valeur true (différente de zéro) ou *elseifstatements* si *expression1* a la valeur false (0) et *expression2* a la valeur true.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
   IF expression1  
ifstatements  
[[ELSEIF expression2  
   elseifstatements]]  
[[ELSE  
   elsestatements]]  
ENDIF  
```  
  
## <a name="remarks"></a>Remarques  
 Les directives suivantes peuvent être remplacés par [ELSEIF](../../assembler/masm/elseif-masm.md): **ELSEIFB**, **ELSEIFDEF**, **ELSEIFDIF**, **ELSEIFDIFI** , **ELSEIFE**, **ELSEIFIDN**, **ELSEIFIDNI**, **ELSEIFNB**, et **ELSEIFNDEF** . Si vous le souhaitez, assemble *qu’elsestatements* si l’expression précédente a la valeur false. Notez que les expressions sont évaluées au moment de l’assembly.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)