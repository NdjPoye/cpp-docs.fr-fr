---
title: Erreur du compilateur C2678 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2678
dev_langs:
- C++
helpviewer_keywords:
- C2678
ms.assetid: 1f0a4e26-b429-44f5-9f94-cb66441220c8
caps.latest.revision: 12
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: c243063a9770542f137d5950e8a269f771960f74
ms.openlocfilehash: ce8ee4a0b211bb90ed8f04184f2ac96962032436
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2678"></a>Erreur du compilateur C2678
'opérateur' binaire : aucun opérateur trouvé qui accepte un opérande de partie gauche de type 'type' (ou il n’existe pas de conversion acceptable)  
  
 Pour utiliser l'opérateur, vous devez le surcharger pour le type spécifié ou définir une conversion vers un type pour lequel l'opérateur est défini.  
  
## <a name="example"></a>Exemple  
 L’erreur C2678 peut se produire quand l’opérande de partie gauche est qualifié const, mais que l’opérateur est défini pour accepter un argument non const.  
  
 L'exemple suivant génère l'erreur C2678 et montre comment la corriger :  
  
```  
// C2678a.cpp  
// Compile by using: cl /EHsc /W4 C2678a.cpp  
struct Combo {  
   int number;  
   char letter;  
};  
  
inline Combo& operator+=(Combo& lhs, int rhs) {  
   lhs.number += rhs;  
   return lhs;  
}  
  
int main() {  
   Combo const combo1{ 42, 'X' };  
   Combo combo2{ 13, 'Z' };  
  
   combo1 += 6; // C2678  
   combo2 += 9; // OK - operator+= matches non-const Combo  
}  
```  
  
## <a name="example"></a>Exemple  
 L'erreur C2678 peut également se produire si vous n'épinglez pas un membre natif avant d'appeler une fonction membre dessus.  
  
 L'exemple suivant génère l'erreur C2678 et montre comment la corriger :  
  
```  
// C2678.cpp  
// compile with: /clr /c  
struct S { int _a; };  
  
ref class C {  
public:  
   void M( S param ) {  
      test = param;   // C2678  
  
      // OK  
      pin_ptr<S> ptest = &test;  
      *ptest = param;  
   }  
   S test;  
};  
```  

