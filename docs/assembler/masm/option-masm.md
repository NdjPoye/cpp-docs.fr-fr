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
ms.openlocfilehash: ab64740cd5f04b4a707a702f0bf39174907fc8fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="option-masm"></a>OPTION (MASM)
Active ou désactive les fonctionnalités de l’assembleur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
OPTION   
optionlist  
  
```  
  
## <a name="remarks"></a>Remarques  
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