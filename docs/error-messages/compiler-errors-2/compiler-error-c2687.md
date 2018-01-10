---
title: Erreur du compilateur C2687 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C2687
dev_langs: C++
helpviewer_keywords: C2687
ms.assetid: 1d24b24a-cd0f-41cc-975c-b08dcfb7f402
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: dd6879fafa12a9757e18256520e7bd75957ca52b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c2687"></a>Erreur du compilateur C2687
'type' : déclaration d’exception ne peut pas être 'void' ou désigner un type incomplet ou pointeur ou une référence à un type incomplet  
  
 Pour un type faire partie d’une déclaration d’exception, il doit être défini et différent de void.  
  
 L’exemple suivant génère l’erreur C2687 :  
  
```  
// C2687.cpp  
class C;  
  
int main() {  
   try {}  
   catch (C) {}   // C2687 error  
}  
```  
  
 Solution possible :  
  
```  
// C2687b.cpp  
// compile with: /EHsc  
class C {};  
  
int main() {  
   try {}  
   catch (C) {}  
}  
```