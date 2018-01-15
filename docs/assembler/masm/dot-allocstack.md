---
title: . ALLOCSTACK | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .ALLOCSTACK
dev_langs: C++
helpviewer_keywords: .ALLOCSTACK directive
ms.assetid: 9801594b-7ac2-4df2-a49d-07d9dd9af99e
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 20d9147b2c1a95d4fc9600935111a9c0c013be21
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="allocstack"></a>.ALLOCSTACK
Génère un **UWOP_ALLOC_SMALL** ou un **UWOP_ALLOC_LARGE** avec la taille spécifiée pour l’offset actuel dans le prologue.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.ALLOCSTACK size  
```  
  
## <a name="remarks"></a>Notes  
 MASM choisira l’encodage le plus efficace pour une taille donnée.  
  
 . ALLOCSTACK permet aux utilisateurs de ml64.exe spécifier la façon dont une fonction de frame se déroule et est autorisée uniquement dans le prologue, qui s’étend de la [PROC](../../assembler/masm/proc.md) la déclaration de FRAME le [. ENDPROLOG](../../assembler/masm/dot-endprolog.md) la directive. Ces directives ne génèrent pas de code ; ils génèrent uniquement `.xdata` et `.pdata`. . ALLOCSTACK doit être précédé d’instructions qui mettent véritablement en œuvre les actions devant être déroulée. Il est recommandé d’encapsuler les directives de déroulement et le code qu’ils visent à déroulement dans une macro pour garantir l’accord.  
  
 Le `size` opérande doit être un multiple de 8.  
  
 Pour plus d’informations, consultez la rubrique [MASM pour x64 (ml64.exe)](../../assembler/masm/masm-for-x64-ml64-exe.md).  
  
## <a name="sample"></a>Exemple  
 L’exemple suivant montre comment spécifier un gestionnaire de déroulement ou d’exception :  
  
```  
; ml64 ex3.asm /link /entry:Example1  /SUBSYSTEM:Console  
text SEGMENT  
PUBLIC Example3  
PUBLIC Example3_UW  
Example3_UW PROC NEAR  
   ; exception/unwind handler body  
  
   ret 0  
  
Example3_UW ENDP  
  
Example3 PROC FRAME : Example3_UW  
  
   sub rsp, 16  
.allocstack 16  
  
.endprolog  
  
   ; function body  
    add rsp, 16  
   ret 0  
  
Example3 ENDP  
text ENDS  
END  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)