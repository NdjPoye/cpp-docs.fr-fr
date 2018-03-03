---
title: Compilateur avertissement (niveau 1) C4326 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4326
dev_langs:
- C++
helpviewer_keywords:
- C4326
ms.assetid: d44d2c4e-9456-42d3-b35b-4ba4b2d42ec7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: faf38d27c0a8d38e008cb94d65fc8745995dd947
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-1-c4326"></a>Avertissement du compilateur (niveau 1) C4326
type de retour de 'function' doit être 'type1' au lieu de 'type2'  
  
 Une fonction a retourné un type autre que ***type1***. Par exemple, à l’aide de [/Za](../../build/reference/za-ze-disable-language-extensions.md), principal n’a pas retourné un `int`.  
  
 L’exemple suivant génère l’erreur C4326 :  
  
```  
// C4326.cpp  
// compile with: /Za /W1  
char main()  
{   // C4326 try int main  
}  
```