---
title: "Classes de valeur et structures de valeur (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "12/30/2016"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
helpviewer_keywords: 
  - "value struct"
  - "value class"
ms.assetid: 262a0992-9721-4c02-8297-efc07d90e5a4
caps.latest.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 12
---
# Classes de valeur et structures de valeur (C++/CX)
Un *struct value* ou une *classe value* est une structure POD \(Plain Old Data\) compatible [!INCLUDE[wrt](../cppcx/includes/wrt-md.md)]. Elle a une taille fixe et se compose uniquement de champs ; contrairement à une classe ref, elle ne possède aucune propriété.  
  
 Les exemples suivants montrent comment déclarer et initialiser des structs value.  
  
```  
  
// in mainpage.xaml.h: value struct TestStruct { Platform::String^ str; int i; }; value struct TestStruct2 { TestStruct ts; Platform::String^ str; int i; }; // in mainpage.cpp: // Initialize a value struct with an int and String TestStruct ts = {"I am a TestStruct", 1}; // Initialize a value struct that contains // another value struct, an int and a String TestStruct2 ts2 = {{"I am a TestStruct", 1}, "I am a TestStruct2", 2}; // Initialize value struct members individually. TestStruct ts3; ts3.i = 108; ts3.str = "Another way to init a value struct.";  
  
```  
  
 Lorsque la variable d'un type valeur est assignée à une autre variable, la valeur est copiée, afin que chacune des deux variables ait sa propre copie des données. Un *struct value* est une structure de taille fixe qui contient uniquement des champs de données publics et sont déclarés à l'aide du mot clé `value struct`.  
  
 Une *classe value* est comparable à un `value struct` sauf que ses champs doivent avoir une accessibilité publique explicitement spécifiée. Elle est déclarée à l'aide du mot clé `value class`.  
  
 Un struct value ou une classe value ne peut contenir comme champs que des types numériques fondamentaux, des classes enum, `Platform::String^` ou [Platform::IBox \<T\>^](../cppcx/platform-ibox-interface.md), où T est un type numérique, une classe enum, une class value ou un struct value. Un champ `IBox<T>^` peut avoir une valeur `nullptr`. C'est la façon dont C\+\+ implémente le concept de *types valeur Nullable*.  
  
 Une classe value ou un struct value qui contient un type `Platform::String^` ou `IBox<T>^` comme membre n'est pas utilisable avec `memcpy`.  
  
 Étant donné que tous les membres d'un `value class` ou d'un `value struct` sont publics et sont émis vers des métadonnées, les types C\+\+ standard ne sont pas autorisés comme membres. Ils diffèrent des classes ref, qui peuvent contenir les types C\+\+ standard `private` ou `internal`.  
  
 Le fragment de code suivant déclare les types `Coordinates` et `City` comme structs value. Notez que l'un des membres de données `City` est un type `GeoCoordinates`. Un `value struct` peut contenir d'autres structs value comme membres.  
  
 [!code-cpp[cx_classes#07](../snippets/cpp/VS_Snippets_Misc/cx_classes/cpp/class1.h#07)]  
  
## Passage de paramètres pour les types valeur  
 Si vous avez un type valeur comme paramètre de fonction ou de méthode, il est normalement passé par valeur. Pour les objets plus grands, cela peut provoquer un problème de performances. Dans Visual Studio 2013 et versions antérieures, les types valeur dans C\+\+\/CX étaient toujours passés par valeur. Dans Visual Studio 2015 et versions ultérieures, vous pouvez passer des types valeur par référence ou par valeur.  
  
 Pour déclarer un paramètre qui passe un type valeur par valeur, utilisez du code semblable au suivant :  
  
```  
void Method1(MyValueType obj);  
```  
  
 Pour déclarer un paramètre qui passe un type valeur par référence, utilisez le symbole de référence \(&\), comme suit :  
  
```  
void Method2(MyValueType& obj);  
```  
  
 Le type dans Method2 est une référence à MyValueType. Il fonctionne de la même façon qu’un type référence en C\+\+ standard.  
  
 Quand vous appelez Method1 à partir d’un autre langage, tel que C\#, vous n’avez pas besoin d’utiliser le mot clé `ref` ou `out`. Quand vous appelez Method2, utilisez le mot clé `ref`.  
  
```  
Method2(ref obj);  
```  
  
 Vous pouvez également utiliser un symbole de pointeur \(\*\) pour passer un type valeur par référence. Le comportement par rapport aux appelants dans d’autres langages est identique \(les appelants en C\# utilisent le mot clé `ref`\), mais dans la méthode, le type est un pointeur vers le type valeur.  
  
## Types valeur Nullable  
 Comme indiqué précédemment, une classe value ou un struct value peut avoir un champ de type [Platform::IBox\<T\>^](../cppcx/platform-ibox-interface.md), par exemple `IBox<int>^`. Ce champ peut avoir n'importe quelle valeur numérique valide pour le type `int` ou une valeur `nullptr`. Vous pouvez passer un champ Nullable en tant qu'argument à une méthode dont le paramètre est déclaré comme facultatif, ou à tout emplacement où un type valeur n'est pas obligatoire pour l'obtention d'une valeur.  
  
 L'exemple suivant montre comment initialiser un struct qui a un champ Nullable.  
  
```  
public value struct Student { Platform::String^ Name; int EnrollmentYear; Platform::IBox<int>^ GraduationYear; // Null if not yet graduated. }; //To create a Student struct, one must populate the nullable type. MainPage::MainPage() { InitializeComponent(); Student A; A.Name = "Alice"; A.EnrollmentYear = 2008; A.GraduationYear = ref new Platform::Box<int>(2012); Student B; B.Name = "Bob"; B.EnrollmentYear = 2011; B.GraduationYear = nullptr; IsCurrentlyEnrolled(A); IsCurrentlyEnrolled(B); } bool MainPage::IsCurrentlyEnrolled(Student s) { if (s.GraduationYear == nullptr) { return true; } return false; }  
  
```  
  
 Un struct value lui\-même peut être rendu Nullable de la même manière, comme il est montré ici :  
  
```  
  
public value struct MyStruct { public: int i; Platform::String^ s; }; public ref class MyClass sealed { public: property Platform::IBox<MyStruct>^ myNullableStruct; };  
```  
  
## Voir aussi  
 [Système de type \(C\+\+\/CX\)](../cppcx/type-system-c-cx.md)   
 [Référence du langage Visual C\+\+](../cppcx/visual-c-language-reference-c-cx.md)   
 [Référence aux espaces de noms](../cppcx/namespaces-reference-c-cx.md)   
 [Classes et structures de référence \(C\+\+\/CX\)](../cppcx/ref-classes-and-structs-c-cx.md)