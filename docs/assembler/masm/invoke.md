---
title: APPELER | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: Invoke
dev_langs: C++
helpviewer_keywords: INVOKE directive
ms.assetid: 12d9bb40-33b9-411e-b801-45a1d675967e
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: a4e17298c59a1c8620eb2261c44e5bd9c3aaceb0
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="invoke"></a>INVOKE
Appelle la procédure à l’adresse indiquée par *expression*, en passant les arguments sur la pile ou dans les registres selon les conventions d’appel standards du type de langage.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
INVOKE   
expression [[, arguments]]  
```  
  
## <a name="remarks"></a>Notes  
 Chaque argument passé à la procédure peut être une expression, une paire de registres ou une expression d’adresse (précédé d’une expression `ADDR`).  
  
## <a name="see-also"></a>Voir aussi  
 [Informations de référence sur les directives](../../assembler/masm/directives-reference.md)