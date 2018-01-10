---
title: . CODE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: .CODE
dev_langs: C++
helpviewer_keywords: .CODE directive
ms.assetid: 2b8c882c-c0d2-4fa3-8335-e6b12717a4f4
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 150b5a0c26be3c3c4d0412157179ebfcbec128e7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
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