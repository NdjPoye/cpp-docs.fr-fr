---
title: "C-Style Casts with /clr (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C-style casts and /clr"
ms.assetid: d2a4401a-156a-4da9-8d12-923743e26913
caps.latest.revision: 13
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# C-Style Casts with /clr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La rubrique suivante s'applique uniquement au CLR.  
  
 Lorque utilisé avec le CLR, les tentatives du compilateur de mapper la conversion du style C à l'une des conversions parmi celles indiquées ci\-dessous, dans l'ordre suivant :  
  
1.  const\_cast  
  
2.  safe\_cast  
  
3.  safe\_cast plus le const\_cast  
  
4.  static\_cast  
  
5.  static\_cast plus le const\_cast  
  
 Si aucun des conversions listée au\-dessus n'est valide, et si le type de l'expression et du type de cible sont des types référence CLR, C\-style génère des cartes a un verificateur au moment de l'exécution \(instruction\) castclass MSIL\).  Sinon, la conversion de la solution est considérée comme étant valide et les problèmes du compilateur une erreur.  
  
## Notes  
 La conversion de style en cours c n'est pas recommandée.  Lors de la compilation avec [\/clr \(Compilation pour le Common Language Runtime\)](../build/reference/clr-common-language-runtime-compilation.md), utilisez [safe\_cast](../windows/safe-cast-cpp-component-extensions.md).  
  
 L'exemple suivant montre la conversion de style mappé à `const_cast`.  
  
```  
// cstyle_casts_1.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
int main() {  
   const R^ constrefR = gcnew R();  
   R^ nonconstR = (R^)(constrefR);   
}  
```  
  
 L'exemple suivant montre la conversion de style mappé à `safe_cast`.  
  
```  
// cstyle_casts_2.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   Object ^ o = "hello";  
   String ^ s = (String^)o;  
}  
```  
  
 L'exemple suivant montre la conversion de style mappé à `safe_cast` ainsi que `const_cast`.  
  
```  
// cstyle_casts_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct R {};  
ref struct R2 : public R {};  
  
int main() {  
   const R^ constR2 = gcnew R2();  
   try {  
   R2^ b2DR = (R2^)(constR2);  
   }  
   catch(InvalidCastException^ e) {  
      System::Console::WriteLine("Invalid Exception");  
   }  
}  
```  
  
 L'exemple suivant montre la conversion de style mappé à `static_cast`.  
  
```  
// cstyle_casts_4.cpp  
// compile with: /clr  
using namespace System;  
  
struct N1 {};  
struct N2 {  
   operator N1() {  
      return N1();  
   }  
};  
  
int main() {  
   N2 n2;  
   N1 n1 ;  
   n1 = (N1)n2;  
}  
```  
  
 L'exemple suivant montre la conversion de style mappé à `static_cast` ainsi que `const_cast`.  
  
```  
// cstyle_casts_5.cpp  
// compile with: /clr  
using namespace System;  
struct N1 {};  
  
struct N2 {  
   operator const N1*() {  
      static const N1 n1;  
      return &n1;  
   }  
};  
  
int main() {  
   N2 n2;  
   N1* n1 = (N1*)(const N1*)n2;   // const_cast + static_cast  
}  
```  
  
 L'exemple suivant montre la conversion de style mappé à une vérification en cours de exécution.  
  
```  
// cstyle_casts_6.cpp  
// compile with: /clr  
using namespace System;  
  
ref class R1 {};  
ref class R2 {};  
  
int main() {  
   R1^ r  = gcnew R1();  
   try {  
      R2^ rr = ( R2^)(r);  
   }  
   catch(System::InvalidCastException^ e) {  
      Console::WriteLine("Caught expected exception");  
   }  
}  
```  
  
 L'exemple suivant illustre une conversion de type C invalide, qui a pour conséquence de faire faire au compilateur une erreur.  
  
```  
// cstyle_casts_7.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   String^s = S"hello";  
   int i = (int)s;   // C2440  
}  
```  
  
## Conditions requises  
 Option du compilateur : **\/clr**  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)