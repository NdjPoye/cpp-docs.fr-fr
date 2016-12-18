---
title: "__delegate | Microsoft Docs"
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
  - "__delegate_cpp"
  - "__delegate"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "délégués, _delegate (mot clé)"
  - "pointeurs de fonction gérées"
  - "__delegate (mot clé)"
ms.assetid: a41d2211-b79b-4509-a4c2-cc91f3d4fc9d
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "douge"
---
# __delegate
**Remarque** Cette rubrique s'applique uniquement à la version 1 des extensions managées pour C\+\+. Cette syntaxe doit être utilisée uniquement pour conserver le code de la version 1. Consultez [délégué](../windows/delegate-cpp-component-extensions.md) Pour plus d’informations sur l’utilisation de la fonctionnalité équivalente dans la nouvelle syntaxe.  
  
 Définit un type référence qui peut être utilisé pour encapsuler une méthode avec une signature spécifique.  
  
## Syntaxe  
  
```  
  
__delegate   
function-declarator  
  
```  
  
## Notes  
 Un délégué est sensiblement équivalent à un pointeur fonction C\+\+, à l'exception des éléments suivants :  
  
-   Un délégué peut être lié à une ou plusieurs méthodes dans une classe \_\_gc.  
  
 Lorsque le compilateur rencontre le mot clé `__delegate`, une définition de classe \_\_gc est générée. Cette classe \_\_gc présente caractéristiques suivantes :  
  
-   Elle hérite de **System::MulticastDelegate**.  
  
-   Elle possède un constructeur qui accepte deux arguments : un pointeur vers une classe \_\_gc ou **NULL** \(dans le cas d'une liaison à une méthode statique\) et une méthode complète du type spécifié.  
  
-   Elle possède une méthode appelée `Invoke`, dont la signature correspond à la signature déclarée du délégué.  
  
## Exemple  
 Dans l'exemple suivant, une classe \_\_gc \(`MyCalendar`\) et un délégué \(`GetDayOfWeek`\) sont déclarés. Le délégué est ensuite lié aux différentes méthodes de `MyCalendar`, appelant chaque méthode l'une après l'autre :  
  
```  
// keyword__delegate.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
__delegate int GetDayOfWeek();  
__gc class MyCalendar {  
public:  
   MyCalendar() : m_nDayOfWeek(4) {}  
   int MyGetDayOfWeek() {   
      Console::WriteLine("handler"); return m_nDayOfWeek;   
   }  
   static int MyStaticGetDayOfWeek() {   
      Console::WriteLine("static handler");   
      return 6;  
   }  
private:  
   int m_nDayOfWeek;  
};  
  
int main () {  
   GetDayOfWeek * pGetDayOfWeek;  // declare delegate type  
   int nDayOfWeek;  
  
   // bind delegate to static method  
   pGetDayOfWeek = new GetDayOfWeek(0, &MyCalendar::MyStaticGetDayOfWeek);  
   nDayOfWeek = pGetDayOfWeek->Invoke();  
   Console::WriteLine(nDayOfWeek);  
  
   // bind delegate to instance method  
   MyCalendar * pcal = new MyCalendar();  
   pGetDayOfWeek = static_cast<GetDayOfWeek*>(Delegate::Combine(pGetDayOfWeek,  
      new GetDayOfWeek(pcal, &MyCalendar::MyGetDayOfWeek)));  
   nDayOfWeek = pGetDayOfWeek->Invoke();  
   Console::WriteLine(nDayOfWeek);  
  
   // delegate now bound to two methods; remove instance method  
   pGetDayOfWeek = static_cast<GetDayOfWeek*>(Delegate::Remove(pGetDayOfWeek,  
      new GetDayOfWeek(pcal, &MyCalendar::MyGetDayOfWeek)));  
}  
```  
  
## Résultat de l'exemple  
  
```  
static handler  
6  
static handler  
handler  
4  
```