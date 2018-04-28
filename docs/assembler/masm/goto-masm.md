---
title: GOTO (MASM) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-masm
ms.topic: reference
f1_keywords:
- goto
dev_langs:
- C++
helpviewer_keywords:
- GOTO directive
ms.assetid: 6a5f73e7-6784-4eae-ac52-4fc77a7f369f
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: 9eecdab2fe91de0aae656b37c6fddafe658e60c0
ms.sourcegitcommit: dbca5fdd47249727df7dca77de5b20da57d0f544
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 04/28/2018
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