---
title: GOTO (MASM) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: c86a9b5bc83110f20dccf73f51b1e1aabc693db2
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="goto-masm"></a>GOTO (MASM)
Transfère un assembly à la ligne marquée **: *** macrolabel*.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
GOTO   
macrolabel  
  
```  
  
## <a name="remarks"></a>Notes  
 **GOTO** est autorisée uniquement à l’intérieur de [MACRO](../../assembler/masm/macro.md), [pour](../../assembler/masm/for-masm.md), [FORC](../../assembler/masm/forc.md), [RÉPÉTEZ](../../assembler/masm/repeat.md), et **lors de la**blocs. L’étiquette doit être la seule directive sur la ligne et doit être précédé d’un signe deux-points de début.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)