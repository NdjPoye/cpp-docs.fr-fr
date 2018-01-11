---
title: "Erreur LNK2020 des outils Éditeur de liens | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: LNK2020
dev_langs: C++
helpviewer_keywords: LNK2020
ms.assetid: 4dd017d0-5e83-471b-ac8a-538ac1ed6870
caps.latest.revision: "16"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 394cafe23851df5320a78a4e165a90422fc305de
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="linker-tools-error-lnk2020"></a>Erreur des outils Éditeur de liens LNK2020
jeton non résolu 'jeton'  
  
 Semblable à une erreur externe non définie, sauf que la référence est via des métadonnées. Dans les métadonnées, toutes les fonctions et des données doivent être définies.  
  
 Pour résoudre :  
  
-   Définir la fonction ou les données manquantes ou  
  
-   Inclure le fichier objet ou la bibliothèque dans lequel la fonction ou les données manquantes sont déjà définies.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère l’erreur LNK2020.  
  
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
  
## <a name="example"></a>Exemple  
 LNK2020 se produit également si vous créez une variable d’un type de modèle managé, mais que vous n’instanciez pas également le type.  
  
 L’exemple suivant génère l’erreur LNK2020.  
  
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