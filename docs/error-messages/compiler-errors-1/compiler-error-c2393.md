---
title: Erreur du compilateur C2393 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: fa9bc840894cf677e61c0247effcb875a2fdf2ff
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2393"></a>Erreur du compilateur C2393
'symbole' : symbole par appdomain ne peut pas être alloué dans le segment 'segment'  
  
 Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 L’utilisation de [appdomain](../../cpp/appdomain.md) variables implique que vous compilez avec **/CLR : pure** ou **/CLR : safe**, et une image safe ou pure ne peut pas contenir de segments de données.  
  
 Consultez [/clr (Compilation pour le Common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md) pour plus d’informations.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C2393.  
  
```  
// C2393.cpp  
// compile with: /clr:pure /c  
#pragma data_seg("myseg")  
int n = 0;   // C2393  
```