---
title: GOTO (MASM) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: goto
dev_langs: C++
helpviewer_keywords: GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 896d99b2ed4abe2080e646b6a541eb1e489d2b75
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="goto-masm"></a>GOTO (MASM)
Transfère un assembly à la ligne marquée **:***macrolabel*.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## <a name="remarks"></a>Remarques  
 **GOTO** est autorisée uniquement à l’intérieur de [MACRO](../../assembler/masm/macro.md), [pour](../../assembler/masm/for-masm.md), [FORC](../../assembler/masm/forc.md), [RÉPÉTEZ](../../assembler/masm/repeat.md), et **lors de la**blocs. L’étiquette doit être la seule directive sur la ligne et doit être précédé d’un signe deux-points de début.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)