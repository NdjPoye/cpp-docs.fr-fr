---
title: "Generic Classes (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
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
  - "classes [C++], generic"
  - "generic classes [C++], about generic classes"
  - "data types [C++], generic"
  - "generic classes"
  - "generics [C++], declaring generic classes"
ms.assetid: 0beb99e1-1ec4-4fee-9836-ce9657d67a3a
caps.latest.revision: 33
caps.handback.revision: 31
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Classes (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une classe générique est déclarée en utilisant la syntaxe suivante :  
  
## Syntaxe  
  
```  
[attributes]  
generic <class-key type-parameter-identifier(s)>  
[constraint-clauses]  
[accessibility-modifiers] ref class identifier  [modifiers]  
[: base-list]   
{  
   class-body  
} [declarators] [;]  
```  
  
## Notes  
 Dans la syntaxe ci\-dessus, les termes suivants sont utilisés :  
  
 `attributes` \(facultatif\)  
 Les informations supplémentaires déclarative.  Pour plus d'informations sur les attributs et les classes d'attributs, consultez la section attributs.  
  
 *class\-key*  
 Soit `class`, soit `typename`  
  
 *type\-paramètre\-indentifiant\(s\)*,  
 Liste d'identificateurs séparée par des virgules qui spécifie les noms des paramètres de type.  
  
 *contrainte\-clauses*  
 Une liste \(non séparée par des virgules\) de clauses de **where** spécifiant les contraintes des paramètres de type.  Prend la forme suivante :  
  
 `where`  *type\-parameter\-identifier*  `:`  *constraint\-list*  `...`  
  
 *liste de contraintes*  
 *classe\-ou\-interface*\[`,`*...*\]  
  
 *Modificateurs d'accessibilité*  
 Modificateurs d'Accessibilité pour la classe générique.  Pour [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)], le seul modificateur autorisé est `private`.  Pour le common langage runtime\), les modificateurs autorisés sont `private` et `public`.  
  
 *identificateur*  
 Nom de la classe générique, un identificateur valide et C\+\+.  
  
 *Modificateur* \(facultatif\)  
 Les modificateurs autorisés sont `sealed` et **abstract**.  
  
 *base liste*  
 Liste qui contient une classe de base et toutes les interfaces implémentées, tout en les séparant par des virgules.  
  
 *classe corps*  
 Le corps de la classe, qui contient des champs, des fonctions membres, etc.  
  
 *déclarateurs*  
 Toutes les déclarations de variables de ce type.  Par exemple :*identificateur* de  `^`\[`,` …\]  
  
 Vous pouvez déclarer les classes génériques tels que ceux\-ci \(notez que le mot clé **classe** peut être utilisé à la place de **nom de type**\).  Dans cet exemple, `ItemType`, `KeyType` et `ValueType` sont des types inconnus spécifiés au point où le type.  `HashTable<int, int>` est un type construit du type générique `HashTable<KeyType, ValueType>`.  Un certain nombre de types construits peuvent être construits d'un type générique unique.  Les types construits, construits de classes génériques sont traités comme tout autre type de classe de référence.  
  
```  
// generic_classes_1.cpp  
// compile with: /clr  
using namespace System;  
generic <typename ItemType>  
ref struct Stack {  
   // ItemType may be used as a type here  
   void Add(ItemType item) {}  
};  
  
generic <typename KeyType, typename ValueType>  
ref class HashTable {};  
  
// The keyword class may be used instead of typename:  
generic <class ListItem>  
ref class List {};  
  
int main() {  
   HashTable<int, Decimal>^ g1 = gcnew HashTable<int, Decimal>();  
}  
```  
  
 Les types de valeur \(les types intégrés tels que `int` ou `double`, ou types de valeur définis par l'utilisateur\) et les types référence peuvent être utilisés comme argument du type générique.  La syntaxe de la définition générique est la même quelle que soit la situation.  Syntaxe, le type inconnu est considéré comme étant un type de référence.  Toutefois, le runtime peut déterminer que le type effectivement utilisé est un type de valeur et remplacer le code généré approprié pour l'accès direct aux membres.  Les types de valeur utilisés comme arguments de type générique ne sont pas enfermés dans la boîte et par conséquent ne souffrent pas l'altération des performances associée au boxing.  La syntaxe utilisée dans le corps du générique doit être **T^** et '**\-\>**' au lieu de '**.**'.  Toute utilisation de [ref new, gcnew](../windows/ref-new-gcnew-cpp-component-extensions.md) pour le paramètre de type est interprétée correctement par le runtime comme simple création d'un type de valeur si l'argument de type est un type de valeur.  
  
 Vous pouvez également déclarer une classe générique avec [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md) sur les types d'éléments qui peuvent être utilisés pour le paramètre de type.  Dans l'exemple suivant n'importe quel type utilisé pour `ItemType` doit implémenter l'interface `IItem`.  Tenter d'utiliser `int`, par exemple, qui n'implémente pas `IItem`, produirait une erreur de compilation car l'argument de type ne satisfait pas la contrainte.  
  
```  
// generic_classes_2.cpp  
// compile with: /clr /c  
interface class IItem {};  
generic <class ItemType>  
where ItemType : IItem  
ref class Stack {};  
```  
  
 Les classes génériques dans le même espace de noms ne peuvent pas être surchargées en modifiant uniquement le nombre ou les types de paramètres de type.  Toutefois, si chaque classe vit dans un espace de noms différent, elles peuvent être surchargées.  Par exemple, considérez les deux classes suivantes, `MyClass` et `MyClass<ItemType>`, dans les espaces de noms `A` et `B`.  Les deux classes peuvent être surchargées dans un troisième espace de noms c c :  
  
```  
// generic_classes_3.cpp  
// compile with: /clr /c  
namespace A {  
   ref class MyClass {};  
}  
  
namespace B {  
   generic <typename ItemType>   
   ref class MyClass2 { };  
}  
  
namespace C {  
   using namespace A;  
   using namespace B;  
  
   ref class Test {  
      static void F() {  
         MyClass^ m1 = gcnew MyClass();   // OK  
         MyClass2<int>^ m2 = gcnew MyClass2<int>();   // OK  
      }  
   };  
}  
```  
  
 Les classes de base et les interfaces de base ne peuvent pas être des paramètres de type.  Toutefois, la classe de base peut impliquer le paramètre de type comme argument, comme dans le cas suivant :  
  
```  
// generic_classes_4.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
interface class IInterface {};  
  
generic <typename ItemType>  
ref class MyClass : IInterface<ItemType> {};  
```  
  
 Les constructeurs et les destructeurs sont exécutés une fois pour chaque instance de l'objet \(comme d'habitude\) ; les constructeurs statiques sont exécutés une fois pour chaque type construit.  
  
## Champs dans les classes génériques  
 Cette section illustre l'utilisation des champs d'instance et statiques dans les classes génériques.  
  
### Variables d'instance  
 Les variables d'instance d'une classe générique peuvent avoir des types et des initialiseurs de variable qui incluentt tous les paramètres de type de la classe englobant.  
  
## Exemple  
 Dans l'exemple suivant, trois instances différentes de la classe générique, MyClass\<ItemType\>, sont créés à l'aide de les arguments de type approprié \(`int`, **double**, et **string**\).  
  
```  
// generics_instance_fields1.cpp  
// compile with: /clr  
// Instance fields on generic classes  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
// Field of the type ItemType:  
public :  
   ItemType field1;  
   // Constructor using a parameter of the type ItemType:  
   MyClass(ItemType p) {  
     field1 = p;   
   }  
};  
  
int main() {  
   // Instantiate an instance with an integer field:  
   MyClass<int>^ myObj1 = gcnew MyClass<int>(123);  
   Console::WriteLine("Integer field = {0}", myObj1->field1);  
  
   // Instantiate an instance with a double field:  
   MyClass<double>^ myObj2 = gcnew MyClass<double>(1.23);  
   Console::WriteLine("Double field = {0}", myObj2->field1);  
  
   // Instantiate an instance with a String field:  
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>("ABC");  
   Console::WriteLine("String field = {0}", myObj3->field1);  
   }  
```  
  
  **Zone entière \= 123**  
**Double champ \= 1,23**  
**Champ de chaîne \= ABC**   
## Variables Statiques  
 Sur la création d'un type générique, les instances de toutes les variables statiques sont créées et tout constructeur statique pour ce type est exécuté.  
  
 Les variables statiques peuvent utiliser tous les paramètres de type de la classe englobant.  
  
## Exemple  
 L'exemple suivant illustre l'utilisation des champs statiques et un constructeur statique d'une classe générique.  
  
```  
// generics_static2.cpp  
// compile with: /clr  
using namespace System;  
  
interface class ILog {  
   void Write(String^ s);  
};  
  
ref class DateTimeLog : ILog {  
public:  
   virtual void Write(String^ s) {  
      Console::WriteLine( "{0}\t{1}", DateTime::Now, s);  
   }  
};  
  
ref class PlainLog : ILog {  
public:  
   virtual void Write(String^ s) { Console::WriteLine(s); }  
};  
  
generic <typename LogType>  
where LogType : ILog  
ref class G {  
   static LogType s_log;  
  
public:  
   G(){}  
   void SetLog(LogType log) { s_log = log; }  
   void F() { s_log->Write("Test1"); }  
   static G() { Console::WriteLine("Static constructor called."); }     
};  
  
int main() {  
   G<PlainLog^>^ g1 = gcnew G<PlainLog^>();  
   g1->SetLog(gcnew PlainLog());  
   g1->F();  
  
   G<DateTimeLog^>^ g2 = gcnew G<DateTimeLog^>();  
   g2->SetLog(gcnew DateTimeLog());  
  
   // prints date  
   // g2->F();  
}  
```  
  
  **Le constructeur statique appellé.**  
**Le constructeur statique appellé.**  
**Le constructeur statique appellé.**  
**Test1**   
## Méthodes des classes génériques  
 Les méthodes des classes génériques peuvent être génériques elles\-mêmes ; les méthodes génériques sont implicitement paramétrables par le paramètre de type de la classe.  
  
 Les règles particulières suivantes s'appliquent aux méthodes dans les classes génériques :  
  
-   Les méthodes des classes génériques peuvent utiliser des paramètres de type en guise de paramètres, types de retour, ou variables locales.  
  
-   Les méthodes des classes génériques peuvent utiliser les types construits ouverts et fermés comme paramètres, types de retour, ou variables locales.  
  
### Méthodes génériques dans les classes génériques  
 Les méthodes des classes génériques qui n'ont pas de paramètres de type supplémentaire sont généralement indiquées comme générique bien qu'elles soient paramétrables implicitement par la classe générique englobant.  
  
 La signature de la méthode générique peut inclure un ou plusieurs paramètres de type de la classe englobant, directement ou dans un type construit ouvert.  Par exemple :  
  
 `void MyMethod(MyClass<ItemType> x) {}`  
  
 Le corps de ces méthodes peuvent également utiliser ces paramètres de type.  
  
## Exemple  
 L'exemple suivant déclare une méthode générique, `ProtectData`, dans une classe générique, `MyClass<ItemType>`.  La méthode utilise le paramètre de type `ItemType` de classe dans sa signature d'un type construit ouvert.  
  
```  
// generics_non_generic_methods1.cpp  
// compile with: /clr  
// Non-generic methods within a generic class.  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
public:  
   String^ name;  
   ItemType data;  
  
   MyClass(ItemType x) {  
      data = x;  
   }  
  
   // Non-generic method using the type parameter:  
   virtual void ProtectData(MyClass<ItemType>^ x) {  
      data = x->data;  
   }  
};  
  
// ItemType defined as String^  
ref class MyMainClass: MyClass<String^> {  
public:  
   // Passing "123.00" to the constructor:  
   MyMainClass(): MyClass<String^>("123.00") {  
      name = "Jeff Smith";   
   }   
  
   virtual void ProtectData(MyClass<String^>^ x) override {  
      x->data = String::Format("${0}**", x->data);  
   }  
  
   static void Main() {  
      MyMainClass^ x1 = gcnew MyMainClass();  
  
      x1->ProtectData(x1);  
      Console::WriteLine("Name: {0}", x1->name);  
      Console::WriteLine("Amount: {0}", x1->data);  
   }  
};  
  
int main() {  
   MyMainClass::Main();  
}  
```  
  
  **Nom: Jeff Smith**  
**Montant: $123.00\*\***   
## Méthodes génériques dans les classes génériques  
 Vous pouvez déclarer les méthodes génériques dans les classes génériques et non\-génériques.  Par exemple :  
  
## Exemple  
  
```  
// generics_method2.cpp  
// compile with: /clr /c  
generic <typename Type1>  
ref class G {  
public:  
   // Generic method having a type parameter  
   // from the class, Type1, and its own type  
   // parameter, Type2  
   generic <typename Type2>  
   void Method1(Type1 t1, Type2 t2) { F(t1, t2); }  
  
   // Non-generic method:  
   // Can use the class type param, Type1, but not Type2.  
   void Method2(Type1 t1) { F(t1, t1); }  
  
   void F(Object^ o1, Object^ o2) {}  
};  
```  
  
 La méthode générique est toujours générique dans le sens qu'elle est paramétrable par le paramètre de type de la classe, mais elle n'a pas de paramètres de type supplémentaire.  
  
 Tous les types de méthode dans la classe génériques peuvent être génériques, y compris les curseurs statiques instance, les méthodes, et virtuels.  
  
## Exemple  
 L'exemple suivant montre comment déclarer et utiliser les méthodes génériques dans les classes génériques :  
  
```  
// generics_generic_method2.cpp  
// compile with: /clr  
using namespace System;  
generic <class ItemType>  
ref class MyClass {  
public:  
   // Declare a generic method member.  
   generic <class Type1>  
   String^ MyMethod(ItemType item, Type1 t) {  
      return String::Concat(item->ToString(), t->ToString());  
   }  
};  
  
int main() {  
   // Create instances using different types.  
   MyClass<int>^ myObj1 = gcnew MyClass<int>();  
   MyClass<String^>^ myObj2 = gcnew MyClass<String^>();  
   MyClass<String^>^ myObj3 = gcnew MyClass<String^>();  
  
   // Calling MyMethod using two integers.  
   Console::WriteLine("MyMethod returned: {0}",  
            myObj1->MyMethod<int>(1, 2));  
  
   // Calling MyMethod using an integer and a string.  
   Console::WriteLine("MyMethod returned: {0}",  
            myObj2->MyMethod<int>("Hello #", 1));  
  
   // Calling MyMethod using two strings.  
   Console::WriteLine("MyMethod returned: {0}",  
       myObj3->MyMethod<String^>("Hello ", "World!"));  
  
   // generic methods can be called without specifying type arguments  
   myObj1->MyMethod<int>(1, 2);  
   myObj2->MyMethod<int>("Hello #", 1);  
   myObj3->MyMethod<String^>("Hello ", "World!");  
}  
```  
  
  **MyMethod retourné : 12**  
**MyMethod retourné : Hello \#1**  
**MyMethod retourné : Hello World\!**   
## Utilisation de tables imbriquées dans les classes génériques  
 Tout comme avec les classes ordinaires, vous pouvez déclarer les autres types dans une classe générique.  La déclaration de classe imbriquée est implicitement paramétrable par les paramètres de type de la déclaration de classe externe.  Par conséquent, une classe séparée imbriquée est définie pour chaque type externe construit.  Par exemple dans la déclaration,  
  
```  
// generic_classes_5.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref struct Outer {  
   ref class Inner {};  
};  
```  
  
 Le type Outer\<int\>::Inner n'est pas identique au type Outer\<double\>::Inner.  
  
 Comme avec les méthodes génériques dans les classes génériques, les paramètres de type supplémentaires peuvent être définies pour le type imbriqué.  Si vous utilisez les mêmes noms de paramètre de type de la classe interne et externe, le paramètre de type interne masquera le paramètre de type externe.  
  
```  
// generic_classes_6.cpp  
// compile with: /clr /c  
generic <typename ItemType>  
ref class Outer {  
   ItemType outer_item;   // refers to outer ItemType  
  
   generic <typename ItemType>  
   ref class Inner {  
      ItemType inner_item;   // refers to Inner ItemType  
   };  
};  
```  
  
 Étant donné qu'il n'existe aucun moyen pour faire référence au paramètre de type externe, le compilateur produit une erreur dans cette situation.  
  
 Lorsque des types génériques imbriqués construits sont nommés, le paramètre de type pour le type externe n'est pas inclus dans la liste des paramètres de type pour le type interne, même si le type interne est implicitement paramétrable par le paramètre de type externe de type.  Dans le cas ci\-dessus, un nom de type construit est Outer\<int\>::Inner\<string\>.  
  
 L'exemple suivant illustre la construction et la lecture d'une liste liée à des tables imbriquées dans les classes génériques.  
  
## Exemple  
  
```  
// generics_linked_list.cpp  
// compile with: /clr  
using namespace System;  
generic <class ItemType>  
ref class LinkedList {  
// The node class:  
public:  
   ref class Node {  
   // The link field:  
   public:  
      Node^ next;  
      // The data field:  
      ItemType item;   
   } ^first, ^current;  
};  
  
ref class ListBuilder {  
public:  
   void BuildIt(LinkedList<double>^ list) {  
      /* Build the list */  
      double m[5] = {0.1, 0.2, 0.3, 0.4, 0.5};  
      Console::WriteLine("Building the list:");  
  
      for (int n=0; n<=4; n++) {  
         // Create a new node:  
         list->current = gcnew LinkedList<double>::Node();  
  
         // Assign a value to the data field:  
         list->current->item = m[n];  
  
         // Set the link field "next" to be the same as   
         // the "first" field:  
         list->current->next = list->first;  
  
         // Redirect "first" to the new node:  
         list->first = list->current;  
  
         // Display node's data as it builds:  
         Console::WriteLine(list->current->item);  
      }  
   }  
  
   void ReadIt(LinkedList<double>^ list) {  
      // Read the list  
      // Make "first" the "current" link field:  
      list->current = list->first;  
      Console::WriteLine("Reading nodes:");  
  
      // Read nodes until current == null:  
      while (list->current != nullptr) {  
         // Display the node's data field:  
         Console::WriteLine(list->current->item);  
  
         // Move to the next node:  
         list->current = list->current->next;  
      }  
   }  
};  
  
int main() {  
   // Create a list:  
   LinkedList<double>^ aList = gcnew LinkedList<double>();  
  
   // Initialize first node:  
   aList->first = nullptr;  
  
   // Instantiate the class, build, and read the list:   
   ListBuilder^ myListBuilder = gcnew ListBuilder();  
   myListBuilder->BuildIt(aList);  
   myListBuilder->ReadIt(aList);  
}  
```  
  
  **Générer la liste :**  
**0.1**  
**0.2**  
**0.3**  
**0.4**  
**0.5**  
**Nœuds de lecture :**  
**0.5**  
**0.4**  
**0.3**  
**0.2**  
**0.1**   
## Propriétés, événements, indexeurs et opérateurs dans les classes génériques  
  
-   Les propriétés, les événements, les indexeurs et les opérateurs peuvent utiliser des paramètres de type de la classe générique englobant comme valeurs de retour, paramètres, ou variables locales, telle que `ItemType` soit un paramètre de type d'une classe :  
  
    ```  
    public ItemType MyProperty {}  
    ```  
  
-   Les propriétés, les événements, les indexeurs et les opérateurs ne peuvent pas eux\-mêmes être paramétrés.  
  
## Exemple  
 Cet exemple montre les déclarations d'une propriété d'instance d'une classe générique.  
  
```  
// generics_generic_properties1.cpp  
// compile with: /clr  
using namespace System;  
  
generic <typename ItemType>  
ref class MyClass {  
private:  
   property ItemType myField;  
  
public:  
   property ItemType MyProperty {  
      ItemType get() {  
         return myField;   
      }  
      void set(ItemType value) {  
         myField = value;  
      }  
   }  
};  
  
int main() {  
   MyClass<String^>^ c = gcnew MyClass<String^>();  
   MyClass<int>^ c1 = gcnew MyClass<int>();  
  
   c->MyProperty = "John";  
   c1->MyProperty = 234;  
  
   Console::Write("{0}, {1}", c->MyProperty, c1->MyProperty);  
}  
```  
  
  **John, 234**   
## Exemple  
 L'exemple suivant montre une classe générique avec un événement.  
  
```  
// generics_generic_with_event.cpp  
// compile with: /clr  
// Declare a generic class with an event and  
// invoke events.  
using namespace System;  
  
// declare delegates  
generic <typename ItemType>  
delegate void ClickEventHandler(ItemType);  
  
// generic class that defines events  
generic <typename ItemType>  
ref class EventSource {  
public:  
   // declare the event OnClick  
   event ClickEventHandler<ItemType>^ OnClick;   
   void FireEvents(ItemType item) {  
      // raises events  
      OnClick(item);  
   }  
};  
  
// generic class that defines methods that will called when  
// event occurs  
generic <typename ItemType>  
ref class EventReceiver {  
public:  
   void OnMyClick(ItemType item) {  
     Console::WriteLine("OnClick: {0}", item);  
   }  
};  
  
int main() {  
   EventSource<String^>^ MyEventSourceString =  
                   gcnew EventSource<String^>();  
   EventSource<int>^ MyEventSourceInt = gcnew EventSource<int>();  
   EventReceiver<String^>^ MyEventReceiverString =  
                   gcnew EventReceiver<String^>();  
   EventReceiver<int>^ MyEventReceiverInt = gcnew EventReceiver<int>();  
  
   // hook handler to event  
   MyEventSourceString->OnClick += gcnew ClickEventHandler<String^>(  
       MyEventReceiverString, &EventReceiver<String^>::OnMyClick);  
   MyEventSourceInt->OnClick += gcnew ClickEventHandler<int>(  
             MyEventReceiverInt, &EventReceiver<int>::OnMyClick);  
  
   // invoke events  
   MyEventSourceString->FireEvents("Hello");  
   MyEventSourceInt->FireEvents(112);  
  
   // unhook handler to event  
   MyEventSourceString->OnClick -= gcnew ClickEventHandler<String^>(  
        MyEventReceiverString, &EventReceiver<String^>::OnMyClick);  
   MyEventSourceInt->OnClick -= gcnew ClickEventHandler<int>(  
        MyEventReceiverInt, &EventReceiver<int>::OnMyClick);  
}  
```  
  
## Generic Structs  
 Les règles pour déclarer et utiliser les structs génériques sont les mêmes que celles pour les classes génériques, à l'exception de les différences indiquées dans Visual C\+\+ référence du langage.  
  
## Exemple  
 L'exemple suivant déclare une structure générique, `MyGenStruct`, avec un champ, `myField`, et lui assigner des valeurs de types différents \(`int`, **double**, **String^**\) à ce champ.  
  
```  
// generics_generic_struct1.cpp  
// compile with: /clr  
using namespace System;  
  
generic <typename ItemType>  
ref struct MyGenStruct {  
public:  
   ItemType myField;  
  
   ItemType AssignValue(ItemType item) {  
      myField = item;  
      return myField;  
   }  
};  
  
int main() {  
   int myInt = 123;  
   MyGenStruct<int>^ myIntObj = gcnew MyGenStruct<int>();  
   myIntObj->AssignValue(myInt);  
   Console::WriteLine("The field is assigned the integer value: {0}",  
            myIntObj->myField);  
  
   double myDouble = 0.123;  
   MyGenStruct<double>^ myDoubleObj = gcnew MyGenStruct<double>();  
   myDoubleObj->AssignValue(myDouble);  
   Console::WriteLine("The field is assigned the double value: {0}",  
            myDoubleObj->myField);  
  
   String^ myString = "Hello Generics!";  
   MyGenStruct<String^>^ myStringObj = gcnew MyGenStruct<String^>();  
   myStringObj->AssignValue(myString);  
   Console::WriteLine("The field is assigned the string: {0}",  
            myStringObj->myField);  
}  
```  
  
  **On attribut au champs la valeur entière: 123**  
**Le champ est affecté la valeur double : 0,123**  
**Le champ est affecté la chaîne : Hello génériques \!**   
## Voir aussi  
 [Generics](../windows/generics-cpp-component-extensions.md)