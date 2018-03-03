---
title: Erreur du compilateur C3861 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3861
dev_langs:
- C++
helpviewer_keywords:
- C3861
ms.assetid: 0a1eee30-b3db-41b1-b1e5-35949c3924d7
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 82656822d408be4b2fc085abe8a007469c822a65
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-error-c3861"></a>Erreur du compilateur C3861

> '*identificateur*' : identificateur introuvable  
  
Le compilateur n’a pas pu résoudre une référence à un identificateur, même à l’aide d’une recherche dépendante d’un argument.  
  
Pour corriger cette erreur, comparez l’utilisation de *identificateur* à la déclaration de l’identificateur de la casse et l’orthographe. Vérifiez que [opérateurs de résolution de portée](../../cpp/scope-resolution-operator.md) et espace de noms [à l’aide de directives](../../cpp/namespaces-cpp.md#using_directives) sont utilisés correctement. Si l’identificateur est déclaré dans un fichier d’en-tête, vérifiez que l’en-tête est inclus avant l’identificateur est référencé. Si l’identificateur est destiné à être visible de l’extérieur, assurez-vous qu’il est déclaré dans un fichier source qui l’utilise. Vérifiez également que la déclaration de l’identificateur ou la définition n’est pas exclue par [directives de compilation conditionnelle](../../preprocessor/hash-if-hash-elif-hash-else-and-hash-endif-directives-c-cpp.md). 

Modifications apportées à supprimer des fonctions obsolètes à partir de la bibliothèque Runtime C dans Visual Studio 2015 peuvent entraîner C3861. Pour résoudre cette erreur, supprimez les références à ces fonctions ou les remplacer avec leurs alternatives sécurisés, le cas échéant. Pour plus d’informations, consultez [fonctions obsolètes](../../c-runtime-library/obsolete-functions.md).  

Si l’erreur C3861 s’affiche après la migration de projet à partir de versions antérieures du compilateur, vous avez peut-être des problèmes liés à des versions de Windows prises en charge. Visual C++ ne prend plus en charge le ciblage de Windows 95, Windows 98, Windows ME, Windows NT ou Windows 2000. Si vos macros WINVER ou _WIN32_WINNT sont attribués à une de ces versions de Windows, vous devez modifier les macros. Pour plus d’informations, consultez [modification de WINVER et _WIN32_WINNT](../../porting/modifying-winver-and-win32-winnt.md).
  
## <a name="example"></a>Exemple  

L’exemple suivant génère l’erreur C3861 car l’identificateur n’est pas défini.  
  
```cpp  
// C3861.cpp  
void f2(){}  
int main() {  
   f();    // C3861  
   f2();   // OK  
}  
```  
  
## <a name="example"></a>Exemple  

L’exemple suivant génère l’erreur C3861 car un identificateur est uniquement visible dans la portée du fichier de définition, sauf si elle est déclarée dans d’autres fichiers de code source qui l’utilisent.  
  
```cpp  
// C3861_a1.cpp
// Compile with: cl /EHsc /W4 C3861_a1.cpp C3861_a2.cpp  
#include <iostream>
// Uncomment the following line to fix:
// int f();  // declaration makes external function visible
int main() {  
   std::cout << f() << std::endl;    // C3861
}  
```  
  
```cpp  
// C3861_a2.cpp  
int f() {  // declared and defined here
   return 42;  
}
```  
  
## <a name="example"></a>Exemple  

Classes d’exceptions dans la bibliothèque Standard C++ nécessitent le `std` espace de noms.  
  
```cpp  
// C3861_b.cpp  
// compile with: /EHsc  
#include <iostream>  
int main() {  
   try {  
      throw exception("Exception");   // C3861  
      // try the following line instead  
      // throw std::exception("Exception");  
   }  
   catch (...) {  
      std::cout << "caught an exception" << std::endl;  
   }  
}  
```  
## <a name="example"></a>Exemple  

Fonctions obsolètes ont été supprimées de la bibliothèque CRT.  
  
```cpp  
// C3861_c.cpp  
#include <stdio.h>  
int main() {  
   char line[21]; // room for 20 chars + '\0'  
   gets( line );  // C3861  
   // Use gets_s instead.  
   printf( "The line entered was: %s\n", line );  
}  
```
L’exemple suivant génère l’erreur C3767, car le compilateur ne peut pas utiliser la recherche dépendante d’un argument pour FriendFunc :  
  
```  
namespace N {  
   class C {  
      friend void FriendFunc() {}  
      friend void AnotherFriendFunc(C* c) {}  
   };  
}  
  
int main() {  
   using namespace N;  
   FriendFunc();   // C3861 error  
   C* pC = new C();  
   AnotherFriendFunc(pC);   // found via argument-dependent lookup  
}  
```  
  
Pour corriger cette erreur, déclarez la fonction friend dans la portée de la classe et la définir dans la portée espace de noms :  
  

classe MyClass {  
   int m_private ;  
   Friend func() void ;  
};  
  
{de func() void  
   MyClass s ;  
   s.m_private = 0 ;  
}  
  
int main() {  
   Func() ;  
}  