---
title: "for each, in | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "cliext::foreach"
  - "for"
  - "each"
  - "in"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "pour chaque mot clé (C++)"
ms.assetid: 0c3a364b-2747-43f3-bb8d-b7d3b7023f79
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# for each, in
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Itère dans un tableau ou une collection.  Ce mot clé non standard est disponible dans C\+\+\/CLI et les projets natifs C\+\+.  Toutefois, son utilisation n'est pas recommandée.  Envisagez d'utiliser une instruction [Basé sur une plage, instruction \(C\+\+\)](../cpp/range-based-for-statement-cpp.md) standard à la place.  
  
## Tous les runtimes  
 **Syntaxe**  
  
```  
  
        for each (type identifier in expression) {  
   statements  
}  
  
```  
  
 **Paramètres**  
  
 `type`  
 Type d'élément `identifier`.  
  
 `identifier`  
 La variable d'itération qui représente l'élément de collection.  Lorsque `identifier` est un [Tracking Reference Operator](../windows/tracking-reference-operator-cpp-component-extensions.md), vous pouvez le modifier.  
  
 `expression`  
 Expression ou collection de tableaux.  L'élément de collection doit pouvoir être converti par le compilateur en type d'élément `identifier`.  
  
 `statements`  
 Une ou plusieurs instructions à exécuter.  
  
 **Notes**  
  
 L'instruction `for each` permet d'itérer au sein d'une collection.  Vous pouvez modifier les éléments d'une collection, mais vous ne pouvez ni ajouter ni supprimer des éléments.  
  
 Les *statements* sont exécutées pour chaque élément du tableau ou de la collection.  Une fois l'itération terminée pour tous les éléments de la collection, le contrôle est transféré à l'instruction placée après le bloc `for each`.  
  
 `for each` et `in` sont des [mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md).  
  
 Pour plus d'informations :  
  
-   [Itération au sein d'une collection STL en utilisant for each](../dotnet/iterating-over-stl-collection-by-using-for-each.md)  
  
-   [Comment : itérer au sein des tableaux avec for each](../dotnet/how-to-iterate-over-arrays-with-for-each.md)  
  
-   [Comment : itérer au sein d'une collection générique en utilisant for each](../dotnet/how-to-iterate-over-a-generic-collection-with-for-each.md)  
  
-   [Comment : itérer au sein d'une collection définie par l'utilisateur en utilisant for each](../dotnet/how-to-iterate-over-a-user-defined-collection-with-for-each.md)  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
  
### Conditions requises  
 Option du compilateur : **\/ZW**  
  
### Exemple  
 Cet exemple montre comment utiliser `for each` pour itérer au sein d'une chaîne.  
  
```  
// for_each_string1.cpp  
// compile with: /ZW  
#include <stdio.h>  
using namespace Platform;  
  
ref struct MyClass {  
   property String^ MyStringProperty;  
};  
  
int main() {  
   String^ MyString = ref new String("abcd");  
  
   for each ( char c in MyString )  
      wprintf("%c", c);  
  
   wprintf("/n");  
  
   MyClass^ x = ref new MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( char c in x->MyStringProperty )  
      wprintf("%c", c);  
}  
```  
  
 **Sortie**  
  
  **abcd**  
 **Test**   
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 **Notes**  
  
 La syntaxe CLR est identique à la syntaxe **Tous les runtimes**, à l'exception des points suivants.  
  
 *expression*  
 Collection ou expression de tableau managé.  L'élément de collection doit pouvoir être converti par le compilateur de <xref:System.Object> en type *identifier*.  
  
 *expression* correspond à un type qui implémente <xref:System.Collections.IEnumerable>, <xref:System.Collections.Generic.IEnumerable%601>, ou un type qui définit une méthode `GetEnumerator` qui retourne un type qui implémente <xref:System.Collections.IEnumerator> ou déclare toutes les méthodes définies dans `IEnumerator`.  
  
### Conditions requises  
 Option du compilateur : **\/clr**  
  
### Exemple  
 Cet exemple montre comment utiliser `for each` pour itérer au sein d'une chaîne.  
  
```  
// for_each_string2.cpp  
// compile with: /clr  
using namespace System;  
  
ref struct MyClass {  
   property String ^ MyStringProperty;  
};  
  
int main() {  
   String ^ MyString = gcnew String("abcd");  
  
   for each ( Char c in MyString )  
      Console::Write(c);  
  
   Console::WriteLine();  
  
   MyClass ^ x = gcnew MyClass();  
   x->MyStringProperty = "Testing";  
  
   for each( Char c in x->MyStringProperty )  
      Console::Write(c);  
}  
```  
  
 **Sortie**  
  
  **abcd**  
 **Test**    
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)