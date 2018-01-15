---
title: OPTION (MASM) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: option
dev_langs: C++
helpviewer_keywords: OPTION directive
ms.assetid: 8e10dabd-e36f-4586-ab01-ada96736b0bd
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f449606b143bfbf188e878b261f3d35017846862
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="option-masm"></a>OPTION (MASM)
Active ou désactive les fonctionnalités de l’assembleur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>Notes  
 Les options disponibles sont les suivantes :  
  
|||||  
|-|-|-|-|  
|**CASEMAP**|**DOTNAME**|**NODOTNAME**|**ÉMULATEUR**|  
|**NOEMULATOR**|**ÉPILOGUE**|**EXPR16**|**EXPR32**|  
|**LANGAGE**|**LJMP**|**NOLJMP**|**M510**|  
|**NOM510**|**NOKEYWORD**|**NOSIGNEXTEND**|**DÉCALAGE**|  
|**OLDMACROS**|**NOOLDMACROS**|**OLDSTRUCTS**|**NOOLDSTRUCTS**|  
|**PROC**|**PROLOGUE**|**EN LECTURE SEULE**|**NOREADONLY**|  
|**UNE ÉTENDUE**|**NOSCOPED**|**SEGMENT**|**SETIF2**.|  
  
 La syntaxe de langage est **OPTION de langage :***x*, où *x* est un des C, SYSCALL, STDCALL, PASCAL, FORTRAN ou BASIC.  SYSCALL, PASCAL, FORTRAN et BASIC ne sont pas pris en charge avec utilisé avec [. MODÈLE](../../assembler/masm/dot-model.md) plat.  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)