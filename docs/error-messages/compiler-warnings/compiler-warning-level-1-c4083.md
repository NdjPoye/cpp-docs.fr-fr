---
title: Compilateur avertissement (niveau 1) C4083 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4083
dev_langs: C++
helpviewer_keywords: C4083
ms.assetid: e7d3344e-5645-4d56-8460-d1acc9145ada
caps.latest.revision: "7"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 66a614d71e27b6a90500bd6e3b24f6894a9d5820
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-1-c4083"></a>Compilateur avertissement (niveau 1) C4083
'jeton' attendu trouver l’identificateur 'identificateur'  
  
 Un identificateur apparaît dans un emplacement erroné dans une **#pragma** instruction.  
  
## <a name="example"></a>Exemple  
  
```  
// C4083.cpp  
// compile with: /W1 /LD  
#pragma warning disable:4083    // C4083  
#pragma warning(disable:4083)   //correct  
```  
  
 Vérifiez la syntaxe de la [#pragma](../../preprocessor/pragma-directives-and-the-pragma-keyword.md) directives.