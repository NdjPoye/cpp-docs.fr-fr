---
title: "Conversions d&#233;finies par l&#39;utilisateur&#160;(C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "conversions définies par l'utilisateur [C++]"
ms.assetid: 8010fd59-2775-4e9a-a6ed-58055032d66f
caps.latest.revision: 15
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Conversions d&#233;finies par l&#39;utilisateur&#160;(C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette section décrit les conversions définies par l'utilisateur \(UDC\) lorsqu'un des types de conversion est une référence ou une instance d'un type de valeur ou d'un type de référence.  
  
## Conversions implicites et explicites  
 Une conversion définie par l'utilisateur peut être implicite ou explicite.  Une CDU doit être implicite si la conversion ne peut pas se traduire par une perte d'informations.  Sinon une CDU explicite doit être définie.  
  
 Le constructeur natif d'une classe peut être utilisé pour convertir une référence ou un type de valeur dans une classe native.  
  
 Pour plus d'informations sur les conversions, consultez [Boxing](../windows/boxing-cpp-component-extensions.md) et [Conversions standard](../cpp/standard-conversions.md).  
  
```  
// mcpp_User_Defined_Conversions.cpp  
// compile with: /clr  
#include "stdio.h"  
ref class R;  
class N;  
  
value class V {  
   static operator V(R^) {  
      return V();  
   }  
};  
  
ref class R {  
public:  
   static operator N(R^);  
   static operator V(R^) {  
      System::Console::WriteLine("in R::operator N");  
      return V();  
   }  
};  
  
class N {  
public:  
   N(R^) {  
      printf("in N::N\n");  
   }  
};  
  
R::operator N(R^) {  
   System::Console::WriteLine("in R::operator N");  
   return N(nullptr);  
}  
  
int main() {  
   // Direct initialization:  
   R ^r2;  
   N n2(r2);   // direct initialization, calls constructor  
   static_cast<N>(r2);   // also direct initialization  
  
   R ^r3;  
   // ambiguous V::operator V(R^) and R::operator V(R^)  
   // static_cast<V>(r3);     
}  
```  
  
 **Sortie**  
  
  **dans N::N**  
**dans N::N**   
## Opérateurs Convert\-From  
 Les opérateurs Convert\-from créent un objet de la classe dans laquelle l'opérateur est défini depuis un objet d'une autre classe.  
  
 C\+\+ standard ne prend pas en charge les opérateurs convert\-from ; C\+\+ standard utilise des constructeurs à cet effet.  Toutefois, lors de l'utilisation du CLR, Visual C\+\+ fournit la prise en charge syntactique pour l'appel d'opérateurs convert\-from.  
  
 Pour bien interopérer avec d'autres langages conformes à CLS, incluez avec chaque constructeur unaire défini par l'utilisateur d'une classe donnée un opérateur convert\-from.  
  
 Opérateurs Convert\-From :  
  
-   Seront définis en tant que fonctions statiques.  
  
-   Peut être implicite \(pour les conversions qui ne perdent pas leur précision par exemple sort\-to\-int\) ou explicite, lorsqu'il y a perte de précision.  
  
-   Retourne un objet de la classe conteneur.  
  
-   Auront le type "from" en tant que type unique du paramètre.  
  
 L'exemple suivant illustre un opérateur "convert\-from" implicite et explicite, défini par l'utilisateur \(UDC\).  
  
```  
// clr_udc_convert_from.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
  
   MyDouble(int i) {  
      d = static_cast<double>(i);  
      System::Console::WriteLine("in constructor");  
   }  
  
   // Wrap the constructor with a convert-from operator.  
   // implicit UDC because conversion cannot lose precision  
   static operator MyDouble (int i) {  
      System::Console::WriteLine("in operator");  
      // call the constructor  
      MyDouble d(i);  
      return d;  
   }  
  
   // an explicit user-defined conversion operator  
   static explicit operator signed short int (MyDouble) {  
      return 1;  
   }  
};  
  
int main() {  
   int i = 10;  
   MyDouble md = i;  
   System::Console::WriteLine(md.d);  
  
   // using explicit user-defined conversion operator requires a cast    
   unsigned short int j = static_cast<unsigned short int>(md);  
   System::Console::WriteLine(j);  
}  
```  
  
 **Sortie**  
  
  **in \(opérateur\)**  
**in \(constructeur\)**  
**10**  
**1**   
## Opérateurs Convert\-To  
 Les opérateurs Convert\-to convertissent un objet de la classe dans laquelle l'opérateur est défini en un autre objet.  L'exemple suivant illustre un opérateurde conversion implicite, Convert\-to, opérateur défini par l'utilisateur :  
  
```  
// clr_udc_convert_to.cpp  
// compile with: /clr  
using namespace System;  
value struct MyInt {  
   Int32 i;  
  
   // convert MyInt to String^  
   static operator String^ ( MyInt val ) {  
      return val.i.ToString();  
   }  
  
   MyInt(int _i) : i(_i) {}  
};  
  
int main() {  
   MyInt mi(10);  
   String ^s = mi;  
   Console::WriteLine(s);  
}  
```  
  
 **Sortie**  
  
  **10** Un opérateur de conversion défini par l'utilisateur explicite Convert\-to est approprié pour les conversions qui perdent potentiellement les données d'une certaine façon.  Pour appeler un opérateur Convert\-to explicit, un cast doit être utilisé.  
  
```  
// clr_udc_convert_to_2.cpp  
// compile with: /clr  
value struct MyDouble {  
   double d;  
   // convert MyDouble to Int32  
   static explicit operator System::Int32 ( MyDouble val ) {  
      return (int)val.d;  
   }  
};  
  
int main() {  
   MyDouble d;  
   d.d = 10.3;  
   System::Console::WriteLine(d.d);  
   int i = 0;  
   i = static_cast<int>(d);  
   System::Console::WriteLine(i);  
}  
```  
  
 **Sortie**  
  
  **10.3**  
**10**   
## Convertir des classes génériques  
 Vous pouvez convertir une classe générique en T.  
  
```  
// clr_udc_generics.cpp  
// compile with: /clr  
generic<class T>   
public value struct V {  
   T mem;  
   static operator T(V v) {  
      return v.mem;  
   }  
  
   void f(T t) {  
      mem = t;  
   }  
};  
  
int main() {  
   V<int> v;  
   v.f(42);  
   int i = v;  
   i += v;  
   System::Console::WriteLine(i == (42 * 2) );  
}  
```  
  
 **Sortie**  
  
  **True** Un constructeur de conversion prend un type et l'utilise pour créer un objet.  Un constructeur de conversion est appelé avec l'initialisation directe uniquement ; les cast n'appelleront pas de constructeurs de conversion.  Par défaut, les constructeurs de conversion sont explicites pour les types CLR.  
  
```  
// clr_udc_converting_constructors.cpp  
// compile with: /clr  
public ref struct R {  
   int m;  
   char c;  
  
   R(int i) : m(i) { }  
   R(char j) : c(j) { }  
};  
  
public value struct V {  
   R^ ptr;  
   int m;  
  
   V(R^ r) : ptr(r) { }  
   V(int i) : m(i) { }  
};  
  
int main() {   
   R^ r = gcnew R(5);  
  
   System::Console::WriteLine( V(5).m);  
   System::Console::WriteLine( V(r).ptr);  
}  
```  
  
 **Sortie**  
  
  **5**  
**R** Dans cet exemple de code, une fonction statique de conversion implicite fait la même chose qu'un constructeur de conversion explicite.  
  
```  
public value struct V {  
   int m;  
   V(int i) : m(i) {}  
   static operator V(int i) {  
      V v(i*100);  
      return v;  
   }  
};  
  
public ref struct R {  
   int m;  
   R(int i) : m(i) {}  
   static operator R^(int i) {  
      return gcnew R(i*100);  
   }  
};  
  
int main() {  
   V v(13);   // explicit  
   R^ r = gcnew R(12);   // explicit  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
  
   // explicit ctor can't be called here: not ambiguous  
   v = 5;  
   r = 20;  
  
   System::Console::WriteLine(v.m);  
   System::Console::WriteLine(r->m);  
}  
```  
  
 **Sortie**  
  
  **13**  
**12**  
**500**  
**2000**   
## Voir aussi  
 [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md)