---
title: "Generic Delegates (Visual C++) | Microsoft Docs"
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
  - "generic delegates"
  - "delegates, generic [C++]"
ms.assetid: 09d430b2-1aef-4fbc-87f9-9d7b8185d798
caps.latest.revision: 20
caps.handback.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Delegates (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser des paramètres de types génériques avec des délégués.  For more information on delegates, see [délégué](../windows/delegate-cpp-component-extensions.md).  
  
## Syntaxe  
  
```  
[attributes]   
generic < [class | typename] type-parameter-identifiers >  
[type-parameter-constraints-clauses]  
[accessibility-modifiers] delegate result-type identifier   
([formal-parameters]);  
```  
  
#### Paramètres  
 `attributes` \(facultatif\)  
 Les informations supplémentaires déclarative.  Pour plus d'informations sur les attributs et les classes d'attributs, consultez la section attributs.  
  
 *type\-paramètre\-indentifiant\(s\)*  
 Liste séparée par des virgules des identificateurs des paramètres de type.  
  
 `type-parameter-constraints-clauses`  
 Le format spécifié dans [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md)  
  
 *Accessibility\- modificateurs* \(facultatif\)  
 Modificateurs d'Accessibilité \(par exemple  **public**, `private`\).  
  
 *result\-type*  
 Type de retour du délégué.  
  
 *identificateur*  
 Nom du délégué.  
  
 *Formels\-paramètres* \(Facultatifs\)  
 La liste de paramètres du délégué.  
  
## Exemple  
 Les paramètres de type délégué sont spécifiés à l'endroit où un objet délégué est créé.  Le délégué et la méthode qui lui est associée doivent avoir la même signature.  L'exemple suivant illustre une déclaration delegate d'événement.  
  
```  
// generics_generic_delegate1.cpp  
// compile with: /clr /c  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
```  
  
## Exemple  
 L'exemple suivant montre que  
  
-   Vous ne pouvez pas utiliser le même objet délégué avec des types construits.  Créez des objets délégués pour différents types.  
  
-   Un délégué générique peut être associé à une méthode générique.  
  
-   Lorsqu'une méthode générique est appelée sans spécifier des arguments de type, le compilateur tente de déduire les arguments de type pour appeler.  
  
```  
// generics_generic_delegate2.cpp  
// compile with: /clr  
generic < class ItemType>  
delegate ItemType GenDelegate(ItemType p1, ItemType% p2);  
  
generic < class ItemType>  
ref struct MyGenClass {  
   ItemType MyMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
ref struct MyClass {  
   generic < class ItemType>  
   static ItemType MyStaticMethod(ItemType i, ItemType % j) {  
      return ItemType();  
   }  
};  
  
int main() {  
   MyGenClass<int> ^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double> ^ myObj2 = gcnew MyGenClass<double>();  
   GenDelegate<int>^ myDelegate1 =  
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   GenDelegate<double>^ myDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   GenDelegate<int>^ myDelegate =  
      gcnew GenDelegate<int>(&MyClass::MyStaticMethod<int>);  
}  
```  
  
## Exemple  
 L'exemple suivant déclare un délégué générique `GenDelegate<ItemType>`, puis les instancie en les associant à la méthode `MyMethod` qui utilise le paramètre de type `ItemType`.  Deux instances du délégué \(entier et une valeur double\) sont créées et sont appelées.  
  
```  
// generics_generic_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare generic delegate  
generic <typename ItemType>  
delegate ItemType GenDelegate (ItemType p1, ItemType% p2);  
  
// Declare a generic class:  
generic <typename ItemType>  
ref class MyGenClass {  
public:  
   ItemType MyMethod(ItemType p1, ItemType% p2) {  
      p2 = p1;  
      return p1;  
    }  
};  
  
int main() {  
   int i = 0, j = 0;   
   double m = 0.0, n = 0.0;  
  
   MyGenClass<int>^ myObj1 = gcnew MyGenClass<int>();  
   MyGenClass<double>^ myObj2 = gcnew MyGenClass<double>();   
  
   // Instantiate a delegate using int.  
   GenDelegate<int>^ MyDelegate1 =   
      gcnew GenDelegate<int>(myObj1, &MyGenClass<int>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   i = MyDelegate1(123, j);  
  
   Console::WriteLine(  
      "Invoking the integer delegate: i = {0}, j = {1}", i, j);  
  
   // Instantiate a delegate using double.  
   GenDelegate<double>^ MyDelegate2 =   
      gcnew GenDelegate<double>(myObj2, &MyGenClass<double>::MyMethod);  
  
   // Invoke the integer delegate using MyMethod.  
   m = MyDelegate2(0.123, n);  
  
   Console::WriteLine(  
      "Invoking the double delegate: m = {0}, n = {1}", m, n);  
}  
```  
  
  **Appeler le délégué entier : i \= 123, j \= 123**  
**Appeler le délégué : double m \= 0,123, n \= 0,123**   
## Voir aussi  
 [Generics](../windows/generics-cpp-component-extensions.md)