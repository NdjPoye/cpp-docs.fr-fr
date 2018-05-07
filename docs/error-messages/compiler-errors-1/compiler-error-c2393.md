---
title: Erreur du compilateur C2393 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2393
dev_langs:
- C++
helpviewer_keywords:
- C2393
ms.assetid: 4bd95728-e813-4ce8-844a-c6ebe235ca82
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: efa8da496c6067381937820db365a5b37a19e843
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
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