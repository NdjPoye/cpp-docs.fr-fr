---
title: "Erreur des outils &#201;diteur de liens LNK2020 | Microsoft Docs"
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
  - "LNK2020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2020"
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: 16
caps.handback.revision: 16
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2020
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

jeton 'jeton' non résolu  
  
 Comparable à une erreur externe non définie, sauf que la référence est par des métadonnées.  Dans les métadonnées, toutes les fonctions et données doivent être définies.  
  
 Pour résoudre :  
  
-   Définissez la fonction ou les données manquantes, ou  
  
-   Incluez le fichier objet ou la bibliothèque dans lequel la fonction ou les données manquantes sont déjà définies.  
  
## Exemple  
 L'exemple suivant génère l'erreur LNK2020.  
  
```  
// LNK2020.cpp  
// compile with: /clr /LD  
ref struct A {  
   A(int x);   // LNK2020  
   static int f();   // LNK2020  
};  
  
// OK  
ref struct B {  
   B(int x) {}  
   static int f() { return 0; }  
};  
```  
  
## Exemple  
 L'erreur LNK2020 est également générée si vous créez une variable d'un type de modèle managé, sans instancier également le type.  
  
 L'exemple suivant génère l'erreur LNK2020.  
  
```  
// LNK2020_b.cpp  
// compile with: /clr   
  
template <typename T>  
ref struct Base {  
   virtual void f1() {};  
};  
  
template <typename T>  
ref struct Base2 {  
   virtual void f1() {};  
};  
  
int main() {  
   Base<int>^ p;   // LNK2020  
   Base2<int>^ p2 = gcnew Base2<int>();   // OK  
};  
```