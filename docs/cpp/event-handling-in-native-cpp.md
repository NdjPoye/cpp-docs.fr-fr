---
title: "Gestion des &#233;v&#233;nements en mode natif C++ | Microsoft Docs"
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
  - "gestion des événements, Visual C++"
ms.assetid: e4b9219a-15d8-42fb-83c8-6d2e4e087c8d
caps.latest.revision: 9
caps.handback.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestion des &#233;v&#233;nements en mode natif C++
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans la gestion des événements C\+\+ native, vous configurez une source d'événement et un récepteur d'événements respectivement à l'aide des attributs de [event\_source](../windows/event-source.md) et [event\_receiver](../windows/event-receiver.md), en spécifiant `type`\=`native`.  Ces attributs permettent aux classes auxquelles ils sont appliqués de déclencher et de gérer des événements dans un contexte natif non COM.  
  
## Déclaration d'événements  
 Dans une classe de source d'événement, utilisez le mot clé [\_\_event](../cpp/event.md) dans une déclaration de méthode pour déclarer la méthode comme événement.  Veillez à déclarer la méthode, mais ne la définissez pas ; cela générerait une erreur du compilateur, car celui\-ci définit la méthode implicitement lorsqu'elle est convertie en événement.  Les événements natifs peuvent être des méthodes avec zéro, un ou plusieurs paramètres.  Le type de retour peut être void ou un type intégral.  
  
## Définition de gestionnaires d'événements  
 Dans une classe de récepteur d'événements, vous définissez des gestionnaires d'événements, qui sont des méthodes avec signatures \(types de retour, conventions d'appel et arguments\) qui correspondent à l'événement qu'ils doivent gérer.  
  
## Raccordement de gestionnaires d'événements à des événements  
 Dans une classe de récepteur d'événements, vous utilisez également la fonction intrinsèque [\_\_hook](../cpp/hook.md) pour raccorder des événements aux gestionnaires d'événements et [\_\_unhook](../cpp/unhook.md) pour dissocier des événements des gestionnaires d'événements.  Vous pouvez raccorder plusieurs événements à un gestionnaire d'événements, ou plusieurs gestionnaires d'événements à un événement.  
  
## Déclenchement d'événements  
 Pour déclencher un événement, il vous suffit d'appeler la méthode déclarée comme événement dans la classe de source d'événement.  Si des gestionnaires ont été raccordés à l'événement, les gestionnaires sont appelés.  
  
### Code d'événement C\+\+ natif  
 L'exemple suivant montre comment déclencher un événement en C\+\+ natif.  Pour compiler et exécuter l'exemple, consultez les commentaires du code.  
  
## Exemple  
  
### Code  
  
```  
// evh_native.cpp  
#include <stdio.h>  
  
[event_source(native)]  
class CSource {  
public:  
   __event void MyEvent(int nValue);  
};  
  
[event_receiver(native)]  
class CReceiver {  
public:  
   void MyHandler1(int nValue) {  
      printf_s("MyHandler1 was called with value %d.\n", nValue);  
   }  
  
   void MyHandler2(int nValue) {  
      printf_s("MyHandler2 was called with value %d.\n", nValue);  
   }  
  
   void hookEvent(CSource* pSource) {  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __hook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
  
   void unhookEvent(CSource* pSource) {  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler1);  
      __unhook(&CSource::MyEvent, pSource, &CReceiver::MyHandler2);  
   }  
};  
  
int main() {  
   CSource source;  
   CReceiver receiver;  
  
   receiver.hookEvent(&source);  
   __raise source.MyEvent(123);  
   receiver.unhookEvent(&source);  
}  
```  
  
### Sortie  
  
```  
MyHandler2 was called with value 123.  
MyHandler1 was called with value 123.  
```  
  
## Voir aussi  
 [Gestion des événements](../cpp/event-handling.md)