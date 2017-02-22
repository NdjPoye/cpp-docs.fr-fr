---
title: "Erreur du compilateur C2440 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2440"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2440"
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 27
---
# Erreur du compilateur C2440
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'conversion' : impossible de convertir de 'type1' en 'type2'  
  
 Le compilateur ne peut pas caster '`type1`' en '`type2`'.  
  
## Exemple  
 L'erreur C2440 peut être provoquée si vous tentez d'initialiser un `char*` non const \(ou `wchar_t*`\) à l'aide d'un littéral de chaîne en code C\+\+, lorsque l'option de conformité du compilateur [\/Zc:strictStrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) est définie.  En C, le type d'un littéral de chaîne est un tableau de `char`, mais en C\+\+, il correspond à un tableau de `const` `char`.  Cet exemple génère l'erreur C2440 :  
  
```cpp  
// C2440s.cpp  
// Build: cl /Zc:strictStrings /W3 C2440s.cpp  
// When built, the compiler emits:  
// error C2440: 'initializing' : cannot convert from 'const char [5]'   
// to 'char *'  
//        Conversion from string literal loses const qualifier (see  
// /Zc:strictStrings)  
  
int main() {  
   char* s1 = "test"; // C2440  
   const char* s2 = "tests"; // OK  
}  
```  
  
## Exemple  
 L'erreur C2440 peut également être provoquée si vous essayez de convertir un pointeur de membre en type void\*.  L'exemple suivant génère l'erreur C2440 :  
  
```cpp  
// C2440.cpp  
class B {  
public:  
   void  f(){;}  
  
   typedef void (B::*pf)();  
  
   void f2(pf pf) {  
       (this->*pf)();  
       void* pp = (void*)pf;   // C2440  
   }  
  
   void f3() {  
      f2(f);  
   }  
};  
```  
  
## Exemple  
 L'erreur C2440 peut également être provoquée si vous tentez d'effectuer un cast d'un type qui est uniquement déclaré avec anticipation mais pas défini.  Cet exemple génère l'erreur C2440 :  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## Exemple  
 Les erreurs C2440 présentes sur les lignes 15 et 16 de l'exemple suivant sont qualifiées avec le message `Incompatible calling conventions for UDT return value`. \(Un UDT est un type défini par l'utilisateur tel que class, struct ou union.\) Ces sortes d'erreurs d'incompatibilité surviennent lorsque la convention d'appel d'un UDT spécifié dans le type de retour d'une déclaration anticipée est en conflit avec la convention d'appel réelle de l'UDT et lorsqu'un pointeur fonction est impliqué.  
  
 Dans l'exemple, vous avez d'abord les déclarations anticipées d'une structure ou d'une fonction qui retourne la structure ; le compilateur considère que la structure utilise la convention d'appel en C\+\+.  Ensuite, vous avez la définition de struct qui, par défaut, utilise la convention d'appel en C.  Comme le compilateur ne connaît la convention d'appel de la structure qu'à la fin de la lecture de la structure complète, la convention d'appel de la structure dans le type de retour de `get_c2` est censée être également en C\+\+.  
  
 La structure est suivie d'une autre déclaration de fonction qui retourne la structure mais, à ce stade, le compilateur sait que la convention d'appel de la structure est en C\+\+.  De même, le pointeur fonction, qui retourne la structure, est défini après la définition de la structure de sorte que le compilateur sait que la structure utilise la convention d'appel en C\+\+.  
  
 Pour corriger l'erreur C2440 liée à l'incompatibilité des conventions d'appel, déclarez des fonctions qui retournent un UDT après la définition de l'UDT.  
  
```cpp  
// C2440b.cpp  
struct MyStruct;  
  
MyStruct get_c1();  
  
struct MyStruct {  
   int i;  
   static MyStruct get_C2();  
};  
  
MyStruct get_C3();  
  
typedef MyStruct (*FC)();  
  
FC fc1 = &get_c1;   // C2440, line 15  
FC fc2 = &MyStruct::get_C2;   // C2440, line 16  
FC fc3 = &get_C3;  
  
class CMyClass {  
public:  
   explicit CMyClass( int iBar)  
      throw()   {  
   }  
  
   static CMyClass get_c2();  
};  
  
int main() {  
   CMyClass myclass = 2;   // C2440  
   // try one of the following  
   // CMyClass myclass{2};  
   // CMyClass myclass(2);  
  
   int *i;  
   float j;  
   j = (float)i;   // C2440, cannot cast from pointer to int to float  
}  
```  
  
## Exemple  
 L'erreur C2440 peut également se produire si vous assignez la valeur zéro à un pointeur intérieur :  
  
```cpp  
// C2440c.cpp  
// compile with: /clr  
int main() {  
   array<int>^ arr = gcnew array<int>(100);  
   interior_ptr<int> ipi = &arr[0];  
   ipi = 0;   // C2440  
   ipi = nullptr;   // OK  
}  
```  
  
## Exemple  
 L'erreur C2440 peut également survenir en cas d'utilisation incorrecte d'une conversion définie par l'utilisateur.  Pour plus d'informations sur les conversions définies par l'utilisateur, consultez [Conversions définies par l'utilisateur](../../dotnet/user-defined-conversions-cpp-cli.md).  Cet exemple génère l'erreur C2440 :  
  
```cpp  
// C2440d.cpp  
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
   int i;  
   i = d;   // C2440  
   // Uncomment the following line to resolve.  
   // i = static_cast<int>(d);  
}  
```  
  
## Exemple  
 L'erreur C2440 peut également se produire si vous essayez de créer une instance d'un tableau Visual C\+\+ dont le type est <xref:System.Array>.  Pour plus d'informations, consultez [Arrays](../../windows/arrays-cpp-component-extensions.md).  L'exemple suivant génère l'erreur C2440 :  
  
```cpp  
// C2440e.cpp  
// compile with: /clr  
using namespace System;  
int main() {  
   array<int>^ intArray = Array::CreateInstance(__typeof(int), 1);   // C2440  
   // try the following line instead  
   // array<int>^ intArray = safe_cast<array<int> ^>(Array::CreateInstance(__typeof(int), 1));  
}  
```  
  
## Exemple  
 L'erreur C2440 peut également se produire en raison de modifications apportées aux fonctionnalités des attributs.  L'exemple suivant génère l'erreur C2440 :  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## Exemple  
 Le compilateur Visual C\+\+ n'autorise plus l'[const\_cast, opérateur](../../cpp/const-cast-operator.md) à effectuer un cast aval lorsque le code source qui utilise la programmation **\/clr** est compilé.  
  
 Pour résoudre cette erreur C2440, utilisez l'opérateur de cast correct.  Pour plus d'informations, consultez [Opérateurs de casting](../../cpp/casting-operators.md).  
  
 Cet exemple génère l'erreur C2440 :  
  
```cpp  
// c2440g.cpp  
// compile with: /clr  
ref class Base {};  
ref class Derived : public Base {};  
int main() {  
   Derived ^d = gcnew Derived;  
   Base ^b = d;  
   d = const_cast<Derived^>(b);   // C2440  
   d = dynamic_cast<Derived^>(b);   // OK  
}  
```  
  
## Exemple  
 L'erreur C2440 peut également être générée à l'aide de **\/clr:oldSyntax** :  
  
```cpp  
// c2440h.cpp  
// compile with: /clr:oldSyntax  
__gc class Base {};  
__gc class Derived : public Base {};  
int main() {  
   Derived *d = new Derived;  
   Base *b = d;  
   d = const_cast<Derived*>(b);   // C2440  
   d = dynamic_cast<Derived*>(b);   // OK  
}  
```