---
title: "R&#233;f&#233;rences faibles et cycles de rupture (C++/CX) | Microsoft Docs"
ms.custom: ""
ms.date: "01/22/2017"
ms.prod: "windows-client-threshold"
ms.technology: ""
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "article"
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
caps.latest.revision: 12
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
caps.handback.revision: 12
---
# R&#233;f&#233;rences faibles et cycles de rupture (C++/CX)
Dans n'importe quel système de type basé sur le comptage de références, les références aux types peuvent représenter des *cycles*, autrement dit, un objet fait référence à un deuxième objet, le deuxième objet fait référence à un troisième objet, et ainsi de suite jusqu'à ce qu'un objet final refasse référence au premier objet. Dans un cycle, les objets ne peuvent pas être supprimés correctement lorsque le nombre de références à un objet devient égal à zéro. Pour vous aider à résoudre ce problème, [!INCLUDE[cppwrt_short](../cppcx/includes/cppwrt-short-md.md)] fournit la classe [Platform::WeakReference, classe](../cppcx/platform-weakreference-class.md). Un objet `WeakReference` prend en charge la méthode [Resolve](../cppcx/weakreference-resolve-method-platform-namespace.md), qui retourne la valeur null si l'objet n'existe plus ou lève une exception [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) si l'objet existe mais n'est pas de type  `T`.  
  
 Un scénario dans lequel `WeakReference` doit être utilisé lorsque le pointeur `this` est capturé dans une expression lambda qui est utilisée pour définir un gestionnaire d'événements. Nous vous recommandons d'utiliser les méthodes nommées lorsque vous définissez des gestionnaires d'événements, mais si vous souhaitez utiliser un lambda pour votre gestionnaire d'événements \(ou si vous devez arrêter un cycle de comptage de références dans une autre situation\), utilisez `WeakReference`. Voici un exemple :  
  
```  
  
using namespace Platform::Details;  
using namespace Windows::UI::Xaml;  
using namespace Windows::UI::Xaml::Input;  
using namespace Windows::UI::Xaml::Controls;  
  
Class1::Class1()  
{  
    // Class1 has a reference to m_Page  
    m_Page = ref new Page();  
  
    // m_Page will have a reference to this Class1  
    // so create a weak reference to this  
    WeakReference wr(this);  
    m_Page->DoubleTapped += ref new DoubleTappedEventHandler(   
        [wr](Object^ sender, DoubleTappedRoutedEventArgs^ args)  
    {  
       // Use the weak reference to get the object  
       Class1^ c = wr.Resolve<Class1>();  
       if (c != nullptr)  
       {  
           c->m_eventFired = true;  
       }  
       else  
       {  
           // Inform the event that this handler should be removed  
           // from the subscriber list  
           throw ref new DisconnectedException();  
       }  
    });   
}  
  
}  
```  
  
 Lorsqu'un gestionnaire d'événements lève `DisconnectedException`, l'événement supprime le gestionnaire de la liste d'abonnés.  
  
## Voir aussi  
 [\(NOTINBUILD\) Rubriques avancées](http://msdn.microsoft.com/fr-fr/1ccff0cf-a6cc-47ef-a05f-eba6307b3ced)