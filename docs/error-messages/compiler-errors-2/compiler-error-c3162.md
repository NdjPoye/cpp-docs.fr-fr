---
title: Erreur du compilateur C3162 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3162
dev_langs:
- C++
helpviewer_keywords:
- C3162
ms.assetid: 0d4c4a24-1456-4191-b7d8-c38cb7b17c32
caps.latest.revision: 4
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 8bfde260ef0efe58ed70469a80a8bf7316eefa46
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3162"></a>Erreur du compilateur C3162
'type' : un type référence qui a un destructeur ne peut pas être utilisé comme type de données membres static 'membre'  
  
 Le common language runtime ne peut pas savoir à quel moment exécuter un destructeur défini par l’utilisateur lorsque la classe contient également la fonction membre statique.  
  
 Un destructeur ne sera jamais exécuté, sauf si l’objet est supprimé de manière explicite.  
  
 Pour plus d'informations, consultez  
  
-   [/CLR (Compilation pour le common Language Runtime)](../../build/reference/clr-common-language-runtime-compilation.md)  
  
-   [Problèmes courants de migration vers Visual C++ 64 bits](../../build/common-visual-cpp-64-bit-migration-issues.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3162.  
  
```  
// C3162.cpp  
// compile with: /clr /c  
ref struct A {  
   ~A() { System::Console::WriteLine("in destructor"); }  
   static A i;   // C3162  
   static A^ a = gcnew A;   // OK  
};  
  
int main() {  
   A ^ a = gcnew A;  
   delete a;  
}  
```
