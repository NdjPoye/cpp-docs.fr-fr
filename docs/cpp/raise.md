---
title: "__raise | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__raise"
  - "__raise_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__raise (mot clé) (C++)"
ms.assetid: 6f1ae418-5f0f-48b6-9f6e-8ea7e66b239a
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# __raise
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Met en évidence le site d'appel d'un événement.  
  
## Syntaxe  
  
```  
  
__raise   
method-declarator  
;  
  
```  
  
## Notes  
 À partir du code managé, un événement ne peut être déclenché que par la classe dans laquelle il est défini.  Pour plus d'informations, consultez [event](../windows/event-cpp-component-extensions.md).  
  
 Le mot clé `__raise` entraîne l'émission d'une erreur si vous appelez un non\-événement.  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## Exemple  
  
```  
// EventHandlingRef_raise.cpp  
struct E {  
   __event void func1();  
   void func1(int) {}  
  
   void func2() {}  
  
   void b() {  
      __raise func1();  
      __raise func1(1);  // C3745: 'int Event::bar(int)':   
                         // only an event can be 'raised'  
      __raise func2();   // C3745  
   }  
};  
  
int main() {  
   E e;  
   __raise e.func1();  
   __raise e.func1(1);  // C3745  
   __raise e.func2();   // C3745  
}  
```  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Gestion des événements](../cpp/event-handling.md)   
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)