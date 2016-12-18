---
title: "ref new, gcnew  (C++ Component Extensions) | Microsoft Docs"
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
  - "gcnew"
  - "ref new"
  - "gcnew_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "ref new keyword (C++)"
  - "gcnew keyword [C++]"
ms.assetid: 388a62da-c2df-4a94-a9a2-205b53e577da
caps.latest.revision: 24
caps.handback.revision: 22
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ref new, gcnew  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé d'agrégation `ref new` alloue une instance d'un type récupéré par le garbage collector quand l'objet devient inaccessible, et qui renvoie un handle \([^](../windows/handle-to-object-operator-hat-cpp-component-extensions.md)\) à l'objet alloué.  
  
## Tous les runtimes  
 La mémoire d'une instance d'un type alloué par `ref new` est automatiquement désallouée.  
  
 Une opération `ref new` lève une exception `OutOfMemoryException` s'il est impossible d'allouer de la mémoire.  
  
 Pour plus d'informations sur l'allocation et la désallocation de la mémoire pour les types C\+\+ natifs, consultez les [opérateurs new et delete](../cpp/new-and-delete-operators.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Utilisez `ref new` pour allouer de la mémoire aux objets Windows Runtime dont vous voulez administrer automatiquement la durée de vie.  L'objet est automatiquement désalloué quand son nombre de références atteint zéro, ce qui se produit une fois que la dernière copie de la référence est hors de portée.  Pour plus d'informations, consultez [Classes et structs de référence](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Spécifications  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
 La mémoire d'un type managé \(type référence ou valeur\) est allouée par `gcnew`, puis désallouée à l'aide du garbage collection.  
  
### Spécifications  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple suivant utilise `gcnew` pour allouer un objet Message.  
  
```  
// mcppv2_gcnew_1.cpp  
// compile with: /clr  
ref struct Message {  
   System::String^ sender;  
   System::String^ receiver;  
   System::String^ data;  
};  
  
int main() {  
   Message^ h_Message  = gcnew Message;  
  //...  
}  
```  
  
 **Exemple**  
  
 L'exemple suivant utilise `gcnew` pour créer un type valeur boxed à utiliser comme type référence.  
  
```  
// example2.cpp : main project file.  
// compile with /clr  
using namespace System;  
value class Boxed {  
    public:  
        int i;  
};  
int main()  
{  
    Boxed^ y = gcnew Boxed;  
    y->i = 32;  
    Console::WriteLine(y->i);  
    return 0;  
}  
```  
  
 **Sortie**  
  
  **32**   
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)