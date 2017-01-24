---
title: "Erreur du compilateur C3104 | Microsoft Docs"
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
  - "C3104"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3104"
ms.assetid: b5648d47-e5d3-4b45-a3c0-f46e04eae731
caps.latest.revision: 14
caps.handback.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3104
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

argument non conforme pour l'attribut  
  
 Vous avez spécifié un argument non valide pour un attribut.  
  
 Pour plus d'informations, consultez [Attribute Parameter Types](../../windows/attribute-parameter-types-cpp-component-extensions.md).  
  
 Cette erreur peut être due à la mise en conformité du compilateur pour Visual C\+\+ 2005 : lors du passage de tableaux managés à des attributs personnalisés, le type du tableau n'est plus déduit de la liste d'initialisation d'agrégats.  Le compilateur exige désormais que vous spécifiiez le type du tableau ainsi que la liste d'initialiseurs.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3104 :  
  
```  
// C3104a.cpp  
// compile with: /clr /c  
using namespace System;  
  
[AttributeUsage(AttributeTargets::Class)]  
public ref struct ABC : public Attribute {  
   ABC(array<int>^){}  
   array<double> ^ param;  
};  
  
[ABC( {1,2,3}, param = {2.71, 3.14})]   // C3104  
// try the following line instead  
// [ABC( gcnew array<int> {1,2,3}, param = gcnew array<double>{2.71, 3.14})]   
ref struct AStruct{};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C3104 :  
  
```  
// C3104b.cpp  
// compile with: /clr /c  
// C3104 expected  
using namespace System;  
  
int func() {  
   return 0;   
}  
  
[attribute(All)]  
ref class A {  
public:   
   A(int) {}  
};  
  
// Delete the following 2 lines to resolve.  
[A(func())]  
ref class B {};  
  
// OK  
[A(0)]  
ref class B {};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C3104 :  
  
```  
// C3104c.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
  
[ attribute(Class) ]  
public __gc class AnotherAttr {  
public:  
   AnotherAttr(Object* arr __gc[]) : var0(arr) {}  
   Object* var1 __gc[];  
   Object* var0 __gc[];  
};  
  
[ AnotherAttr( { __box(3.14159), S"pi" }, var1 = { S"a", S"b" } ) ]   // C3104  
public __gc class Class1 {};  
  
// OK  
[ AnotherAttr( new Object * __gc[] {__box(3.14159), S"pi" }, var1 = new Object * __gc[] { S"a", S"b" } ) ]  
public __gc class Class2 {};  
```