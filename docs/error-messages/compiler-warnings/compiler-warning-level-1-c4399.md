---
title: Compilateur avertissement (niveau 1) C4399 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4399
dev_langs:
- C++
helpviewer_keywords:
- C4399
ms.assetid: f58d9ba7-71a0-4c3b-b26f-f946dda8af30
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: eff01c29d423b0823b41bf63702cf42ee839a523
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4399"></a>Avertissement du compilateur (niveau 1) C4399
'symbole' : symbole par processus ne doit pas être marqué avec __declspec (dllimport) lors de la compilation avec/clr : pure  
  
 Le **/CLR : pure** option du compilateur est déconseillée dans Visual Studio 2015.  
  
 Données à partir d’une image native ou une image avec des constructions natives et CLR ne peuvent pas être importées dans une image pure. Pour résoudre cet avertissement, compilez avec **/CLR** (pas **/CLR : pure**) ou supprimer `__declspec(dllimport)`.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C4399.  
  
```  
// C4399.cpp  
// compile with: /clr:pure /doc /W1 /c  
__declspec(dllimport) __declspec(process) extern const int i;   // C4399  
```