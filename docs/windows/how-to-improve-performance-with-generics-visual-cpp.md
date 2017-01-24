---
title: "How to: Improve Performance with Generics (Visual C++) | Microsoft Docs"
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
  - "performance, C++"
  - "Visual C++, performance"
  - "Visual C++, generics"
  - "generics [C++], performance"
ms.assetid: f14a175b-301f-46cc-86e4-c82d35f9aa3e
caps.latest.revision: 7
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# How to: Improve Performance with Generics (Visual C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Avec les génériques, vous pouvez créer du code réutilisable en fonction d'un paramètre de type.  Le type réel du type de paramètre est différé jusqu'à ce qu'il soit appelé par le code client.  Pour plus d'informations sur les types génériques, consultez [Generics](../windows/generics-cpp-component-extensions.md).  
  
 Cet article discutera comment les génériques peuvent aider à améliorer les performances d'une application qui utilise des collections.  
  
## Exemple  
 Le Framework .NET est fourni avec de nombreuses classes de collection dans l'espace de noms <xref:System.Collections?displayProperty=fullName>.  La plupart de ces collections traitent des objets de type <xref:System.Object?displayProperty=fullName>.  Cela permet aux collections d'enregistrer tout type, puisque tous les types dans .NET Framework, même les types de valeur, dérivent de <xref:System.Object?displayProperty=fullName>.  Toutefois, il existe deux inconvénients à cette méthode.  
  
 D'abord, si la collection contient des types de valeur élevée tels que des entiers, la valeur doit être enfermée dans la boîte avant d'être ajouté à la collection et unboxed lorsque la valeur est récupérée depuis la collection.  Ce sont des opérations coûteuses.  
  
 Ensuite, il n'existe aucune méthode pour contrôler quels types peuvent être ajouté à une collection.  Il est parfaitement légale d'ajouter un entier et une chaîne à cette collection, même si ce n'est probablement pas ce qui est attendu.  Par conséquent, pour que votre code soit sûr, vous devez vérifier que le type récupéré de la collection est réellement celui qui était attendu.  
  
 L'exemple de code suivant montre les deux inconvénients majeurs des collections de .NET Framework avant les génériques.  
  
```  
// perf_pre_generics.cpp  
// compile with: /clr  
  
using namespace System;  
using namespace System::Collections;  
  
int main()  
{  
    // This Stack can contain any type.  
    Stack ^s = gcnew Stack();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
  
    // Push a String to the same Stack.  
    // The Stack now contains two different data types.  
    s->Push("Seven");  
  
    // Pop the items off the Stack.  
    // The item is returned as an Object, so a cast is  
    // necessary to convert it to its proper type.  
    while (s->Count > 0)  
    {  
        Object ^o = s->Pop();  
        if (o->GetType() == Type::GetType("System.String"))  
        {  
            Console::WriteLine("Popped a String: {0}", (String ^)o);  
        }  
        else if (o->GetType() == Type::GetType("System.Int32"))  
        {  
            Console::WriteLine("Popped an int: {0}", (int)o);  
        }  
        else  
        {  
            Console::WriteLine("Popped an unknown type!");  
        }  
    }  
}  
```  
  
  **A dépilé une chaîne : Sept**  
**A dépilé un entier : 7**   
## Exemple  
 Le nouvel espace de noms <xref:System.Collections.Generic?displayProperty=fullName> contient de nombreuses collections présentes dans l'espace de noms de <xref:System.Collections?displayProperty=fullName>, mais ont été modifiées pour accepter les paramètres du type générique.  Cela élimine les deux inconvénients des collections génériques : la conversion boxing et unboxing des types de valeurs et l'incapacité de spécifier les types de stockage dans les collections.  Les opérations sur les deux collections sont les mêmes ; elles diffèrent uniquement par la façon dont elles sont instanciées.  
  
 Comparez l'exemple écrit ci\-dessus avec cet exemple qui utilise une collection générique <xref:System.Collections.Generic.Stack%601>.  Sur les grandes collections qui sont fréquemment sollicitées, les performances de cet exemple sont très supérieure à l'exemple précédent.  
  
```  
// perf_post_generics.cpp  
// compile with: /clr  
  
#using <System.dll>  
  
using namespace System;  
using namespace System::Collections::Generic;  
  
int main()  
{  
    // This Stack can only contain integers.  
    Stack<int> ^s = gcnew Stack<int>();  
  
    // Push an integer to the Stack.  
    // A boxing operation is performed here.  
    s->Push(7);  
    s->Push(14);  
  
    // You can no longer push a String to the same Stack.  
    // This will result in compile time error C2664.  
    //s->Push("Seven");  
  
    // Pop an item off the Stack.  
    // The item is returned as the type of the collection, so no  
    // casting is necessary and no unboxing is performed for  
    // value types.  
    int i = s->Pop();  
    Console::WriteLine(i);  
  
    // You can no longer retrieve a String from the Stack.  
    // This will result in compile time error C2440.  
    //String ^str = s->Pop();  
}  
```  
  
  **14**   
## Voir aussi  
 [Generics](../windows/generics-cpp-component-extensions.md)