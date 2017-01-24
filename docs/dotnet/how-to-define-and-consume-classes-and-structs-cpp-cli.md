---
title: "Comment&#160;: d&#233;finir et consommer des Classes et Structs (C++-CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "structures [C++]"
  - "classes [C++], instanciation"
ms.assetid: 1c03cb0d-1459-4b5e-af65-97d6b3094fd7
caps.latest.revision: 15
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: d&#233;finir et consommer des classes et des structs (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment définir et utiliser des types référence définis par l’utilisateur et les types de valeur dans [!INCLUDE[cppcli](../build/reference/includes/cppcli_md.md)].  
  
##  <a name="a-namebkmkcontentsa-contents"></a><a name="BKMK_Contents"></a> Contenu  
 [Instanciation d’objet](#BKMK_Object_instantiation)  
  
 [Classes implicitement abstraites](#BKMK_Implicitly_abstract_classes)  
  
 [Visibilité du type](#BKMK_Type_visibility)  
  
 [Visibilité des membres](#BKMK_Member_visibility)  
  
 [Classes natives publics et privés](#BKMK_Public_and_private_native_classes)  
  
 [Constructeurs statiques](#BKMK_Static_constructors)  
  
 [Sémantiques de ce pointeur](#BKMK_Semantics_of_the_this_pointer)  
  
 [Fonctions Hide-by-signature](#BKMK_Hide_by_signature_functions)  
  
 [Constructeurs de copie](#BKMK_Copy_constructors)  
  
 [Destructeurs et finaliseurs](#BKMK_Destructors_and_finalizers)  
  
##  <a name="a-namebkmkobjectinstantiationa-object-instantiation"></a><a name="BKMK_Object_instantiation"></a> Instanciation d’objet  
 Types référence (Réf) et les types valeur peuvent uniquement être instanciés sur le tas managé, pas sur la pile ou sur le tas natif.  
  
```  
// mcppv2_ref_class2.cpp  
// compile with: /clr  
ref class MyClass {  
public:  
   int i;  
  
   // nested class  
   ref class MyClass2 {  
   public:  
      int i;  
   };  
  
   // nested interface  
   interface struct MyInterface {  
      void f();  
   };  
};  
  
ref class MyClass2 : public MyClass::MyInterface {  
public:  
   virtual void f() {  
      System::Console::WriteLine("test");  
   }  
};  
  
public value struct MyStruct {  
   void f() {  
      System::Console::WriteLine("test");  
   }     
};  
  
int main() {  
   // instantiate ref type on garbage-collected heap  
   MyClass ^ p_MyClass = gcnew MyClass;  
   p_MyClass -> i = 4;  
  
   // instantiate value type on garbage-collected heap  
   MyStruct ^ p_MyStruct = gcnew MyStruct;  
   p_MyStruct -> f();  
  
   // instantiate value type on the stack  
   MyStruct p_MyStruct2;  
   p_MyStruct2.f();  
  
   // instantiate nested ref type on garbage-collected heap  
   MyClass::MyClass2 ^ p_MyClass2 = gcnew MyClass::MyClass2;  
   p_MyClass2 -> i = 5;  
}  
```  
  
##  <a name="a-namebkmkimplicitlyabstractclassesa-implicitly-abstract-classes"></a><a name="BKMK_Implicitly_abstract_classes"></a> Classes implicitement abstraites  
 Un *implicitement abstraites classe* ne peut pas être instanciée. Une classe est abstraite implicitement si le type de la classe de base est une interface et la classe n’implémente pas toutes les fonctions membres de l’interface.  
  
 Si vous ne parvenez pas à construire des objets à partir d’une classe qui est dérivée d’une interface, la raison peut être que la classe est abstraite implicitement. Pour plus d’informations sur les classes abstraites, consultez [abstraite](../windows/abstract-cpp-component-extensions.md).  
  
 L’exemple de code suivant montre que la `MyClass` classe ne peut pas être instanciée car fonction `MyClass::func2` n’est pas implémentée. Pour activer l’exemple compiler, supprimez les commentaires de `MyClass::func2`.  
  
```  
// mcppv2_ref_class5.cpp  
// compile with: /clr  
interface struct MyInterface {  
   void func1();  
   void func2();  
};  
  
ref class MyClass : public MyInterface {  
public:  
   void func1(){}  
   // void func2(){}  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;   // C2259   
                                          // To resolve, uncomment MyClass::func2.  
}  
```  
  
##  <a name="a-namebkmktypevisibilitya-type-visibility"></a><a name="BKMK_Type_visibility"></a> Visibilité du type  
 Vous pouvez contrôler la visibilité des types common language runtime (CLR) de sorte que, si un assembly est référencé, les types dans l’assembly peuvent être visible ou invisible en dehors de l’assembly.  
  
 `public` Indique qu’un type est visible par n’importe quel fichier source qui contient un `#using` directive pour l’assembly qui contient le type.  `private` Indique qu’un type n’est pas visible pour les fichiers sources qui contiennent un `#using` directive pour l’assembly qui contient le type. Toutefois, les types privés sont visibles dans le même assembly. Par défaut, la visibilité d’une classe est `private`.  
  
 Par défaut avant Visual C++ 2005, les types natifs avaient une accessibilité publique en dehors de l’assembly. Activer [l’avertissement du compilateur (niveau 1) C4692](../error-messages/compiler-warnings/compiler-warning-level-1-c4692.md) pour vous aider à voir où les types natifs privées sont utilisées correctement. Utilisez le [make_public](../preprocessor/make-public.md) pragma afin de donner une accessibilité publique vers un type natif dans un fichier de code source que vous ne pouvez pas modifier.  
  
 Pour plus d’informations, consultez la rubrique [#using, Directive](../preprocessor/hash-using-directive-cpp.md).  
  
 L’exemple suivant montre comment déclarer des types et spécifier leur accessibilité ensuite accéder à ces types dans l’assembly. Bien entendu, si un assembly qui a des types privés est référencé à l’aide de `#using`, seuls les types publics dans l’assembly sont visibles.  
  
```  
// type_visibility.cpp  
// compile with: /clr  
using namespace System;  
// public type, visible inside and outside assembly  
public ref struct Public_Class {  
   void Test(){Console::WriteLine("in Public_Class");}  
};  
  
// private type, visible inside but not outside assembly  
private ref struct Private_Class {  
   void Test(){Console::WriteLine("in Private_Class");}  
};  
  
// default accessibility is private  
ref class Private_Class_2 {  
public:  
   void Test(){Console::WriteLine("in Private_Class_2");}  
};  
  
int main() {  
   Public_Class ^ a = gcnew Public_Class;  
   a->Test();  
  
   Private_Class ^ b = gcnew Private_Class;  
   b->Test();  
  
   Private_Class_2 ^ c = gcnew Private_Class_2;  
   c->Test();  
}  
```  
  
 **Sortie**  
  
```Output  
in Public_Class  
in Private_Class  
in Private_Class_2  
```  
  
 À présent, nous allons réécrire l’exemple précédent afin qu’il est généré sous la forme d’une DLL.  
  
```  
// type_visibility_2.cpp  
// compile with: /clr /LD  
using namespace System;  
// public type, visible inside and outside the assembly  
public ref struct Public_Class {  
   void Test(){Console::WriteLine("in Public_Class");}  
};  
  
// private type, visible inside but not outside the assembly  
private ref struct Private_Class {  
   void Test(){Console::WriteLine("in Private_Class");}  
};  
  
// by default, accessibility is private  
ref class Private_Class_2 {  
public:  
   void Test(){Console::WriteLine("in Private_Class_2");}  
};  
```  
  
 L’exemple suivant montre comment accéder à des types en dehors de l’assembly. Dans cet exemple, le client utilise le composant qui est créé dans l’exemple précédent.  
  
```  
// type_visibility_3.cpp  
// compile with: /clr  
#using "type_visibility_2.dll"  
int main() {  
   Public_Class ^ a = gcnew Public_Class;  
   a->Test();  
  
   // private types not accessible outside the assembly  
   // Private_Class ^ b = gcnew Private_Class;  
   // Private_Class_2 ^ c = gcnew Private_Class_2;  
}  
```  
  
 **Sortie**  
  
```Output  
in Public_Class  
```  
  
##  <a name="a-namebkmkmembervisibilitya-member-visibility"></a><a name="BKMK_Member_visibility"></a> Visibilité des membres  
 Vous pouvez différencient accès à un membre d’une classe publique à partir du même assembly que l’accès à partir en dehors de l’assembly à l’aide des spécificateurs d’accès aux paires de `public`, `protected`, et `private`  
  
 Ce tableau récapitule les effets des spécificateurs d’accès différents :  
  
|Spécificateur|Effet|  
|---------------|------------|  
|public|Membre est accessible à l’intérieur et à l’extérieur de l’assembly.  Consultez [public](../cpp/public-cpp.md) Pour plus d’informations.|  
|private|Membre n’est pas accessible, à l’intérieur ni à l’extérieur de l’assembly.  Consultez [privé](../cpp/private-cpp.md) Pour plus d’informations.|  
|protected|Membre est accessible à l’intérieur et à l’extérieur de l’assembly, mais uniquement pour les types dérivés.  Consultez [protégé](../cpp/protected-cpp.md) Pour plus d’informations.|  
|internal|Membre est public dans l’assembly mais privé en dehors de l’assembly.  `internal` est un mot clé contextuel.  Pour plus d’informations, consultez [mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md).|  
|public public protégé - ou - protégé|Membre est public dans l’assembly mais protégé à l’extérieur de l’assembly.|  
|privé privé protégé - ou - protégé|Membre est protégé à l’intérieur de l’assembly mais privé en dehors de l’assembly.|  
  
 L’exemple suivant illustre un type public qui possède des membres qui sont déclarés avec les accessibilités différents et affiche ensuite l’accès à ces membres d’à l’intérieur de l’assembly.  
  
```  
  
// compile with: /clr  
using namespace System;  
// public type, visible inside and outside the assembly  
public ref class Public_Class {  
public:  
   void Public_Function(){System::Console::WriteLine("in Public_Function");}  
  
private:  
   void Private_Function(){System::Console::WriteLine("in Private_Function");}  
  
protected:  
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}  
  
internal:  
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}  
  
protected public:  
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}  
  
public protected:  
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}  
  
private protected:  
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}  
  
protected private:  
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}  
};  
  
// a derived type, calls protected functions  
ref struct MyClass : public Public_Class {  
   void Test() {  
      Console::WriteLine("=======================");  
      Console::WriteLine("in function of derived class");  
      Protected_Function();  
      Protected_Private_Function();  
      Private_Protected_Function();  
      Console::WriteLine("exiting function of derived class");  
      Console::WriteLine("=======================");  
   }  
};  
  
int main() {  
   Public_Class ^ a = gcnew Public_Class;  
   MyClass ^ b = gcnew MyClass;  
   a->Public_Function();  
   a->Protected_Public_Function();  
   a->Public_Protected_Function();  
  
   // accessible inside but not outside the assembly  
   a->Internal_Function();  
  
   // call protected functions  
   b->Test();  
  
   // not accessible inside or outside the assembly  
   // a->Private_Function();  
}  
```  
  
 **Sortie**  
  
```Output  
in Public_Function  
in Protected_Public_Function  
in Public_Protected_Function  
in Internal_Function  
=======================  
in function of derived class  
in Protected_Function  
in Protected_Private_Function  
in Private_Protected_Function  
exiting function of derived class  
=======================  
```  
  
 Maintenant nous allons développer l’exemple précédent en tant que DLL.  
  
```  
  
// compile with: /clr /LD  
using namespace System;  
// public type, visible inside and outside the assembly  
public ref class Public_Class {  
public:  
   void Public_Function(){System::Console::WriteLine("in Public_Function");}  
  
private:  
   void Private_Function(){System::Console::WriteLine("in Private_Function");}  
  
protected:  
   void Protected_Function(){System::Console::WriteLine("in Protected_Function");}  
  
internal:  
   void Internal_Function(){System::Console::WriteLine("in Internal_Function");}  
  
protected public:  
   void Protected_Public_Function(){System::Console::WriteLine("in Protected_Public_Function");}  
  
public protected:  
   void Public_Protected_Function(){System::Console::WriteLine("in Public_Protected_Function");}  
  
private protected:  
   void Private_Protected_Function(){System::Console::WriteLine("in Private_Protected_Function");}  
  
protected private:  
   void Protected_Private_Function(){System::Console::WriteLine("in Protected_Private_Function");}  
};  
  
// a derived type, calls protected functions  
ref struct MyClass : public Public_Class {  
   void Test() {  
      Console::WriteLine("=======================");  
      Console::WriteLine("in function of derived class");  
      Protected_Function();  
      Protected_Private_Function();  
      Private_Protected_Function();  
      Console::WriteLine("exiting function of derived class");  
      Console::WriteLine("=======================");  
   }  
};  
```  
  
 L’exemple suivant utilise le composant qui est créé dans l’exemple précédent et ce qui montre comment accéder aux membres à partir de l’extérieur de l’assembly.  
  
```  
  
// compile with: /clr  
#using "type_member_visibility_2.dll"  
using namespace System;  
// a derived type, calls protected functions  
ref struct MyClass : public Public_Class {  
   void Test() {  
      Console::WriteLine("=======================");  
      Console::WriteLine("in function of derived class");  
      Protected_Function();  
      Protected_Public_Function();  
      Public_Protected_Function();  
      Console::WriteLine("exiting function of derived class");  
      Console::WriteLine("=======================");  
   }  
};  
  
int main() {  
   Public_Class ^ a = gcnew Public_Class;  
   MyClass ^ b = gcnew MyClass;  
   a->Public_Function();  
  
   // call protected functions  
   b->Test();  
  
   // can't be called outside the assembly  
   // a->Private_Function();  
   // a->Internal_Function();     
   // a->Protected_Private_Function();  
   // a->Private_Protected_Function();  
}  
```  
  
 **Sortie**  
  
```Output  
in Public_Function  
=======================  
in function of derived class  
in Protected_Function  
in Protected_Public_Function  
in Public_Protected_Function  
exiting function of derived class  
=======================  
```  
  
##  <a name="a-namebkmkpublicandprivatenativeclassesa-public-and-private-native-classes"></a><a name="BKMK_Public_and_private_native_classes"></a> Classes natives publics et privés  
 Un type natif peut être référencé à partir d’un type managé.  Par exemple, une fonction dans un type managé peut accepter un paramètre dont le type est une structure native.  Si le type managé et la fonction sont publiques dans un assembly, le type natif doit également être publique.  
  
```  
  
// native type  
public struct N {  
   N(){}  
   int i;  
};  
```  
  
 Ensuite, créez le fichier de code source qui utilise le type natif :  
  
```  
  
// compile with: /clr /LD  
#include "mcppv2_ref_class3.h"  
// public managed type  
public ref struct R {  
   // public function that takes a native type  
   void f(N nn) {}  
};  
```  
  
 À présent, compilez un client :  
  
```  
  
// compile with: /clr  
#using "mcppv2_ref_class3.dll"  
  
#include "mcppv2_ref_class3.h"  
  
int main() {  
   R ^r = gcnew R;  
   N n;  
   r->f(n);  
}  
```  
  
##  <a name="a-namebkmkstaticconstructorsa-static-constructors"></a><a name="BKMK_Static_constructors"></a> Constructeurs statiques  
 Un type CLR, par exemple, une classe ou un struct, peut avoir un constructeur statique qui peut être utilisé pour initialiser les données membres static.  Un constructeur statique est appelé une fois au maximum et est appelé avant l’accès à tout membre statique du type de la première fois.  
  
 Un constructeur d’instance est toujours exécuté après un constructeur statique.  
  
 Le compilateur ne peut pas incorporer un appel à un constructeur si la classe possède un constructeur statique.  Le compilateur ne peut pas incorporer un appel à une fonction membre si la classe est un type valeur, possède un constructeur statique et ne dispose pas d’un constructeur d’instance.  Le CLR peut inline l’appel, mais le compilateur ne peut pas.  
  
 Définir un constructeur statique comme une fonction membre privé, car il est destiné à être appelé uniquement par le CLR.  
  
 Pour plus d’informations sur les constructeurs statiques, consultez [Comment : définir un constructeur d’Interface statique (C + c++ / CLI)](../dotnet/how-to-define-an-interface-static-constructor-cpp-cli.md) .  
  
```  
  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
private:  
   static int i = 0;  
  
   static MyClass() {  
      Console::WriteLine("in static constructor");  
      i = 9;  
   }  
  
public:  
   static void Test() {  
      i++;  
      Console::WriteLine(i);  
   }  
};  
  
int main() {  
   MyClass::Test();  
   MyClass::Test();  
}  
```  
  
 **Sortie**  
  
```Output  
in static constructor  
10  
11  
```  
  
##  <a name="a-namebkmksemanticsofthethispointera-semantics-of-the-this-pointer"></a><a name="BKMK_Semantics_of_the_this_pointer"></a> Sémantiques de ce pointeur  
 Lorsque vous utilisez Visual C++ pour définir des types, les `this` le pointeur dans un type de référence est de type « handle ». Le `this` pointeur en un type valeur est de type « pointeur intérieur ».  
  
 Ces sémantiques différentes de la `this` pointeur peut provoquer un comportement inattendu lorsqu’un indexeur par défaut est appelé. L’exemple suivant montre comment accéder à un indexeur par défaut dans un type de référence et un type de valeur.  
  
 Pour plus d'informations, consultez  
  
-   [Handle vers l’objet ^, opérateur](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)  
  
-   [interior_ptr (C + c++ / CLI)](../windows/interior-ptr-cpp-cli.md)  
  
-   [Comment : utiliser des propriétés indexées](../misc/how-to-use-indexed-properties.md)  
  
```  
  
// compile with: /clr  
using namespace System;  
  
ref struct A {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
  
   A() {  
      // accessing default indexer  
      Console::WriteLine("{0}", this[3.3]);  
   }  
};  
  
value struct B {  
   property Double default[Double] {  
      Double get(Double data) {  
         return data*data;  
      }  
   }  
   void Test() {  
      // accessing default indexer  
      Console::WriteLine("{0}", this->default[3.3]);  
   }  
};  
  
int main() {  
   A ^ mya = gcnew A();  
   B ^ myb = gcnew B();  
   myb->Test();  
}  
```  
  
 **Sortie**  
  
```Output  
10.89  
10.89  
```  
  
##  <a name="a-namebkmkhidebysignaturefunctionsa-hide-by-signature-functions"></a><a name="BKMK_Hide_by_signature_functions"></a> Fonctions Hide-by-signature  
 En C++ standard, une fonction dans une classe de base est masquée par une fonction qui a le même nom dans une classe dérivée, même si la fonction de classe dérivée n’a pas le même nombre ou type de paramètres. Cela est appelé *Masquer par nom* sémantique. Dans un type référence, une fonction dans une classe de base peut uniquement être masquée par une fonction dans une classe dérivée si le nom et la liste de paramètres sont identiques. Il s’agit *hide-by-signature* sémantique.  
  
 Une classe est considérée comme une classe hide-by-signature lorsque toutes ses fonctions sont marquées dans les métadonnées comme `hidebysig`. Par défaut, toutes les classes qui sont créés sous **/clr** ont `hidebysig` fonctions. Toutefois, une classe qui est compilée à l’aide de **/clr : oldSyntax** n’a pas `hidebysig` fonctions ; au lieu de cela, ils sont des fonctions de masquage-par-nom. Lorsqu’une classe a `hidebysig` fonctions, le compilateur ne masque pas les fonctions par nom dans les classes de base directes, mais si le compilateur rencontre une classe masquer par nom dans une chaîne d’héritage, il poursuit ce comportement masquer par nom.  
  
 La sémantique hide-by-signature, lorsqu’une fonction est appelée sur un objet, le compilateur identifie la classe la plus dérivée qui contient une fonction qui peut répondre à l’appel de fonction. S’il existe une seule fonction dans la classe qui peut répondre à l’appel, le compilateur appelle cette fonction. S’il existe plusieurs fonctions dans la classe qui peut répondre à l’appel, le compilateur utilise pour déterminer quelle fonction appeler les règles de résolution de surcharge. Pour plus d’informations sur les règles de surcharge, consultez [surcharge de fonction](../cpp/function-overloading.md).  
  
 Pour un appel de fonction donné, une fonction dans une classe de base peut avoir une signature qui rend légèrement meilleure qu’une fonction dans une classe dérivée. Toutefois, si la fonction a été appelée explicitement sur un objet de la classe dérivée, la fonction dans la classe dérivée est appelée.  
  
 Étant donné que la valeur de retour n’est pas considéré comme faisant partie de signature d’une fonction, une fonction de classe de base est masquée si elle a le même nom et prend le même nombre et le type des arguments comme une fonction de classe dérivée, même s’il est différent du type de la valeur de retour.  
  
 L’exemple suivant montre une fonction dans une classe de base n’est pas masquée par une fonction dans une classe dérivée.  
  
```  
  
// compile with: /clr  
using namespace System;  
ref struct Base {  
   void Test() {   
      Console::WriteLine("Base::Test");   
   }  
};  
  
ref struct Derived : public Base {  
   void Test(int i) {   
      Console::WriteLine("Derived::Test");   
   }  
};  
  
int main() {  
   Derived ^ t = gcnew Derived;  
   // Test() in the base class will not be hidden  
   t->Test();  
}  
```  
  
 **Sortie**  
  
```Output  
Base::Test  
```  
  
 L’exemple suivant montre que le compilateur Visual C++ appelle une fonction dans la classe la plus dérivée, même si une conversion est nécessaire pour correspondre à un ou plusieurs des paramètres et pas appeler une fonction dans une classe de base qui est une meilleure correspondance pour l’appel de fonction.  
  
```  
  
// compile with: /clr  
using namespace System;  
ref struct Base {  
   void Test2(Single d) {   
      Console::WriteLine("Base::Test2");   
   }  
};  
  
ref struct Derived : public Base {  
   void Test2(Double f) {   
      Console::WriteLine("Derived::Test2");   
   }  
};  
  
int main() {  
   Derived ^ t = gcnew Derived;  
   // Base::Test2 is a better match, but the compiler  
   // calls a function in the derived class if possible  
   t->Test2(3.14f);  
}  
```  
  
 **Sortie**  
  
```Output  
Derived::Test2  
```  
  
 L’exemple suivant montre qu’il est possible de masquer une fonction, même si la classe de base a la même signature que la classe dérivée.  
  
```  
  
// compile with: /clr  
using namespace System;  
ref struct Base {  
   int Test4() {   
      Console::WriteLine("Base::Test4");   
      return 9;   
   }  
};  
  
ref struct Derived : public Base {  
   char Test4() {   
      Console::WriteLine("Derived::Test4");   
      return 'a';   
   }  
};  
  
int main() {  
   Derived ^ t = gcnew Derived;  
  
   // Base::Test4 is hidden  
   int i = t->Test4();  
   Console::WriteLine(i);  
}  
```  
  
 **Sortie**  
  
```Output  
Derived::Test4  
97  
```  
  
 L’exemple suivant définit un composant qui est compilé à l’aide de **/clr : oldSyntax**. Classes définies par l’utilisation des Extensions managées pour C++ ont des fonctions membres de masquer par nom.  
  
```  
  
// compile with: /clr:oldSyntax /LD  
using namespace System;  
public __gc struct Base0 {  
   void Test() {   
      Console::WriteLine("in Base0::Test");  
   }  
};  
  
public __gc struct Base1 : public Base0 {  
   void Test(int i) {   
      Console::WriteLine("in Base1::Test");  
   }  
};  
```  
  
 L’exemple suivant utilise le composant qui est créé dans l’exemple précédent. Notez comment masquer par signature fonctionnalité n’est pas appliquée aux classes de base des types qui sont compilés à l’aide de **/clr : oldSyntax**.  
  
```  
  
// compile with: /clr:oldSyntax /LD  
// compile with: /clr  
using namespace System;  
#using "hide_by_signature_4.dll"  
  
ref struct Derived : public Base1 {  
   void Test(int i, int j) {   
      Console::WriteLine("Derived::Test");  
   }  
};  
  
int main() {  
   Derived ^ t = gcnew Derived;  
   t->Test(8, 8);   // OK  
   t->Test(8);   // OK  
   t->Test();   // C2661  
}  
```  
  
##  <a name="a-namebkmkcopyconstructorsa-copy-constructors"></a><a name="BKMK_Copy_constructors"></a> Constructeurs de copie  
 La norme C++ indique qu’un constructeur de copie est appelé lorsqu’un objet est déplacé, tel qu’un objet est créé et détruit à la même adresse.  
  
 Toutefois, lorsque **/clr** est utilisé pour la compilation et une fonction qui est compilée en appels MSIL natif de fonction où une classe native, ou plusieurs, est passé par valeur et où la classe native a un constructeur de copie et/ou du destructeur, aucun constructeur de copie n’est appelée et l’objet est détruit à une adresse différente de celle où il a été créé. Cela peut entraîner des problèmes si la classe possède un pointeur en elle-même, ou si le code effectue le suivi des objets par adresse.  
  
 Pour plus d'informations, consultez [/clr (Common Language Runtime Compilation)](../build/reference/clr-common-language-runtime-compilation.md).  
  
 L’exemple suivant montre que lorsqu’un constructeur de copie n’est pas généré.  
  
```  
  
// compile with: /clr  
#include<stdio.h>  
  
struct S {  
   int i;  
   static int n;  
  
   S() : i(n++) {   
      printf_s("S object %d being constructed, this=%p\n", i, this);   
   }  
  
   S(S const& rhs) : i(n++) {   
      printf_s("S object %d being copy constructed from S object "  
               "%d, this=%p\n", i, rhs.i, this);   
   }  
  
   ~S() {  
      printf_s("S object %d being destroyed, this=%p\n", i, this);   
   }  
};  
  
int S::n = 0;  
  
#pragma managed(push,off)  
void f(S s1, S s2) {  
   printf_s("in function f\n");  
}  
#pragma managed(pop)  
  
int main() {  
   S s;  
   S t;  
   f(s,t);  
}  
```  
  
 **Sortie**  
  
```Output  
S object 0 being constructed, this=0018F378  
S object 1 being constructed, this=0018F37C  
S object 2 being copy constructed from S object 1, this=0018F380  
S object 3 being copy constructed from S object 0, this=0018F384  
S object 4 being copy constructed from S object 2, this=0018F2E4  
S object 2 being destroyed, this=0018F380  
S object 5 being copy constructed from S object 3, this=0018F2E0  
S object 3 being destroyed, this=0018F384  
in function f  
S object 5 being destroyed, this=0018F2E0  
S object 4 being destroyed, this=0018F2E4  
S object 1 being destroyed, this=0018F37C  
S object 0 being destroyed, this=0018F378  
```  
  
##  <a name="a-namebkmkdestructorsandfinalizersa-destructors-and-finalizers"></a><a name="BKMK_Destructors_and_finalizers"></a> Destructeurs et finaliseurs  
 Destructeurs dans un type référence effectuer un déterministe nettoyage des ressources. Les finaliseurs nettoyer les ressources non managées et peuvent être appelées de façon déterministe par le destructeur ou de manière non déterministe par le garbage collector. Pour plus d’informations à propos des destructeurs c++ standard, consultez [destructeurs](../cpp/destructors-cpp.md).  
  
```  
class classname {  
   ~classname() {}   // destructor  
   ! classname() {}   // finalizer  
};  
```  
  
 Le comportement de destructeurs dans une classe Visual C++ managée diffère des Extensions managées pour C++. Pour plus d’informations sur cette modification, consultez la page [les modifications de la sémantique du destructeur](../dotnet/changes-in-destructor-semantics.md).  
  
 Le garbage collector CLR supprime les objets managés inutilisés et libère leur mémoire lorsqu’ils ne sont plus nécessaires. Toutefois, un type peut utiliser le garbage collector ne sait pas comment libérer des ressources. Ces ressources sont des ressources non managées (fichier natif prend en charge, par exemple). Nous vous recommandons de libérer toutes les ressources non managées dans le finaliseur. Étant donné que les ressources managées sont libérées de manière non déterministe par le garbage collector, il n’est pas sécurisé faire référence à des ressources gérées dans un finaliseur, car il est possible que le garbage collector a nettoyé déjà cette ressource managée.  
  
 Un finaliseur Visual C++ n’est pas le même que le <xref:System.Object.Finalize%2A> méthode. (Documentation du CLR utilise le finaliseur et la <xref:System.Object.Finalize%2A> méthode indifféremment). Le <xref:System.Object.Finalize%2A> méthode est appelée par le garbage collector, qui appelle chaque finaliseur dans une chaîne d’héritage de classe. Contrairement aux destructeurs Visual C++, un appel du finaliseur de classe dérivée n’entraîne pas le compilateur appeler le finaliseur de toutes les classes de base.  
  
 Étant donné que le compilateur Visual C++ prend en charge la libération des ressources, n’essayez pas de mettre en œuvre la <xref:System.IDisposable.Dispose%2A> ou <xref:System.Object.Finalize%2A> méthodes. Toutefois, si vous êtes familiarisé avec ces méthodes, voici comment mappent les un finaliseur Visual C++ et un destructeur qui appelle le finaliseur pour le <xref:System.IDisposable.Dispose%2A> modèle :  
  
```  
// Visual C++ code  
ref class T {  
   ~T() { this->!T(); }   // destructor calls finalizer  
   !T() {}   // finalizer  
};  
  
// equivalent to the Dispose pattern  
void Dispose(bool disposing) {  
   if (disposing) {  
      ~T();  
   } else {  
      !T();  
   }  
}  
```  
  
 Un type managé peut également utiliser les ressources managées que vous préférez pour lancer de façon déterministe et ne doivent pas quitter le garbage collector pour libérer de manière non déterministe à un moment donné une fois que l’objet n’est plus nécessaire. La libération des ressources peut améliorer considérablement les performances.  
  
 Le compilateur Visual C++ permet la définition d’un destructeur pour nettoyer les objets de façon déterministe. Utiliser le destructeur libère toutes les ressources que vous souhaitez libérer de manière déterministe.  Si un finaliseur est présent, l’appeler à partir du destructeur, afin d’éviter la duplication de code.  
  
```  
  
// compile with: /clr /c  
ref struct A {  
   // destructor cleans up all resources  
   ~A() {  
      // clean up code to release managed resource  
      // ...  
      // to avoid code duplication,   
      // call finalizer to release unmanaged resources  
      this->!A();  
   }  
  
   // finalizer cleans up unmanaged resources  
   // destructor or garbage collector will  
   // clean up managed resources  
   !A() {  
      // clean up code to release unmanaged resources  
      // ...  
   }  
};  
```  
  
 Si le code qui utilise votre type n’appelle pas le destructeur, le garbage collector libère éventuellement les ressources managées.  
  
 La présence d’un destructeur n’implique pas la présence d’un finaliseur. Toutefois, la présence d’un finaliseur implique que vous devez définir un destructeur et appeler le finaliseur de ce destructeur. Cela permet de la libération des ressources non managées.  
  
 Supprime l’appel du destructeur, à l’aide de <xref:System.GC.SuppressFinalize%2A>— la finalisation de l’objet. Si le destructeur n’est pas appelé, le finaliseur de votre type sera appelé par le garbage collector.  
  
 Nettoyage déterministe des ressources de l’objet en appelant le destructeur peut améliorer les performances par rapport à laisser le CLR de manière non déterministe finaliser l’objet.  
  
 Code écrit en Visual C++ et compilé à l’aide de **/clr** exécute le destructeur d’un type si :  
  
-   Un objet est créé à l’aide de la sémantique de pile est hors de portée. Pour plus d’informations, consultez [la sémantique de pile C++ pour les Types référence](../dotnet/cpp-stack-semantics-for-reference-types.md).  
  
-   Une exception est levée pendant la construction de l’objet.  
  
-   L’objet est un membre d’un objet dont le destructeur s’exécute.  
  
-   Vous appelez le [Supprimer](../cpp/delete-operator-cpp.md) opérateur sur une poignée ([gérer sur l’opérateur Object (^)](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)).  
  
-   Vous appelez explicitement le destructeur.  
  
 Si votre type est consommé par un client qui est écrit dans une autre langue, le destructeur est appelé comme suit :  
  
-   Un appel à <xref:System.IDisposable.Dispose%2A>.  
  
-   Un appel à `Dispose(void)` sur le type.  
  
-   Si le type est hors de portée dans C# `using` instruction.  
  
 Si vous créez un objet d’un type référence sur le tas managé (ne pas à l’aide de la sémantique de pile pour les types référence), utilisez [try-finally](../cpp/try-finally-statement.md) syntaxe pour vous assurer qu’une exception n’empêche pas le destructeur d’en cours d’exécution.  
  
```  
  
// compile with: /clr  
ref struct A {  
   ~A() {}  
};  
  
int main() {  
   A ^ MyA = gcnew A;  
   try {  
      // use MyA  
   }  
   finally {  
      delete MyA;  
   }  
}  
```  
  
 Si le type a un destructeur, le compilateur génère un `Dispose` méthode qui implémente <xref:System.IDisposable>. Si un type est écrit en Visual C++ et a un destructeur est consommé à partir d’une autre langue, l’appel `IDisposable::Dispose` sur ce type entraîne le destructeur du type à appeler. Lorsque le type est consommé à partir d’un client Visual C++, vous ne pouvez pas appeler directement `Dispose`; au lieu de cela, appelez le destructeur en utilisant le `delete` opérateur.  
  
 Si le type a un finaliseur, le compilateur génère un `Finalize(void)` méthode substitue <xref:System.Object.Finalize%2A>.  
  
 Si un type a un finaliseur ou un destructeur, le compilateur génère un `Dispose(bool)` (méthode), en fonction du modèle de conception. (Pour plus d’informations, consultez [Modèle de suppression](../Topic/Dispose%20Pattern.md)). Vous ne pouvez pas explicitement créer ou appelez `Dispose(bool)` dans Visual C++.  
  
 Si un type a une classe de base qui respecte le modèle de conception, les destructeurs pour toutes les classes de base sont appelés lorsque le destructeur de la classe dérivée est appelé. (Si votre type est écrit en Visual C++, le compilateur garantit que vos types implémentent ce modèle.) En d’autres termes, le destructeur d’une classe de référence est lié à ses bases et membres comme spécifié par la norme C++ : premier destructeur de la classe est exécuté, les destructeurs pour ses membres dans l’ordre inverse de l’ordre dans lequel ils ont été construits et enfin les destructeurs de ses classes de base dans l’ordre inverse de l’ordre dans lequel elles ont été construites.  
  
 Destructeurs et finaliseurs ne sont pas autorisés dans les types valeur ou des interfaces.  
  
 Un finaliseur peut uniquement être défini ou déclaré dans un type référence. Comme un constructeur et un destructeur, un finaliseur n’a aucun type de retour.  
  
 Après l’exécution du finaliseur d’un objet, les finaliseurs de classes de base sont également appelés, commençant par le type moins dérivé. Finaliseurs pour les membres de données ne sont pas automatiquement chaînées à par un finaliseur de classe.  
  
 Si un finaliseur supprime un pointeur natif dans un type managé, vous devez vous assurer que les références à ou via le pointeur natif ne sont pas collectés prématurément ; appelle le destructeur du type managé au lieu d’utiliser <xref:System.GC.KeepAlive%2A>.  
  
 Au moment de la compilation, vous pouvez détecter si un type a un finaliseur ou un destructeur. Pour plus d’informations, consultez [prise en charge du compilateur pour les caractéristiques de Type](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 L’exemple suivant montre deux types, il possède des ressources non managées et celui qui a géré les ressources sont libérées de façon déterministe.  
  
```  
  
// compile with: /clr  
#include <vcclr.h>  
#include <stdio.h>  
using namespace System;  
using namespace System::IO;  
  
ref class SystemFileWriter {  
   FileStream ^ file;  
   array<Byte> ^ arr;  
   int bufLen;  
  
public:  
   SystemFileWriter(String ^ name) : file(File::Open(name, FileMode::Append)),   
                                     arr(gcnew array<Byte>(1024)) {}  
  
   void Flush() {  
      file->Write(arr, 0, bufLen);  
      bufLen = 0;  
   }  
  
   ~SystemFileWriter() {  
      Flush();  
      delete file;  
   }  
};  
  
ref class CRTFileWriter {  
   FILE * file;  
   array<Byte> ^ arr;  
   int bufLen;  
  
   static FILE * getFile(String ^ n) {  
      pin_ptr<const wchar_t> name = PtrToStringChars(n);  
      FILE * ret = 0;  
      _wfopen_s(&ret, name, L"ab");  
      return ret;  
   }  
  
public:  
   CRTFileWriter(String ^ name) : file(getFile(name)), arr(gcnew array<Byte>(1024) ) {}  
  
   void Flush() {  
      pin_ptr<Byte> buf = &arr[0];  
      fwrite(buf, 1, bufLen, file);  
      bufLen = 0;  
   }  
  
   ~CRTFileWriter() {  
      this->!CRTFileWriter();  
   }  
  
   !CRTFileWriter() {  
      Flush();  
      fclose(file);  
   }  
};  
  
int main() {  
   SystemFileWriter w("systest.txt");  
   CRTFileWriter ^ w2 = gcnew CRTFileWriter("crttest.txt");  
}  
```  
  
## <a name="see-also"></a>Voir aussi  
 [Les classes et Structs](../windows/classes-and-structs-cpp-component-extensions.md)   
 [Les classes et Structs](../windows/classes-and-structs-cpp-component-extensions.md)