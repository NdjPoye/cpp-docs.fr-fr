---
title: Compilateur avertissement (niveau 4) C4242 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4242
dev_langs: C++
helpviewer_keywords: C4242
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
caps.latest.revision: "10"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: b0e51952a615037b4df3a43fb37cd4f3dc3e717e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-warning-level-4-c4242"></a>Avertissement du compilateur (niveau 4) C4242
'identificateur' : conversion de 'type1' en 'type2', perte possible de données  
  
 Les types sont différents. Conversion de type peut entraîner une perte de données. Le compilateur effectue la conversion de type.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
 Pour plus d’informations sur l’erreur C4242, consultez [les erreurs courantes du compilateur](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 L’exemple suivant génère l’erreur C4242 :  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```