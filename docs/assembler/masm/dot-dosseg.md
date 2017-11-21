---
title: . DOSSEG | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .DOSSEG
dev_langs: C++
helpviewer_keywords: .DOSSEG directive
ms.assetid: 175ad470-0a2b-4e2b-b078-65e224fec040
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 4d2156161686583ba00d357c1dbca2e2e2867e9b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="dosseg"></a>.DOSSEG
Trie les segments en fonction de la convention de segment MS-DOS : CODE en premier lieu, puis les segments n’est pas dans DGROUP et puis segments dans DGROUP.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
.DOSSEG  
  
```  
  
## <a name="remarks"></a>Remarques  
 Les segments dans DGROUP suivent cet ordre : segments pas BSS ou de la pile, les segments BSS et segments de pile. Principalement utilisé pour assurer la prise en charge de CodeView dans les programmes autonomes MASM. Identique à [DOSSEG](../../assembler/masm/dosseg.md).  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)