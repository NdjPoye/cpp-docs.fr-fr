---
title: Erreur du compilateur C3389 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3389
dev_langs:
- C++
helpviewer_keywords:
- C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: bd88753553d2bad1cb9253cfe709e7627c4b01ba
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3389"></a>Erreur du compilateur C3389
__declspec (Keyword) ne peut pas être utilisé avec/clr : pure ou/CLR : safe  
  
 Les options de compilateur **/clr:pure** et **/clr:safe** sont dépréciées dans Visual Studio 2015.  
  
 A [__declspec](../../cpp/declspec.md) modificateur utilisé implique un état par processus.  [/ CLR : pure](../../build/reference/clr-common-language-runtime-compilation.md) implique un par [appdomain](../../cpp/appdomain.md) état.  Par conséquent, déclarer une variable avec le `keyword` **__declspec** modificateur et la compilation avec **/CLR : pure** n’est pas autorisée.  
  
 L’exemple suivant génère l’erreur C3389 :  
  
```  
// C3389.cpp  
// compile with: /clr:pure /c  
__declspec(dllexport) int g2 = 0;   // C3389  
```