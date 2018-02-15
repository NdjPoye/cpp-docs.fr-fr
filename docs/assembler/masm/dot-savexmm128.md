---
title: .SAVEXMM128 | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .SAVEXMM128
dev_langs:
- C++
helpviewer_keywords:
- .SAVEXMM128 directive
ms.assetid: 551eb472-b8d0-47b1-8d82-995d1f485723
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 2e163f71b0c1d49f845cc871a26d4ee369843597
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="savexmm128"></a>.SAVEXMM128
Génère soit un `UWOP_SAVE_XMM128` ou un `UWOP_SAVE_XMM128_FAR` déroulement d’entrée du code pour le registre XMM spécifié et le décalage à l’aide de l’offset de prologue actuel. MASM choisira l’encodage le plus efficace.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.savexmm128 xmmreg , offset  
```  
  
## <a name="remarks"></a>Notes  
 . SAVEXMM128 permet aux utilisateurs de ml64.exe spécifier comment se déroule une fonction de frame et est uniquement autorisée dans le prologue, qui s’étend de la [PROC](../../assembler/masm/proc.md) la déclaration de FRAME le [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) la directive. Ces directives ne génèrent pas de code ; ils génèrent uniquement `.xdata` et `.pdata`. . SAVEXMM128 doit être précédé d’instructions qui mettent véritablement en œuvre les actions devant être déroulée. Il est recommandé d’encapsuler les directives de déroulement et le code qu’ils visent à déroulement dans une macro pour garantir l’accord.  
  
 `offset` doit être un multiple de 16.  
  
 Pour plus d’informations, consultez [MASM pour x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)