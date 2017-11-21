---
title: . SAVEXMM128 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .SAVEXMM128
dev_langs: C++
helpviewer_keywords: .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4f79fc84e12f536383753d1d5982751cd30099d6
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="savexmm128"></a>.SAVEXMM128
Génère soit un `UWOP_SAVE_XMM128` ou un `UWOP_SAVE_XMM128_FAR` déroulement d’entrée du code pour le registre XMM spécifié et le décalage à l’aide de l’offset de prologue actuel. MASM choisira l’encodage le plus efficace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>Remarques  
 . SAVEXMM128 permet aux utilisateurs de ml64.exe spécifier comment se déroule une fonction de frame et est uniquement autorisée dans le prologue, qui s’étend de la [PROC](../../assembler/masm/proc.md) la déclaration de FRAME le [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) la directive. Ces directives ne génèrent pas de code ; ils génèrent uniquement `.xdata` et `.pdata`. . SAVEXMM128 doit être précédé d’instructions qui mettent véritablement en œuvre les actions devant être déroulée. Il est recommandé d’encapsuler les directives de déroulement et le code qu’ils visent à déroulement dans une macro pour garantir l’accord.  
  
 `offset`doit être un multiple de 16.  
  
 Pour plus d’informations, consultez [MASM pour x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)