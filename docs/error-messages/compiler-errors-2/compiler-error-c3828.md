---
title: Erreur du compilateur C3828 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C3828
dev_langs: C++
helpviewer_keywords: C3828
ms.assetid: 8d9cee75-9504-4bc8-88b6-2413618a3f45
caps.latest.revision: "11"
author: corob-msft
ms.author: corob
manager: ghogen
ms.openlocfilehash: 1b2dfaa6e0c414c80122bcb4291bb021bc1f3c74
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="compiler-error-c3828"></a>Erreur du compilateur C3828
'type objet' : arguments de positionnement non autorisés lors de la création d’instances de gérés ou WinRTclasses  
  
 Lorsque vous créez un objet d’un type managé ou Windows Runtime, vous ne pouvez pas utiliser la forme positionnement de l’opérateur [gcnew de nouveau, ref](../../windows/ref-new-gcnew-cpp-component-extensions.md) ou [nouveau](../../cpp/new-operator-cpp.md).  
  
 L'exemple suivant génère l'erreur C3828 et montre comment la corriger :  
  
```  
// C3828a.cpp  
// compile with: /clr  
ref struct M {  
};  
  
ref struct N {  
   static array<char>^ bytes = gcnew array<char>(256);  
};  
  
int main() {  
   M ^m1 = new (&N::bytes) M();   // C3828  
   // The following line fixes the error.  
   // M ^m1 = gcnew M();  
}  
```