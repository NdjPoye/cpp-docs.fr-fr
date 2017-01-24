---
title: "Constraints on Generic Type Parameters (C++/CLI) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "where"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "where keyword [C++]"
  - "constraints, C++"
ms.assetid: eb828cc9-684f-48a3-a898-b327700c0a63
caps.latest.revision: 25
caps.handback.revision: 23
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Constraints on Generic Type Parameters (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans le type générique ou les déclarations de méthode, vous pouvez qualifier un paramètre de type avec des contraintes.  Une contrainte est une condition que les types utilisés comme arguments de type doivent respecter.  Par exemple, une contrainte peut indiquer que l'argument de type doit implémenter certaines interface ou l'hériter d'une classe spécifique.  
  
 Les contraintes sont facultatives ; ne pas spécifier une contrainte sur un paramètre revient à limiter ce paramètre à <xref:System.Object>.  
  
## Syntaxe  
  
```  
  
where type-parameter: constraint list  
```  
  
#### Paramètres  
 *Paramètre de type*  
 Un des paramètres de type, être contraint.  
  
 *liste de contraintes*  
 *liste de contraintes* est une liste séparée par des virgules des caractéristiques de contrainte.  La liste peut inclure des interfaces à implémenter par le paramètre de type.  
  
 La liste peut également inclure une classe.  Pour que l'argument de type satisfasse une contrainte de classe de base, il doit être de la même classe que la contrainte ou dériver de la contrainte.  
  
 Vous pouvez également spécifier `gcnew()` pour indiquer l'argument de type doit disposer d'un constructeur public sans paramètre ; ou `ref class` pour indiquer l'argument de type doit être un type référence, y compris tout classe, interface, délégué, ou tableau ; ou `value class` pour indiquer que l'argument de type doit être un type de valeur.  Tout type valeur, excepté Nullable\<T\>, peut être spécifié.  
  
 Vous pouvez également spécifier un paramètre générique en tant que contrainte.  L'argument de type disponible pour le type que vous contraignez doit être ou être dérivé du type de la contrainte.  Cela s'appelle une contrainte de type naked.  
  
## Notes  
 La clause de contrainte consiste en **where** suivi d'un paramètre de type, d'un signe deux\-points \(**:**\), ainsi que la contrainte, qui indique la nature de la restriction au paramètre de type.  **where** est un mot clé contextuel ; consultez [Mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md) pour plus d'informations.  Plusieurs clauses de **where** séparées par un espace.  
  
 Les contraintes sont appliquées aux paramètres de type pour placer des restrictions sur les types d'éléments qui peuvent être utilisés comme arguments pour un type ou une méthode générique.  
  
 La classe et les contraintes d'interface spécifient les types d'argument qui doivent être de type ou hériter d'une classe spécifiée ou implémenter une interface spécifiée.  
  
 L'application des contraintes à un type ou une méthode générique permet au code de ce type ou de cette méthode de tirer parti des fonctionnalités des contraintes.  Vous pouvez, par exemple, déclarer une classe générique, telle que le paramètre de type implémente l'interface **IComparable\<T\>** :  
  
```  
// generics_constraints_1.cpp  
// compile with: /c /clr  
using namespace System;  
generic <typename T>  
where T : IComparable<T>  
ref class List {};  
```  
  
 Cette contrainte exige qu'un argument de type utilisé pour `T` implémente `IComparable<T>` au moment de la compilation.  Il permet également aux méthodes de l'interface, telles que **CompareTo**, a être appelé.  Aucune conversion n'est nécessaire sur une instance du paramètre de type pour appeler des méthodes de l'interface.  
  
 Les méthodes statiques dans la classe de l'argument de type ne peuvent pas être appelées par le paramètre de type ; elle peut être appelée uniquement par le type nommé réel.  
  
 Une contrainte ne peut pas être un type de valeur, y compris les types intégrés tels que `int` ou **double**.  Les types de valeurs ne peuvent pas être dérivé des classes, seule la classe peut jamais satisfaire la contrainte.  Dans ce cas, le générique peut être réécrites avec le paramètre de type remplacé par le type de valeur spécifique.  
  
 Les contraintes sont requises dans certains cas puique le compilateur ne permet pas l'utilisation des méthodes ou d'autres fonctionnalités d'un type inconnu à moins que les contraintes impliquent que le type inconnu prend en charge les méthodes ou des interfaces.  
  
 Plusieurs contraintes pour le même paramètre de type peuvent être spécifiées dans une liste séparée par des virgules  
  
```  
// generics_constraints_2.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
generic <typename T>  
where T : List<T>, IComparable<T>  
ref class List {};  
```  
  
 Avec plusieurs paramètres de type, utilisez une clause **where** pour chaque paramètre de type.  Par exemple :  
  
```  
// generics_constraints_3.cpp  
// compile with: /c /clr  
using namespace System;  
using namespace System::Collections::Generic;  
  
generic <typename K, typename V>  
   where K: IComparable<K>  
   where V: IComparable<K>  
ref class Dictionary {};  
```  
  
 Pour résumer, utiliser des contraintes dans votre code en fonction de les règles suivantes :  
  
-   Si plusieurs contraintes sont répertoriées, les contraintes indiquées dans un ordre quelconque.  
  
-   Les contraintes peuvent également être des types de classe, tels que les classes de base abstraites.  Toutefois, les contraintes ne peuvent pas être des types de valeurs ou des sealed.  
  
-   Les contraintes ne peuvent pas elles\-mêmes être des paramètres de type, mais elles peuvent impliquer les paramètres de type dans un type construit ouvert.  Par exemple :  
  
    ```  
    // generics_constraints_4.cpp  
    // compile with: /c /clr  
    generic <typename T>  
    ref class G1 {};  
  
    generic <typename Type1, typename Type2>  
    where Type1 : G1<Type2>   // OK, G1 takes one type parameter  
    ref class G2{};  
    ```  
  
## Exemple  
 L'exemple suivant illustre l'utilisation de contraintes pour appeler des méthodes d'instance des paramètres de type.  
  
```  
// generics_constraints_5.cpp  
// compile with: /clr  
using namespace System;  
  
interface class IAge {  
   int Age();  
};  
  
ref class MyClass {  
public:  
   generic <class ItemType> where ItemType : IAge   
   bool isSenior(ItemType item) {  
      // Because of the constraint,  
      // the Age method can be called on ItemType.  
      if (item->Age() >= 65)   
         return true;  
      else  
         return false;  
   }  
};  
  
ref class Senior : IAge {  
public:  
   virtual int Age() {  
      return 70;  
   }  
};  
  
ref class Adult: IAge {  
public:  
   virtual int Age() {  
      return 30;  
   }  
};  
  
int main() {  
   MyClass^ ageGuess = gcnew MyClass();  
   Adult^ parent = gcnew Adult();  
   Senior^ grandfather = gcnew Senior();  
  
   if (ageGuess->isSenior<Adult^>(parent))  
      Console::WriteLine("\"parent\" is a senior");  
   else  
      Console::WriteLine("\"parent\" is not a senior");  
  
   if (ageGuess->isSenior<Senior^>(grandfather))  
      Console::WriteLine("\"grandfather\" is a senior");  
   else  
      Console::WriteLine("\"grandfather\" is not a senior");  
}  
```  
  
  **« parent » n'est pas un aîné**  
**« grand\-père » est un aîné**   
## Exemple  
 Lorsqu'un paramètre de type générique est utilisé comme contrainte, elles constituent une contrainte de type naked.  Les contraintes de type naked sont utiles lorsqu'une fonction membre avec son propre paramètre de type doit limiter ce paramètre au paramètre de type contenant le type.  
  
 Dans l'exemple suivant, T est une contrainte de type naked dans le contexte de la méthode add.  
  
 Les contraintes de type naked peuvent également être utilisés dans les définitions de classes génériques.  L'utilité de contraintes de type naked avec les classes génériques est très limitée, car le compilateur ne peut rien deviner à propos des contraintes de types naked en dehors du fait qu'elle dérive de <xref:System.Object>.  Utilisez des contraintes de type naked sur les classes génériques dans lesquels vous souhaitez mettre en application une relation d'héritage entre deux paramètres de type.  
  
```  
// generics_constraints_6.cpp  
// compile with: /clr /c  
generic <class T>  
ref struct List {  
   generic <class U>  
   where U : T  
   void Add(List<U> items)  {}  
};  
  
generic <class A, class B, class C>  
where A : C  
ref struct SampleClass {};  
```  
  
## Voir aussi  
 [Generics](../windows/generics-cpp-component-extensions.md)