---
title: Erreur du compilateur C2923 | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-diagnostics
ms.topic: error-reference
f1_keywords:
- C2923
dev_langs:
- C++
helpviewer_keywords:
- C2923
ms.assetid: 6b92933b-13ef-4124-99d9-b89f9fdae030
author: corob-msft
ms.author: corob
ms.workload:
- cplusplus
ms.openlocfilehash: b71470ed288abe0a0868c788917dfcecdeeb914a
ms.sourcegitcommit: 76b7653ae443a2b8eb1186b789f8503609d6453e
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/04/2018
---
# <a name="compiler-error-c2923"></a>Erreur du compilateur C2923
'type' : 'identifier' n’est pas un argument de type de modèle valide pour le paramètre 'param'.  
  
 Il manque un type nécessaire pour instancier le modèle ou le générique dans la liste d’arguments. Vérifiez la déclaration du modèle ou du générique.  
  
 L’exemple suivant génère l’erreur C2923 :  
  
```  
// C2923.cpp  
template <class T> struct TC {};  
int x;  
int main() {  
   TC<x>* tc2;   // C2923  
   TC<int>* tc2;   // OK  
}  
```  
  
 L’erreur C2923 peut également se produire lors de l’utilisation de génériques :  
  
```  
// C2923b.cpp  
// compile with: /clr /c  
generic <class T> ref struct GC {};  
  
int x;  
  
int main() {  
   GC<x>^ gc2;   // C2923  
   GC<int>^ gc2;   // OK  
}  
```