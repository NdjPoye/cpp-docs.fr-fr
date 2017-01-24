---
title: "delegate (extensions du composant&#160;C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "delegate_cpp"
  - "delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "delegate (mot clé C++)"
ms.assetid: 03caf23d-7873-4a23-9b34-becf42aaf429
caps.latest.revision: 26
caps.handback.revision: 24
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# delegate (extensions du composant&#160;C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déclare un type qui représente un pointeur fonction.  
  
## Tous les runtimes  
 [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)] et le Common Language Runtime prennent en charge les délégués.  
  
### Remarques  
 `delegate` est un mot clé contextuel.  Pour plus d'informations, consultez [Mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Pour détecter au moment de la compilation si un type est un délégué, utilisez le trait de type `__is_delegate()`.  Pour plus d'informations, consultez [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
## Windows Runtime  
 C\+\+\/CX prend en charge les délégués à l'aide de la syntaxe suivante.  
  
### Syntaxe  
  
```cpp  
  
access delegate return-type delegate-type-identifier ([ parameters ])  
```  
  
### Paramètres  
 *access*  
 \(facultatif\) Accessibilité du délégué, qui peut être `public` \(par défaut\) ou `private`.  Le prototype de fonction peut également être qualifié avec les mots clés `const` ou `volatile`.  
  
 *return\-type*  
 Type de retour du prototype de fonction.  
  
 *delegate\-type\-identifier*  
 Nom du type du délégué déclaré.  
  
 *parameters*  
 \(Facultatif\) Types et identificateurs du prototype de fonction.  
  
### Remarques  
 Utilisez *delegate\-type\-identifier* pour déclarer un événement avec le même prototype que le délégué.  Pour plus d'informations, consultez [Délégués \(C\+\+\/CX\)](../Topic/Delegates%20\(C++-CX\).md).  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 Le Common Language Runtime prend en charge les délégués avec la syntaxe suivante.  
  
### Syntaxe  
  
```cpp  
  
access delegate function_declaration  
```  
  
### Paramètres  
 *access*  
 \(facultatif\) L'accessibilité du délégué en dehors de l'assembly peut être publique et privée.  La valeur par défaut est Privé.  À l'intérieur d'une classe, un délégué peut avoir n'importe quelle accessibilité.  
  
 *function\_declaration*  
 Signature de la fonction qui peut être liée au délégué.  Le type de retour d'un délégué peut être tout type managé.  Pour des raisons d'interopérabilité, il est recommandé que le retour d'un délégué soit de type CLS.  
  
 Pour définir un délégué indépendant, le premier paramètre de *function\_declaration* doit être le type du pointeur `this` de l'objet.  Pour plus d'informations, consultez [Délégués indépendants](../misc/unbound-delegates.md).  
  
### Remarques  
 Les délégués sont multicast : le « pointeur fonction » peut être lié à une ou plusieurs méthodes dans une classe managée.  Le mot clé **délégué** définit un type délégué multicast avec une signature de méthode spécifique.  
  
 Un délégué peut également être lié à une méthode d'une classe Valeur, telle qu'une méthode statique.  
  
 Un délégué possède les caractéristiques suivantes :  
  
-   Elle hérite de **System::MulticastDelegate**.  
  
-   Il possède un constructeur qui accepte deux arguments : un pointeur vers une classe managée ou **NULL** \(dans le cas de liaison à une méthode statique\) et une méthode qualifiée complète de type spécifié.  
  
-   Elle possède une méthode appelée `Invoke`, dont la signature correspond à la signature déclarée du délégué.  
  
 Lorsqu'un délégué est appelé, ses fonctions sont appelées dans l'ordre dans lequel elles ont été attachées.  
  
 La valeur de retour d'un délégué est la valeur de retour de sa dernière fonction membre jointe.  
  
 Les délégués ne peuvent pas être surchargés.  
  
 Les délégués peuvent être liés ou indépendants.  
  
 Lorsque vous instanciez un délégué lié, le premier argument doit être une référence d'objet.  Le deuxième argument d'une instanciation de délégué doit être l'adresse d'une méthode d'un objet de classe managé, ou un pointeur vers une méthode d'un type valeur.   Le deuxième argument d'une instanciation de délégué doit nommer la méthode avec la syntaxe de portée de classe complète et appliquer l'opérateur address\-of.  
  
 Lorsque vous instanciez un délégué indépendant, le premier argument doit être l'adresse d'une méthode d'objet de classe managée, ou un pointeur vers une méthode d'un type valeur.   L'argument doit nommer la méthode avec la syntaxe de portée de classe complète et appliquer l'opérateur address\-of.  
  
 Lors de la création d'un délégué d'une fonction statique ou globale, un seul paramètre est requis : la fonction \(éventuellement, l'adresse de la fonction\).  
  
 Pour plus d'informations sur les délégués, consultez  
  
-   [Délégués indépendants](../misc/unbound-delegates.md)  
  
-   [Comment : définir et utiliser des délégués](../dotnet/how-to-define-and-use-delegates-cpp-cli.md)  
  
-   [Délégué à un membre d'une classe Value](../misc/how-to-associate-delegates-to-members-of-a-value-class.md)  
  
-   [Délégué à une fonction non managée](../misc/how-to-associate-delegates-to-unmanaged-functions.md)  
  
-   [Délégués composés](../misc/how-to-compose-delegates.md)  
  
-   [Comment : passer un délégué ^ à une fonction native qui attend un pointeur de fonction](../misc/how-to-pass-a-delegate-hat-to-a-native-function-expecting-a-function-pointer.md)  
  
-   [Generic Delegates \(Visual C\+\+\)](../windows/generic-delegates-visual-cpp.md)  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple suivant montre comment déclarer, initialiser et appeler des délégués.  
  
```cpp  
// mcppv2_delegate.cpp  
// compile with: /clr  
using namespace System;  
  
// declare a delegate  
public delegate void MyDel(int i);  
  
ref class A {  
public:  
   void func1(int i) {  
      Console::WriteLine("in func1 {0}", i);  
   }  
  
   void func2(int i) {  
      Console::WriteLine("in func2 {0}", i);  
   }  
  
   static void func3(int i) {  
      Console::WriteLine("in static func3 {0}", i);  
   }  
};  
  
int main () {  
   A ^ a = gcnew A;  
  
   // declare a delegate instance  
   MyDel^ DelInst;  
  
   // test if delegate is initialized  
   if (DelInst)  
      DelInst(7);  
  
   // assigning to delegate  
   DelInst = gcnew MyDel(a, &A::func1);  
  
   // invoke delegate  
   if (DelInst)  
      DelInst(8);  
  
   // add a function  
   DelInst += gcnew MyDel(a, &A::func2);  
  
   DelInst(9);  
  
   // remove a function  
   DelInst -= gcnew MyDel(a, &A::func1);  
  
   // invoke delegate with Invoke  
   DelInst->Invoke(10);  
  
   // make delegate to static function  
   MyDel ^ StaticDelInst = gcnew MyDel(&A::func3);  
   StaticDelInst(11);  
}  
```  
  
 **Sortie**  
  
  **dans func1 8**  
 **dans func1 9**  
 **dans func2 9**  
 **dans func2 10**  
 **dans func3 11 statique**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)