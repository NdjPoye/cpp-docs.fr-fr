---
title: "Overview of Generics in Visual C++ | Microsoft Docs"
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
  - "generics [C++], about generics"
  - "default initializers [C++]"
  - "type parameters [C++]"
  - "constructed types"
  - "type arguments [C++]"
  - "constructed types, open [C++]"
  - "open constructed types [C++]"
  - "constructed types, closed [C++]"
ms.assetid: 21f10637-0fce-4916-b925-6c86a126d3aa
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Overview of Generics in Visual C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les génériques sont des types paramétrables pris en charge par le CLR.  Un type paramétrable est un type est défini à un paramètre de type inconnu spécifié lorsque le générique est utilisé.  
  
## Pourquoi génériques ?  
 Prend en charge des modèles C\+\+ et les modèles et les génériques prennent en charge les types paramétrables pour créer les classes de collection de type.  Toutefois, les modèles fournissent le paramétrage de compilation.  Vous ne pouvez pas référencer un assembly contenant la définition du modèle et créer de nouvelles spécialisations du modèle.  Une fois compilé, un template spécialisé ressemble à n'importe quelle classe ou méthode.  En revanche, les génériques sont émis dans le langage MSIL en tant que type paramètré connus par le runtime pour être un type paramétré ; code source faisant référence à un assembly qui contient un type générique peut créer des spécialisations du type générique.  Pour plus d'informations sur la comparaison des modèles et les génériques Visual C\+\+, consultez [Generics and Templates \(Visual C\+\+\)](../windows/generics-and-templates-visual-cpp.md).  
  
## Types et fonctions génériques  
 Les types de classe, à condition que ils sont des types managés, peuvent être génériques.  Un exemple de ce peut être une classe `List`.  Le type d'un objet dans la liste est le paramètre de type.  Si vous aviez besoin d'une classe `List` pour différents types d'objets, avant que les génériques vous pourriez avoir utilisé `List` qui prend **System::Object** comme type d'élément.  Mais cela permettrait un objet objets \(y compris du type incorrect\) à utiliser dans la liste.  Une telle liste est appelée une classe de collection non typée.  Au mieux, vous pouvez vérifier le type au moment de l'exécution et lever d'exception.  Ou, vous pouvez avoir utilisé un modèle, qui perdrait sa qualité générique une fois compilé dans un assembly.  Les consommateurs de votre assembly ne peuvent pas créer leurs propres spécialisations du modèle.  Les génériques vous permettent de créer des classes de collection de type, disons `List<int>` \(lecture en tant que « liste int »\) et `List<double>` \(«liste de double »\) qui génèrent une erreur de compilation si vous essayer de mettre un type à la collection n'a pas été conçue pour recevoir dans la collection non typée.  En outre, ces types sont génériques une fois qu'ils sont compilées.  
  
 Une description de la syntaxe des classes génériques figure dans le nouvel espace de noms de [Generic Classes \(C\+\+\/CLI\)](../windows/generic-classes-cpp-cli.md)`.` A, <xref:System.Collections.Generic>, propose un ensemble de types de collections paramétrables et <xref:System.Collections.Generic.Dictionary%602>, <xref:System.Collections.Generic.List%601> et <xref:System.Collections.Generic.LinkedList%601>.  Pour plus d'informations, consultez [Génériques dans la bibliothèque de classes .NET Framework](../Topic/Generics%20in%20the%20.NET%20Framework%20Class%20Library%20\(C%23%20Programming%20Guide\).md).  
  
 Les fonctions membres d'instance et de classe statique, les délégués, et les fonctions globales peuvent également être génériques.  Les fonctions génériques peuvent être nécessaires si les paramètres de la fonction sont d'un type inconnu, ou si la fonction elle\-même doit utiliser les types génériques.  Dans de nombreux cas où **System::Object** a peut\-être été utilisé dans le passé comme paramètre pour un type d'objet inconnu, un paramètre de type générique peut être utilisé à la place, en tenant compte de le code de type sécurisé.  Toute tentative de transmission d'un type pour lequel la fonction n'a pas été conçue est marquée comme une erreur de compilation.  Utiliser **System::Object** comme paramètre de fonction, le passage discret d'un objet dont la fonction n'a pas été pas conçue pour ne serait pas détecté, et vous devez convertir le type d'objet inconnu vers un spécifique pour capturer le corps de la fonction, et explique la probabilité d'une InvalidCastException.  Avec un code générique, la tentative de transmission d'un objet à la fonction provoquerait un conflit de type afin que le corps de la fonction soit garanti d'être du type approprié.  
  
 Les mêmes avantages s'appliquent aux classes de collection basées sur les génériques.  Les classes de collection dans le passé emploieraient **System::Object** pour stocker les éléments d'une collection.  L'insertion des objets d'un type dont la collection n'a pas été conçue pour n'a pas été marquée au moment de la compilation, et pas souvent même si les objets ont été insérés.  Habituellement, un objet est converti en un autre type lorsqu'il accède à la collection.  Uniquement lorsque la conversion a échoué le type inattendu est détecté.  Les génériques résolvent ce problème au moment de la compilation en détectant tout code qui insère un type qui ne correspond pas \(ou la conversion implicite\) le paramètre de type de la collection générique.  
  
 Pour obtenir une description de la syntaxe, consultez [Generic Functions \(C\+\+\/CLI\)](../windows/generic-functions-cpp-cli.md).  
  
## Terminologie utilisée avec des caractères génériques  
  
##### Paramètres de type  
 Une déclaration générique contient un ou plusieurs types inconnus, connus comme *paramètres de types*.  Les paramètreq de type ont un nom qui représente le type dans le corps de la déclaration générique.  Le nom de paramètre de type est utilisé comme type dans le corps de la déclaration générique.  La déclaration générique pour List\<T\> contient le paramètre de type T.  
  
##### Arguments de Type  
 *L'argument de type* est le type réel utilisé à la place du paramètre de type lorsque le générique est spécialisé pour un type spécifique ou types.  Par exemple, `int` esr l'argument de type dans `List<int>`.  Les types de valeurs et les types de descripteur sont les seuls types autorisés dans un argument du type générique.  
  
##### Type Construit  
 Un type construit d'un type générique s'appelle un *Type construit*.  Type pas entièrement précisé, par exemple `List<T>` est *un type construit ouvert*; type entièrement précisé, par exemple `List<double>,` est *un type construit fermé* ou *type spécial*.  Les types construits ouverts peut être utilisé dans la définition d'autres types ou des méthodes génériques et ne peuvent pas être spécifié tant que le générique englobant lui\-même est spécifié.  Par exemple, voici une utilisation d'un type construit ouvert en tant que classe de base pour un générique :  
  
 `// generics_overview.cpp`  
  
 `// compile with: /clr /c`  
  
 `generic <typename T>`  
  
 `ref class List {};`  
  
 `generic <typename T>`  
  
 `ref class Queue : public List<T> {};`  
  
##### Contrainte  
 Une contrainte est une restriction aux types qui peuvent être utilisés en tant que paramètre de type.  Par exemple, une classe générique donnée peut recevoir uniquement les classes qui héritent d'une classe spécifiée, ou implémentent une interface spécifiée.  Pour plus d'informations, consultez [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
## Types Référence et types Valeur  
 Les handles types et des types de valeurs peuvent être utilisés comme arguments de type.  Dans la définition générique, dans laquelle l'un ou l'autre de type peut être utilisé, la syntaxe est l'un des types référence.  Par exemple, l'opérateur de **\-\>** est utilisé pour accéder à des membres du type du paramètre de type si le type par la suite utilisé est un type de référence ou un type de valeur.  Lorsqu'un type de valeur est utilisée comme argument de type, l'exécution du code qui utilise les types de valeurs directement sans la casse dans la boîte les types de valeur.  
  
 Lorsque vous utilisez un type référent comme argument de type générique, utilisez la syntaxe de descripteur.  Lors de l'utilisation d'un type valeur à l'argument de type générique, utilisez le nom du type.  
  
 `// generics_overview_2.cpp`  
  
 `// compile with: /clr`  
  
 `generic <typename T>`  
  
 `ref class GenericType {};`  
  
 `ref class ReferenceType {};`  
  
 `value struct ValueType {};`  
  
 `int main() {`  
  
 `GenericType<ReferenceType^> x;`  
  
 `GenericType<ValueType> y;`  
  
 `}`  
  
## Paramètres de type  
 Les paramètres de type dans une classe générique sont traitées comme les autres identificateurs.  Toutefois, le type n'est pas connu, il existe des restrictions sur leur utilisation.  Par exemple, vous ne pouvez pas utiliser les membres et les méthodes de type de fichier à moins que le paramètre de type connu pour prendre en charge ces membres.  Autrement dit, pour accéder à un membre par le paramètre de type, vous devez ajouter le type qui contient le membre à la liste de contraintes du paramètre de type.  
  
 `// generics_overview_3.cpp`  
  
 `// compile with: /clr`  
  
```  
interface class I {  
   void f1();  
   void f2();  
};  
  
ref struct R : public I {  
   virtual void f1() {}  
   virtual void f2() {}   
   virtual void f3() {}   
};  
  
generic <typename T>  
where T : I  
void f(T t) {  
   t->f1();  
   t->f2();  
   safe_cast<R^>(t)->f3();  
}  
  
int main() {  
   f(gcnew R());  
}  
```  
  
 Ces restrictions s'appliquent aux opérateurs également.  Un paramètre de type générique sans contrainte ne peut pas utiliser les opérateurs `==` et `!=` pour comparer deux instances du type, au cas où le type ne prendrait pas en charge ces opérateurs.  Ces contrôles sont nécessaires pour les génériques, mais pas pour les modèles, car les génériques peuvent être spécialisés pendant l'exécution avec n'importe quelle classe qui suit les contraintes, lorsqu'elle est trop tardive pour vérifier l'utilisation de membres valides.  
  
 Une instance par défaut du paramètre de type peut être créée à l'aide de l'opérateur `()`.  Par exemple :  
  
 `T t = T();`  
  
 où `T` est un paramètre de type dans une classe ou une définition de méthode générique, initialise la variable la valeur par défaut.  Si `T` est une classe de référence il s'agit d'un pointeur null ; si `T` est une classe de valeur, l'objet est initialisé à zéro.  Cela s'appelle *un initialiseur par défaut*.  
  
## Voir aussi  
 [Generics](../windows/generics-cpp-component-extensions.md)