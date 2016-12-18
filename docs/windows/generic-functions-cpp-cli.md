---
title: "Generic Functions (C++/CLI) | Microsoft Docs"
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
  - "functions [C++], generic"
  - "generic methods"
  - "generics [C++], functions"
  - "methods [C++], generic"
  - "generic functions"
ms.assetid: 8e409364-58f9-4360-b486-e7d555e0c218
caps.latest.revision: 21
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Generic Functions (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une fonction générique est une fonction non déclaré avec des paramètres de type.  Lorsqu'elle est appelée, les types réels sont utilisés à la place des paramètres de type.  
  
## Toutes les plateformes  
 **Remarques**  
  
 Cette fonctionnalité ne s'applique pas à toutes les plateformes.  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 **Remarques**  
  
 Cette fonctionnalité n'est pas prise en charge danq [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)].  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 Une fonction générique est une fonction non déclaré avec des paramètres de type.  Lorsqu'elle est appelée, les types réels sont utilisés à la place des paramètres de type.  
  
 **Syntaxe**  
  
```  
[attributes] [modifiers]  
return-type identifier <type-parameter identifier(s)>  
[type-parameter-constraints clauses]  
  
([formal-parameters])  
{  
   function-body  
}  
```  
  
 **Paramètres**  
  
 *attributes* \(facultatif\)  
 Les informations supplémentaires déclarative.  Pour plus d'informations sur les attributs et les classes d'attributs, consultez la section attributs.  
  
 *modifiers* \(facultatif\)  
 Un modificateur de la fonction, comme Static.  `virtual` n'est pas autorisée puisque les méthodes virtuels peuvent ne pas être génériques.  
  
 *return\-type*  
 Type retourné par la méthode.  Si le type de retour est vide, aucune valeur de retour n'est requise.  
  
 *identifier*  
 le nom de la fonction ;  
  
 *type\-parameter identifier\(s\)*  
 Liste séparée par des virgules des identificateurs.  
  
 *formal\-parameters* \(facultatif\)  
 Liste de paramètres.  
  
 *type\-parameter\-constraints\-clauses*  
 Ceci permet de spécifier des restrictions concernant les types qui peuvent être utilisés comme arguments de type, et le format spécifié dans [Constraints on Generic Type Parameters \(C\+\+\/CLI\)](../windows/constraints-on-generic-type-parameters-cpp-cli.md).  
  
 *function\-body*  
 Le corps de la méthode, qui peut faire référence aux identificateurs de type.  
  
 **Remarques**  
  
 Les fonctions génériques sont des fonctions déclarées avec un paramètre de type générique.  Elles peuvent être des méthodes d'une classe ou une structure, ou des fonctions autonomes.  Une seule déclaration générique déclare implicitement une famille de fonctions qui ne diffèrent que par la substitution de type réel différent pour le paramètre de type générique.  
  
 Dans [!INCLUDE[vcprvc](../build/includes/vcprvc_md.md)], la classe ou les constructeurs de structure ne peut être déclaré avec des paramètres du type générique.  
  
 Lorsqu'il est appelé, le paramètre de type générique est remplacé par un type réel.  Le type réel peut être défini explicitement entre chevrons à l'aide de la syntaxe similaire à un appel de fonction du modèle.  Si elle est appelée sans paramètres de type, le compilateur tente de déduire le type réel des paramètres fournis dans l'appel de fonction.  Si l'argument de type prévu ne peut pas être déduit des paramètres utilisés, le compilateur signale une erreur.  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple de code suivant illustre une fonction générique.  
  
```  
// generics_generic_function_1.cpp  
// compile with: /clr  
generic <typename ItemType>  
void G(int i) {}  
  
ref struct A {  
   generic <typename ItemType>  
   void G(ItemType) {}  
  
   generic <typename ItemType>  
   static void H(int i) {}  
};  
  
int main() {  
   A myObject;  
  
   // generic function call  
   myObject.G<int>(10);  
  
   // generic function call with type parameters deduced  
   myObject.G(10);  
  
   // static generic function call  
   A::H<int>(10);  
  
   // global generic function call  
   G<int>(10);  
}  
```  
  
 **Exemple**  
  
 Les fonctions génériques peuvent être surchargées sur la signature ou l'arity, le nombre de paramètres de type dans une fonction.  En outre, les fonctions génériques peuvent être surchargées avec des fonctions génériques du même nom, à condition que les fonctions diffèrent dans certains paramètres de type.  Par exemple, les fonctions suivantes peuvent maintenant être surchargées:  
  
```  
// generics_generic_function_2.cpp  
// compile with: /clr /c  
ref struct MyClass {  
   void MyMythod(int i) {}  
  
   generic <class T>   
   void MyMythod(int i) {}  
  
   generic <class T, class V>   
   void MyMythod(int i) {}  
};  
```  
  
 **Exemple**  
  
 L'exemple suivant utilise une fonction générique pour trouver le premier élément dans un tableau.  Il déclare `MyClass`, qui hérite de la classe de base `MyBaseClass`.  `MyClass` contient une fonction générique, `MyFunction`, qui appelle une autre fonction générique, `MyBaseClassFunction`, dans la classe de base.  Dans **main**, la fonction générique, `MyFunction`, est appelée en utilisant des arguments de type.  
  
```  
// generics_generic_function_3.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyBaseClass {  
protected:  
   generic <class ItemType>  
   ItemType MyBaseClassFunction(ItemType item) {  
      return item;  
   }  
};  
  
ref class MyClass: public MyBaseClass {  
public:  
   generic <class ItemType>  
   ItemType MyFunction(ItemType item) {  
      return MyBaseClass::MyBaseClassFunction<ItemType>(item);  
   }  
};  
  
int main() {  
   MyClass^ myObj = gcnew MyClass();  
  
   // Call MyFunction using an int.  
   Console::WriteLine("My function returned an int: {0}",  
                           myObj->MyFunction<int>(2003));  
  
   // Call MyFunction using a string.  
   Console::WriteLine("My function returned a string: {0}",  
   myObj->MyFunction<String^>("Hello generic functions!"));  
}  
```  
  
 **Sortie**  
  
  **Ma fonction a renvoyé un entier : 2003**  
 **Ma fonction renvoyait une chaîne : Hello fonctions génériques\!**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)   
 [Generics](../windows/generics-cpp-component-extensions.md)