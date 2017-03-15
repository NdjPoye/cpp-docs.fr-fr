---
title: "Gestion des &#233;v&#233;nements dans COM | Microsoft Docs"
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
  - "COM, événements"
  - "déclarer des événements"
  - "déclarer des événements, gestion des événements dans COM"
  - "déclarer des événements, dans COM"
  - "gestionnaires d'événements"
  - "gestionnaires d'événements, COM"
  - "gestion des événements"
  - "gestion des événements, à propos de la gestion d'événements"
  - "gestion des événements, COM"
  - "récepteurs d'événements, dans la gestion des événements"
  - "récepteurs d'événements, correspondance de nom et de signature"
  - "sources d'événement, dans la gestion des événements"
  - "raccorder les événements"
ms.assetid: 6b4617d4-a58e-440c-a8a6-1ad1c715b2bb
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion des &#233;v&#233;nements dans COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la gestion des événements COM, vous configurez une source d'événement et un récepteur d'événements respectivement à l'aide des attributs [event\_source](../windows/event-source.md) et [event\_receiver](../windows/event-receiver.md), en spécifiant `type`\=**com**.  Ces attributs injectent le code approprié pour les interfaces personnalisées, de dispatch et doubles afin d'autoriser les classes auxquelles ils sont appliqués à déclencher et gérer des événements via des points de connexion COM.  
  
## Déclaration d'événements  
 Dans une classe de source d'événement, utilisez le mot clé [\_\_event](../cpp/event.md) dans une déclaration d'interface pour déclarer les méthodes d'interface en tant qu'événements.  Les événements de cette interface sont déclenchés lorsqu'ils sont appelés comme méthodes d'interface.  Les méthodes sur les interfaces d'événements peuvent contenir zéro, un ou plusieurs paramètres \(qui doivent tous être des paramètres **in** \).  Le type de retour peut être void ou un type intégral.  
  
## Définition de gestionnaires d'événements  
 Dans une classe de récepteur d'événements, vous définissez des gestionnaires d'événements, qui sont des méthodes avec signatures \(types de retour, conventions d'appel et arguments\) qui correspondent à l'événement qu'ils doivent gérer.  Pour les événements COM, la correspondance des conventions d'appel n'est pas nécessaire ; pour plus de détails, consultez la rubrique [Événements COM dépendant des dispositions](#vcconeventhandlingincomanchorlayoutdependentcomevents) ci\-dessous.  
  
## Raccordement de gestionnaires d'événements à des événements  
 Dans une classe de récepteur d'événements, vous utilisez également la fonction intrinsèque [\_\_hook](../cpp/hook.md) pour raccorder des événements aux gestionnaires d'événements et [\_\_unhook](../cpp/unhook.md) pour dissocier des événements des gestionnaires d'événements.  Vous pouvez raccorder plusieurs événements à un gestionnaire d'événements, ou plusieurs gestionnaires d'événements à un événement.  
  
> [!NOTE]
>  En général, il existe deux techniques pour permettre à un récepteur d'événements COM d'accéder aux définitions de l'interface de source d'événements.  La première, comme indiqué ci\-dessous, consiste à partager un fichier d'en\-tête commun.  La deuxième consiste à utiliser [\#import](../preprocessor/hash-import-directive-cpp.md) avec le qualificateur d'importation `embedded_idl`, afin que la bibliothèque de types de sources d'événement soit écrite dans le fichier .tlh tout en préservant le code généré par attributs.  
  
## Déclenchement d'événements  
 Pour déclencher un événement, il vous suffit d'appeler la méthode dans l'interface déclarée avec le mot clé `__event` dans la classe de source d'événement.  Si des gestionnaires ont été raccordés à l'événement, les gestionnaires sont appelés.  
  
### Code d'événement COM  
 L'exemple suivant montre comment déclencher un événement dans une classe COM.  Pour compiler et exécuter l'exemple, consultez les commentaires du code.  
  
```  
// evh_server.h  
#pragma once  
  
[ dual, uuid("00000000-0000-0000-0000-000000000001") ]  
__interface IEvents {  
   [id(1)] HRESULT MyEvent([in] int value);  
};  
  
[ dual, uuid("00000000-0000-0000-0000-000000000002") ]  
__interface IEventSource {  
   [id(1)] HRESULT FireEvent();  
};  
  
class DECLSPEC_UUID("530DF3AD-6936-3214-A83B-27B63C7997C4") CSource;  
```  
  
 Puis le serveur :  
  
```  
// evh_server.cpp  
// compile with: /LD  
// post-build command: Regsvr32.exe /s evh_server.dll  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include "evh_server.h"  
  
[ module(dll, name="EventSource", uuid="6E46B59E-89C3-4c15-A6D8-B8A1CEC98830") ];  
  
[coclass, event_source(com), uuid("530DF3AD-6936-3214-A83B-27B63C7997C4")]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;   
  
   HRESULT FireEvent() {  
      __raise MyEvent(123);  
      return S_OK;  
   }  
};  
```  
  
 Puis le client :  
  
```  
// evh_client.cpp  
// compile with: /link /OPT:NOREF  
#define _ATL_ATTRIBUTES 1  
#include <atlbase.h>  
#include <atlcom.h>  
#include <stdio.h>  
#include "evh_server.h"  
  
[ module(name="EventReceiver") ];  
  
[ event_receiver(com) ]  
class CReceiver {  
public:  
   HRESULT MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   HRESULT MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
      return S_OK;  
   }  
  
   void HookEvent(IEventSource* pSource) {  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void UnhookEvent(IEventSource* pSource) {  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&IEvents::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   // Create COM object  
   CoInitialize(NULL);  
   {  
      IEventSource* pSource = 0;  
      HRESULT hr = CoCreateInstance(__uuidof(CSource), NULL,         CLSCTX_ALL, __uuidof(IEventSource), (void **) &pSource);  
      if (FAILED(hr)) {  
         return -1;  
      }  
  
      // Create receiver and fire event  
      CReceiver receiver;  
      receiver.HookEvent(pSource);  
      pSource->FireEvent();  
      receiver.UnhookEvent(pSource);  
   }  
   CoUninitialize();  
   return 0;  
}  
```  
  
### Sortie  
  
```  
MyHandler1 was called with value 123.  
MyHandler2 was called with value 123.  
```  
  
##  <a name="vcconeventhandlingincomanchorlayoutdependentcomevents"></a> Événements COM dépendant des dispositions  
 La dépendance aux dispositions représente un problème uniquement dans le cadre de la programmation COM.  Dans la gestion des événements natifs et managés, les signatures \(type de retour, convention d'appel et arguments\) des gestionnaires doivent correspondre aux événements, mais il n'est pas nécessaire que les noms des gestionnaires correspondent aux événements.  
  
 Toutefois, dans la gestion des événements COM, lorsque vous définissez le paramètre *layout\_dependent* de **event\_receiver** sur **true**, la correspondance du nom et de la signature est appliquée.  Cela signifie que les noms et les signatures des gestionnaires dans le récepteur d'événements doivent correspondre exactement aux noms et aux signatures des événements auxquels ils sont raccordés.  
  
 Si *layout\_dependent* a la valeur **false**, la convention d'appel et la classe de stockage \(virtuelle, statique, etc.\) peuvent être associées et mises en correspondance entre la méthode de déclenchement d'événement et les méthodes de raccordement \(ses délégués\).  Lorsque *layout\_dependent\=***true**, c'est un peu plus efficace.  
  
 Par exemple, supposons que `IEventSource` est défini pour disposer des méthodes suivantes :  
  
```  
[id(1)] HRESULT MyEvent1([in] int value);  
[id(2)] HRESULT MyEvent2([in] int value);  
```  
  
 Supposez que la source d'événement a la forme suivante :  
  
```  
[coclass, event_source(com)]  
class CSource : public IEventSource {  
public:  
   __event __interface IEvents;  
  
   HRESULT FireEvent() {  
      MyEvent1(123);  
      MyEvent2(123);  
      return S_OK;  
   }  
};  
```  
  
 Ensuite, dans le récepteur d'événements, tout gestionnaire raccordé à une méthode dans `IEventSource` doit correspondre au nom et à la signature, comme indiqué :  
  
```  
[coclass, event_receiver(com, true)]  
class CReceiver {  
public:  
   HRESULT MyEvent1(int nValue) {  // name and signature matches MyEvent1  
      ...  
   }  
   HRESULT MyEvent2(E c, char* pc) {  // signature doesn't match MyEvent2  
      ...  
   }  
   HRESULT MyHandler1(int nValue) {  // name doesn't match MyEvent1 (or 2)  
      ...  
   }  
   void HookEvent(IEventSource* pSource) {  
      __hook(IFace, pSource);  // Hooks up all name-matched events   
                               // under layout_dependent = true  
      __hook(&IFace::MyEvent1, pSource, &CReceive::MyEvent1);   // valid  
      __hook(&IFace::MyEvent2, pSource, &CSink::MyEvent2);   // not valid  
      __hook(&IFace::MyEvent1, pSource, &CSink:: MyHandler1); // not valid  
   }  
};  
```  
  
## Voir aussi  
 [Gestion des événements](../cpp/event-handling.md)