---
title: "Avertissement du compilateur (niveaus 2 and 4) C4200 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4200"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4200"
ms.assetid: e44d6073-937f-42b7-acc1-65e802b475c6
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveaus 2 and 4) C4200
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

extension non standard utilisée : tableau de taille zéro dans un struct\/union  
  
 Indique qu'une structure ou une union contient un tableau de taille zéro.  
  
 La déclaration d'un tableau de taille zéro est une extension Microsoft.  Cela provoque un avertissement de niveau 2 lors de la compilation d'un fichier C\+\+ et un avertissement de niveau 4 lors de la compilation d'un fichier C.  La compilation C\+\+ génère aussi cet avertissement : « Impossible de générer un constructeur de copie ou un opérateur d'assignation de copie lorsque UDT contient un tableau de taille zéro. » Cet exemple génère l'avertissement C4200 :  
  
```cpp  
// C4200.cpp  
// compile by using: cl /W4 c4200.cpp  
struct A {  
    int a[0];  // C4200  
};  
int main() {  
}  
```  
  
 Cette extension non standard est souvent utilisée pour assurer une interface entre le code et les structures de données externes qui ont une longueur variable.  Si ce scénario s'applique à votre code, vous pouvez désactiver l'avertissement :  
  
## Exemple  
  
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