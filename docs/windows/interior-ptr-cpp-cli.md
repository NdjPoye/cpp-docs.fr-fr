---
title: "interior_ptr (C++/CLI) | Microsoft Docs"
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
  - "stdcli::language::interior_ptr"
  - "interior_ptr_cpp"
  - "interior_ptr"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interior_ptr keyword [C++]"
ms.assetid: 25160f74-569e-492d-9e3c-67ece7486baa
caps.latest.revision: 17
caps.handback.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# interior_ptr (C++/CLI)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un *pointeur intérieur* déclare un pointeur à l'intérieur d'un type de référence, mais pas à l'objet lui\-même.  Un pointeur intérieur peut pointer vers un handle de référence, un type de valeur, un handle enfermé dans une boîte de type, un membre d'un type managé, ou un élément d'un tableau managé.  
  
## Tous les runtimes  
 \(Aucune note de cette fonctionnalité de langage ne s'applique à tous les runtimes.\)  
  
## Windows Runtime  
 \(Aucune note de cette fonctionnalité de langage ne s'applique qu'au Windows Runtime.\)  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
## Common Language Runtime  
 L'exemple de syntaxe montre un pointeur intérieur.  
  
### Syntaxe  
  
```cpp  
cli::interior_ptr<cv_qualifier type> var = &initializer;  
```  
  
### Paramètres  
 *cv\_qualifier*  
 **const** ou identificateurs `volatile`.  
  
 *type*  
 Type de *initializer*.  
  
 *var*  
 Nom de la variable `interior_ptr`.  
  
 *initializer*  
 Un membre d'un type de référence, un élément d'un tableau managé, ou tout autre objet que vous pouvez attribuer à un pointeur natif.  
  
### Remarques  
 Un pointeur natif ne peut pas suivre un élément lorsque son emplacement change sur le segment managé, ce qui résulte en des instances de déplacement de garbage collector d'un objet.  Pour qu'un pointeur fasse référence correctement à l'instance, l'exécution doit mettre à jour le pointeur à l'objet récemment positionné.  
  
 Un `interior_ptr` représente un surensemble des fonctionnalités d'un pointeur natif.  Par conséquent, un problème susceptible d'être affecté à un pointeur natif peut également être affecté à `interior_ptr`.  Un pointeur intérieur est autorisé à exécuter le même ensemble d'opérations que les pointeurs natifs, notamment la comparaison et retourner les opérations arithmétiques sur les pointeurs.  
  
 Un pointeur intérieur peut être déclaré dans la pile.  Un pointeur intérieur ne peut pas être déclaré en tant que membre d'une classe.  
  
 Puisque les pointeurs intérieurs existent uniquement dans la pile, prendre l'adresse d'un pointeur intérieur donne cell d'un pointeur non\-managé.  
  
 `interior_ptr` une conversion implicite à `bool`, qui permet son utilisation dans les instructions conditionnelles.  
  
 Pour plus d'informations sur la façon de déclarer un pointeur intérieur qui pointe vers un objet qui ne peut pas être déplacé sur le segment récupérés par le garbage collector, consultez [pin\_ptr](../windows/pin-ptr-cpp-cli.md).  
  
 `interior_ptr` est dans l'espace de noms cli.  Pour plus d'informations, consultez [Platform, default, and cli Namespaces](../windows/platform-default-and-cli-namespaces-cpp-component-extensions.md).  
  
 Pour plus d'informations sur les pointeurs intérieurs, consultez .  
  
-   [How to: Declare and Use Interior Pointers and Managed Arrays \(C\+\+\/CLI\)](../windows/how-to-declare-and-use-interior-pointers-and-managed-arrays-cpp-cli.md)  
  
-   [How to: Declare Value Types with the interior\_ptr Keyword \(C\+\+\/CLI\)](../windows/how-to-declare-value-types-with-the-interior-ptr-keyword-cpp-cli.md)  
  
-   [How to: Overload Functions with Interior Pointers and Native Pointers \(C\+\+\/CLI\)](../windows/how-to-overload-functions-with-interior-pointers-and-native-pointers-cpp-cli.md)  
  
-   [How to: Declare Interior Pointers with the const Keyword \(C\+\+\/CLI\)](../windows/how-to-declare-interior-pointers-with-the-const-keyword-cpp-cli.md)  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple suivant indique comment déclarer et utiliser un pointeur dans dans un type de référence.  
  
```cpp  
// interior_ptr.cpp  
// compile with: /clr  
using namespace System;  
  
ref class MyClass {  
public:  
   int data;  
};  
  
int main() {  
   MyClass ^ h_MyClass = gcnew MyClass;  
   h_MyClass->data = 1;  
   Console::WriteLine(h_MyClass->data);  
  
   interior_ptr<int> p = &(h_MyClass->data);  
   *p = 2;  
   Console::WriteLine(h_MyClass->data);  
  
   // alternatively  
   interior_ptr<MyClass ^> p2 = &h_MyClass;  
   (*p2)->data = 3;  
   Console::WriteLine((*p2)->data);  
}  
```  
  
 **Sortie**  
  
 **1**   
**2**   
**3**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)