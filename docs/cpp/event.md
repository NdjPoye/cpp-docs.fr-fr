---
title: "__event | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "__event_cpp"
  - "__event"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__event (mot clé C++)"
  - "événements (C++), __event"
ms.assetid: d3019b3e-722e-48df-8536-c05878461f9e
caps.latest.revision: 14
caps.handback.revision: 14
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# __event
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Déclare un événement.  
  
## Syntaxe  
  
```  
  
      __event   
      method-declarator  
      ;  
__event __interface interface-specifier;  
__event member-declarator;  
```  
  
## Notes  
 Le mot clé `__event` peut être appliqué à une déclaration de méthode, une déclaration d'interface ou une déclaration de membre de données.  Toutefois, vous ne pouvez pas utiliser le mot clé `__event` pour qualifier un membre d'une classe imbriquée.  
  
 Selon que votre source et votre récepteur d'événements sont C\+\+ natif, COM ou managé \(.NET Framework\), vous pouvez utiliser les constructions suivantes en tant qu'événements :  
  
|C\+\+ natif|COM|Managé \(.NET Framework\)|  
|-----------------|---------|-------------------------------|  
|Méthode|—|méthode|  
|—|interface|—|  
|—|—|membre de données|  
  
 Utilisez [\_\_hook](../cpp/hook.md) dans un récepteur d'événements pour associer une méthode de gestionnaire à une méthode d'événement.  Notez qu'une fois que vous avez créé un événement avec le mot clé `__event`, tous les gestionnaires d'événements accrochés ultérieurement à cet événement sont appelés lorsque l'événement est appelé.  
  
 Une déclaration de méthode `__event` ne peut pas avoir de définition. Une définition étant générée implicitement, la méthode d'événement peut être appelée comme s'il s'agissait d'une méthode ordinaire.  
  
> [!NOTE]
>  Une classe ou structure modélisée ne peut pas contenir d'événements.  
  
## Événements natifs  
 Les événements natifs sont des méthodes.  Le type de retour est généralement `HRESULT` ou `void`, mais peut être tout type intégral, notamment `enum`.  Lorsqu'un événement utilise un type de retour intégral, une condition d'erreur est définie lorsqu'un gestionnaire d'événements retourne une valeur différente de zéro, auquel cas l'événement déclenché appelle les autres délégués.  
  
```  
// Examples of native C++ events:  
__event void OnDblClick();  
__event HRESULT OnClick(int* b, char* s);  
```  
  
 Pour obtenir un exemple de code, consultez [Gestion des événements en C\+\+ natif](../cpp/event-handling-in-native-cpp.md).  
  
## Événements COM  
 Les événements COM sont des interfaces.  Les paramètres d'une méthode dans une interface de source d'événement doivent être des paramètres **in** \(mais cela n'est pas rigoureusement appliqué\), car un paramètre **out** n'est pas utile lors du multicasting.  Un avertissement de niveau 1 est émis si vous utilisez un paramètre **out**.  
  
 Le type de retour est généralement `HRESULT` ou `void`, mais peut être tout type intégral, notamment `enum`.  Lorsqu'un événement utilise un type de retour intégral et qu'un gestionnaire d'événements retourne une valeur différente de zéro, il s'agit d'une condition d'erreur. L'événement déclenché annule alors les appels aux autres délégués.  Notez que le compilateur marque automatiquement une interface de source d'événement comme [source](../windows/source-cpp.md) dans le fichier IDL généré.  
  
 Le mot clé [\_\_interface](../cpp/interface.md) est toujours requis après `__event` pour une source d'événement COM.  
  
```  
// Example of a COM event:  
__event __interface IEvent1;  
```  
  
 Pour obtenir un exemple de code, consultez [Gestion des événements dans COM](../cpp/event-handling-in-com.md).  
  
## Événements managés  
 Pour plus d'informations sur le codage des événements dans la nouvelle syntaxe, consultez [event](../windows/event-cpp-component-extensions.md).  
  
 Les événements managés sont des méthodes ou des données membres.  En cas d'utilisation avec un événement, le type de retour d'un délégué doit être conforme à la [Common Language Specification](../Topic/Language%20Independence%20and%20Language-Independent%20Components.md).  Le type de retour du gestionnaire d'événements doit correspondre à celui du délégué.  Pour plus d'informations sur les délégués, consultez [\_\_delegate](../misc/delegate.md).  Si un événement managé est un membre de données, son type doit être un pointeur vers un délégué.  
  
 Dans .NET Framework, vous pouvez traiter un membre de données comme s'il s'agissait d'une méthode \(autrement dit, la méthode `Invoke` de son délégué correspondant\).  Vous devez prédéfinir le type délégué pour déclarer un membre de données d'événement managé.  En revanche, une méthode d'événement managé définit implicitement le délégué managé correspondant, s'il n'est pas déjà défini.  Par exemple, vous pouvez déclarer une valeur d'événement telle que `OnClick` comme événement de la manière suivante :  
  
```  
// Examples of managed events:  
__event ClickEventHandler* OnClick;  // data member as event  
__event void OnClick(String* s);  // method as event  
```  
  
 Lors de la déclaration implicite d'un événement managé, vous pouvez spécifier des accesseurs add et remove qui seront appelés lorsque les gestionnaires d'événements sont ajoutés ou supprimés.  Vous pouvez également définir la méthode qui appelle \(déclenche\) l'événement en dehors de la classe.  
  
## Exemple : événements natifs  
  
```  
// EventHandling_Native_Event.cpp  
// compile with: /c  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
```  
  
## Exemple : événements COM  
  
```  
// EventHandling_COM_Event.cpp  
// compile with: /c  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT MyEvent();  
};  
 [ coclass, uuid("00000000-0000-0000-0000-000000000003"),  event_source(com) ]  
class CSource : public IEventSource {  
public:  
   __event __interface IEventSource;  
   HRESULT FireEvent() {  
      __raise MyEvent();  
      return S_OK;  
   }  
};  
```  
  
## Exemple : événements managés  
  
```  
// EventHandling_Managed_Event.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[event_source(managed)]  
public __gc class CPSource {  
  
public:  
   __event void MyEvent(Int16 nValue);  
};  
```  
  
 Lors de l'application d'un attribut à un événement, vous pouvez spécifier que l'attribut s'applique soit aux méthodes générées, soit à la méthode Invoke du délégué généré.  Le comportement par défaut \(`event:`\) consiste à appliquer l'attribut à l'événement.  
  
```  
// EventHandling_Managed_Event_2.cpp  
// compile with: /clr:oldSyntax /c  
using namespace System;  
[attribute(All, AllowMultiple=true)]  
public __gc class Attr {};  
  
public __delegate void D();  
  
public __gc class X {  
public:  
   [method:Attr] __event D* E;  
   [returnvalue:Attr] __event void noE();  
};  
```  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Gestion des événements](../cpp/event-handling.md)   
 [event\_source](../windows/event-source.md)   
 [event\_receiver](../windows/event-receiver.md)   
 [\_\_hook](../cpp/hook.md)   
 [\_\_unhook](../cpp/unhook.md)   
 [\_\_raise](../cpp/raise.md)