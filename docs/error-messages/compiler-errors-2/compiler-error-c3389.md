---
title: Erreur du compilateur C3389 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3389
dev_langs: C++
helpviewer_keywords: C3389
ms.assetid: eaaffe17-23f2-413c-b1ad-f7220cfa1334
caps.latest.revision: "9"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 561359afcd9cf694369bd1addb4f641a33a3f989
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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