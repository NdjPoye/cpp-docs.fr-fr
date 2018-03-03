---
title: Compilateur avertissement (niveaux 2 et 4) C4200 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4200
dev_langs:
- C++
helpviewer_keywords:
- C4200
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
caps.latest.revision: 
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: f160476deb2ab3e4ad0ff00100305c934dfb14c3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-levels-2-and-4-c4200"></a>Avertissement du compilateur (niveaux 2 et 4) C4200
extension non standard utilisée : tableau de taille zéro dans un struct/union  
  
 Indique qu'une structure ou une union contient un tableau de taille zéro.  
  
 La déclaration d'un tableau de taille zéro est une extension Microsoft. Cela provoque un avertissement de niveau 2 lors de la compilation d'un fichier C++ et un avertissement de niveau 4 lors de la compilation d'un fichier C. La compilation C++ génère aussi cet avertissement : « Impossible de générer un constructeur de copie ou un opérateur d'assignation de copie lorsque UDT contient un tableau de taille zéro. » Cet exemple génère l'avertissement C4200 :  
  
```cpp  
// C4200.cpp  
// compile by using: cl /W4 c4200.cpp  
struct A {  
    int a[0];  // C4200  
};  
int main() {  
}  
```  
  
 Cette extension non standard est souvent utilisée pour assurer une interface entre le code et les structures de données externes qui ont une longueur variable. Si ce scénario s'applique à votre code, vous pouvez désactiver l'avertissement :  
  
## <a name="example"></a>Exemple  
  
```cpp  
// C4200b.cpp  
// compile by using: cl /W4 c4200a.cpp  
#pragma warning(disable : 4200)  
struct A {  
    int a[0];  
};  
int main() {  
}  
```