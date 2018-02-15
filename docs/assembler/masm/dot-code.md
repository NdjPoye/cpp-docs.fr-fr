---
title: .CODE | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- .CODE
dev_langs:
- C++
helpviewer_keywords:
- .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: de0a9b8930c04929b05b02931a1f796d28a78099
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="code"></a>.CODE
Lorsqu’il est utilisé avec [. MODÈLE](../../assembler/masm/dot-model.md), indique le début d’un segment de code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
.CODE [[name]]  
```  
  
#### <a name="parameters"></a>Paramètres  
  
|Paramètre|Description|  
|---------------|-----------------|  
|`name`|Paramètre facultatif qui spécifie le nom du segment de code. Le nom par défaut est _TEXT pour minuscule, petite, compact et plat [modèles](../../assembler/masm/dot-model.md). Le nom par défaut est *modulename*_TEXT pour d’autres modèles.|  
  
## <a name="see-also"></a>Voir aussi  
 [Référence des directives](../../assembler/masm/directives-reference.md)   
 [.DATA](../../assembler/masm/dot-data.md)