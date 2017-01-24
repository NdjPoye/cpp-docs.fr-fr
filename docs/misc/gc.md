---
title: "__gc | Microsoft Docs"
ms.custom: ""
ms.date: "11/17/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "__gc"
  - "__gc_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "types _gc"
  - "classes (C++), gérées"
  - "classes managées"
ms.assetid: 63b1e7ab-d1c8-4582-aa89-21bfddf694a9
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __gc
> [!NOTE]
>  Cette rubrique s’applique uniquement à la version 1 des extensions managées pour C\+\+. Cette syntaxe doit être utilisée uniquement pour conserver le code de la version 1. Consultez [Classes and Structs](../windows/classes-and-structs-cpp-component-extensions.md) Pour plus d’informations sur l’utilisation de la fonctionnalité équivalente dans la nouvelle syntaxe.  
  
 Déclare un type \_\_gc.  
  
## Syntaxe  
  
```  
  
__gc  
array-specifier  
__gc   
class-specifier  
__gc   
struct-specifier  
__gc  
interface-specifier  
__gc  
pointer-specifier  
__gc new  
  
```  
  
## Notes  
 Un type \_\_gc est une extension de langage C\+\+ qui simplifie la programmation .NET Framework en fournissant des fonctionnalités telles que l'interopérabilité et le garbage collection.  
  
> [!NOTE]
>  Chaque fonction membre d'une \_\_gc class abstraite doit être définie, sauf si la fonction membre est une fonction virtuelle pure.  
  
 Dans les Extensions managées pour C\+\+, les équivalents pour C\# class et C\# struct sont les suivants :  
  
|Extensions managées pour C\+\+|C\#|Pour plus d'informations|  
|------------------------------------|---------|------------------------------|  
|\_\_gc struct ou \_\_gc class|classe|mot clé [class](../Topic/class%20\(C%23%20Reference\).md)|  
|\_\_value struct ou \_\_value class|struct|mot clé [struct](../Topic/struct%20\(C%23%20Reference\).md)|  
  
## Exemple  
 Dans l'exemple suivant, une classe managée \(`X`\) est déclarée avec une donnée membre publique, manipulée par l'intermédiaire d'un pointeur managé :  
  
```  
// keyword__gc.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__gc class X {  
public:  
   int i;  
   int ReturnInt() { return 5; }  
};  
  
int main() {  
   // X is a __gc class, so px is a __gc pointer  
   X* px;  
   px = new X;   // creates a managed object of type X  
   Console::WriteLine(px->i);  
  
   px->i = 4;   // modifies X::i through px  
   Console::WriteLine(px->i);  
  
   int n = px->ReturnInt();   // calls X::ReturnInt through px  
   Console::WriteLine(n);  
}  
```  
  
## Sortie  
  
```  
0  
4  
5  
```