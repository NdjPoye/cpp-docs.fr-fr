---
title: Erreur du compilateur C2440 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C2440
dev_langs:
- C++
helpviewer_keywords:
- C2440
ms.assetid: 36e6676c-f04f-4715-8ba1-f096c4bf3b44
caps.latest.revision: 27
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
ms.sourcegitcommit: a937c9d083a7e4331af63323a19fb207142604a0
ms.openlocfilehash: 5f0472f7d318de24c38898388906a264cf56db7b
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-error-c2440"></a>Erreur du compilateur C2440
'conversion' : Impossible de convertir de 'type1' en 'type2'  
  
Le compilateur ne peut pas caster `type1` à `type2`.  
  
## <a name="example"></a>Exemple  
L’erreur C2440 peut se produire si vous tentez d’initialiser une variable non-const `char*` (ou `wchar_t*`) à l’aide d’un littéral de chaîne dans le code C++, lorsque l’option de mise en conformité du compilateur [/Zc : strictstrings](../../build/reference/zc-strictstrings-disable-string-literal-type-conversion.md) est défini. En C, le type d’un littéral de chaîne est tableau de `char`, mais en C++, il s’agit de tableau de `const char`. Cet exemple génère l’erreur C2440 :  
  
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
  
## <a name="example"></a>Exemple  
 C2440 peut aussi survenir si vous tentez de convertir un pointeur de membre à void *. L’exemple suivant génère l’erreur C2440 :  
  
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
  
## <a name="example"></a>Exemple  
 L’erreur C2440 peut aussi survenir si vous tentez d’effectuer un cast d’un type qui est déclaré uniquement en avant, mais pas défini. Cet exemple génère l’erreur C2440 :  
  
```cpp  
// c2440a.cpp   
struct Base { }; // Defined  
  
struct Derived; // Forward declaration, not defined  
  
Base * func(Derived * d) {  
    return static_cast<Base *>(d); // error C2440: 'static_cast' : cannot convert from 'Derived *' to 'Base *'  
}  
  
```  
  
## <a name="example"></a>Exemple  
 Les erreurs C2440 présentes sur les lignes 15 et 16 de l’exemple suivant sont qualifiés avec le `Incompatible calling conventions for UDT return value` message. A *UDT* est un type défini par l’utilisateur, comme une classe, de structure ou union. Ces types d’erreurs d’incompatibilité surviennent lorsque la convention d’appel d’un UDT spécifié dans le type de retour de conflits d’une déclaration anticipée avec la convention d’appel réelle de l’UDT et lorsqu’un pointeur de fonction est impliqué.  
  
 Dans l’exemple, tout d’abord Voici les déclarations anticipées d’une structure ou d’une fonction qui retourne la structure ; le compilateur suppose que la structure utilise la convention d’appel C++. Suivant est la définition de struct qui, par défaut, utilise le C convention d’appel. Étant donné que le compilateur ne sait pas la convention d’appel de la structure jusqu'à ce qu’il a terminé la lecture de la structure entière, la convention d’appel de la structure dans le type de retour de `get_c2` est censée pour être également C++.  
  
 La structure est suivie d’une autre déclaration de fonction qui retourne la structure, mais à ce stade, le compilateur sait que convention d’appel de la structure est en C++. De même, le pointeur de fonction qui retourne la structure, est défini après la définition de la structure afin que le compilateur sait que la structure utilise la convention d’appel C++.  
  
 Pour résoudre l’erreur C2440 qui se produit en raison des conventions d’appel incompatibles, déclarer des fonctions qui retournent un UDT après la définition de l’UDT.  
  
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
  
## <a name="example"></a>Exemple  
 L’erreur C2440 peut également se produire si vous affectez zéro à un pointeur intérieur :  
  
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
  
## <a name="example"></a>Exemple  
 L’erreur C2440 peut également se produire pour une utilisation incorrecte d’une conversion définie par l’utilisateur. Par exemple, lorsqu’un opérateur de conversion a été défini en tant que `explicit`, le compilateur ne peut pas l’utiliser dans une conversion implicite. Pour plus d’informations sur les conversions définies par l’utilisateur, consultez la page [les Conversions définies par l’utilisateur (C + c++ / CLI)](../../dotnet/user-defined-conversions-cpp-cli.md)). Cet exemple génère l’erreur C2440 :  
  
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
  
## <a name="example"></a>Exemple  
 L’erreur C2440 peut également se produire si vous essayez de créer une instance d’un tableau Visual C++ dont le type est un <xref:System.Array>.</xref:System.Array>  Pour plus d’informations, consultez [tableaux](../../windows/arrays-cpp-component-extensions.md).  L’exemple suivant génère l’erreur C2440 :  
  
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
  
## <a name="example"></a>Exemple  
 L’erreur C2440 peut également se produire en raison des modifications apportées aux fonctionnalités des attributs.  L’exemple suivant génère l’erreur C2440.  
  
```cpp  
// c2440f.cpp  
// compile with: /LD  
[ module(name="PropDemoLib", version=1.0) ];   // C2440  
// try the following line instead  
// [ module(name="PropDemoLib", version="1.0") ];  
```  
  
## <a name="example"></a>Exemple  
 Le compilateur Visual C++ n’autorise plus le [opérateur const_cast](../../cpp/const-cast-operator.md) d’effectuer un cast vers le bas lorsque le code qui utilise la source **/clr** programmation est compilée.  
  
 Pour résoudre cette erreur C2440, utilisez l’opérateur de cast correct. Pour plus d’informations, consultez [des opérateurs de conversion](../../cpp/casting-operators.md).  
  
 Cet exemple génère l’erreur C2440 :  
  
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
  
## <a name="example"></a>Exemple  
L’erreur C2440 peut se produire en raison des modifications de mise en conformité du compilateur dans Visual Studio 2015 Update 3. Auparavant, le compilateur traitait de façon erronée certaines expressions distinctes avec le même type lors de l’identification d’une correspondance de modèle pour un `static_cast` opération. Maintenant, le compilateur fait la distinction correctement les types et de code qui reposait sur la précédente `static_cast` comportement est interrompue. Pour résoudre ce problème, modifiez l’argument template pour correspondre au type de paramètre de modèle, ou utiliser un `reinterpret_cast` ou effectuer un cast de style C.
  
Cet exemple génère l’erreur C2440 :  
  
```cpp  
// c2440h.cpp

template<int *a>
struct S1 {};

int g;
struct S2 : S1<&g> {
};

int main()
{
    S2 s;
    static_cast<S1<&*&g>>(s); // C2440 in VS 2015 Update 3 
    // This compiles correctly:
    // static_cast<S1<&g>>(s);
}

This error can appear in ATL code that uses the SINK_ENTRY_INFO macro defined in <atlcom.h>.

```

