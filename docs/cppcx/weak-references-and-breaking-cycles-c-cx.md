---
title: "Références faibles et cycles de rupture (C + c++ / CX) | Documents Microsoft"
ms.custom: 
ms.date: 01/22/2017
ms.technology: cpp-windows
ms.reviewer: 
ms.suite: 
ms.tgt_pltfrm: 
ms.topic: language-reference
ms.assetid: 1acb6402-05f0-4951-af94-0e9dab41c53e
caps.latest.revision: 
author: ghogen
ms.author: ghogen
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: 3a98dc4dd43b40f378a91713770c4c5500c790d0
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="weak-references-and-breaking-cycles-ccx"></a>Références faibles et cycles de rupture (C++/CX)
Dans n'importe quel système de type basé sur le comptage de références, les références aux types peuvent représenter des *cycles*, autrement dit, un objet fait référence à un deuxième objet, le deuxième objet fait référence à un troisième objet, et ainsi de suite jusqu'à ce qu'un objet final refasse référence au premier objet. Dans un cycle, les objets ne peuvent pas être supprimés correctement lorsque le nombre de références à un objet devient égal à zéro. Pour vous aider à résoudre ce problème, C + c++ / CX fournit le [Platform::WeakReference, classe](../cppcx/platform-weakreference-class.md) classe. Un objet `WeakReference` prend en charge la méthode [Resolve](../cppcx/platform-weakreference-class.md#resolve) , qui retourne la valeur null si l'objet n'existe plus ou lève une exception [Platform::InvalidCastException](../cppcx/platform-invalidcastexception-class.md) si l'objet existe mais n'est pas de type `T`.  
  
 Un scénario dans lequel `WeakReference` doit être utilisé lorsque le pointeur `this` est capturé dans une expression lambda qui est utilisée pour définir un gestionnaire d'événements. Nous vous recommandons d'utiliser les méthodes nommées lorsque vous définissez des gestionnaires d'événements, mais si vous souhaitez utiliser un lambda pour votre gestionnaire d'événements (ou si vous devez arrêter un cycle de comptage de références dans une autre situation), utilisez `WeakReference`. Voici un exemple :  
  
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
  
## <a name="see-also"></a>Voir aussi  


