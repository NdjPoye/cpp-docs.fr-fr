---
title: "Windows Sockets&#160;: blocage | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mode blocage (sockets)"
  - "sockets (C++), comportement sur différentes plateformes Windows"
  - "sockets (C++), mode blocage"
  - "Windows Sockets (C++), mode blocage"
  - "Windows Sockets (C++), Windows (plateformes)"
ms.assetid: 10aca9b1-bfba-41a8-9c55-ea8082181e63
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets&#160;: blocage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article et deux autres expliquent plusieurs problèmes de programmation Windows Sockets.  Cet article traite du blocage.  Les autres problèmes sont traitées dans les articles : [Protocole Windows : Ordre d'octet](../mfc/windows-sockets-byte-ordering.md) et [Protocole Windows : La conversion de chaînes](../mfc/windows-sockets-converting-strings.md).  
  
 Si vous utilisez ou dérivez de la classe [CAsyncSocket](../mfc/reference/casyncsocket-class.md), vous devez gérer ces problèmes vous\-même.  Si vous utilisez ou dérivez de la classe [CSocket](../mfc/reference/csocket-class.md), MFC les gère automatiquement.  
  
## Blocage  
 Un socket peut être « en mode bloquant » ou « en mode non bloquant. » Les fonctions de chiffrement dans le mode de blocage \(ou synchrone\) ne retournent pas jusqu'à ce qu'ils puissent effectuer l'action.  On parle blocage car le socket de la fonction a été appelé ne peut rien faire — il est bloqué — jusqu'à ce que l'appel retourne.  Un appel à la fonction membre **Recevoir**, par exemple, peut prendre un temps arbitrairement long pour se terminer tandis qu'il attend que l'application émettrice effectue l'envoi \(autrement dit si vous utilisez `CSocket`, ou `CAsyncSocket` avec le blocage\).  Si un objet `CAsyncSocket` est en mode de blocage \(mode asynchrone\), l'instruction retourne immédiatement et le code d'erreur actuel, récupérable avec la fonction membre [GetLastError](../Topic/CAsyncSocket::GetLastError.md), est **WSAEWOULDBLOCK**, indiquant que l'appel aurait été bloqué s'il n'avait pas retourné immédiatement en raison de ce mode. \(`CSocket` ne retourne jamais **WSAEWOULDBLOCK**.  La classe gère le blocage pour vous.\)  
  
 Le comportement des sockets est différent dans les systèmes d'exploitation 32 bits et 64 bits \(tels que Windows 95 ou Windows 98\) et dans les systèmes d'exploitation 16 bits \(tels que Windows 3.1\).  Contrairement aux systèmes d'exploitation 16 bits, les systèmes d'exploitation 32 bits et 64 bits utilisent les travaux multitâches préemptif et fournissent le multithreading.  Sous les systèmes d'exploitation 32 bits et 64 bits, vous pouvez mettre les sockets dans des threads de travail distincts.  Un socket dans un thread peut se bloquer sans interférer avec d'autres activités dans votre application et sans passer de temps de calcul dans le blocage.  Pour plus d'informations sur la programmation multithread, consultez l'article [Multithreading](../parallel/multithreading-support-for-older-code-visual-cpp.md).  
  
> [!NOTE]
>  Dans les applications multithread, utilisez la nature bloquante de `CSocket` pour simplifier la création de programme sans affecter la réactivité de l'interface utilisateur.  Lorsque vous gérez des interventions de l'utilisateur dans le thread principal et le traitement `CSocket` dans d'autres threads, vous pouvez séparer ces opérations logiques.  Dans une application qui n'est pas multithread, ces deux opérations doivent être associées et gérées comme un seul thread, qui correspond généralement à `CAsyncSocket` de sorte que vous puissiez traiter les demandes de communication à la demande, ou en remplaçant `CSocket::OnMessagePending` pour gérer les actions utilisateur pendant la longue activité synchrone.  
  
 Le reste de cette discussion est destinée à des programmeurs ciblant les systèmes d'exploitation 16 bits :  
  
 Normalement, si vous utilisez `CAsyncSocket`, vous devez éviter d'utiliser des opérations bloquantes et fonctionner de manière asynchrone à la place.  Dans les opérations asynchrones, depuis le moment où vous recevez le code d'erreur de **WSAEWOULDBLOCK** après avoir appelé **Recevoir**, par exemple, vous attendez que votre fonction membre de `OnReceive` soit appelée pour vous informer que vous pouvez lire de nouveau.  Les appels asynchrones sont effectuées en appelant la fonction appropriée de rappel de notification de votre socket, par exemple [OnReceive](../Topic/CAsyncSocket::OnReceive.md).  
  
 Sous windows, les appels bloquants sont considérés comme une mauvaise pratique.  Par défaut, [CAsyncSocket](../mfc/reference/casyncsocket-class.md) prend en charge les appels asynchrones, vous devez gérer les blocages vous\-même en utilisant des notifications de rappel.  La classe [CSocket](../mfc/reference/csocket-class.md), en revanche, est synchrone.  Cela pompe des messages Windows et gère le blocage pour vous.  
  
 Pour plus d'informations sur les blocages, consultez la spécification de protocole Windows Sockets.  Pour plus d'informations sur les fonctions "ON", consultez [Protocole Windows : Notifications de socket](../mfc/windows-sockets-socket-notifications.md) et [Protocole Windows : Dérivation de classes de chiffrement](../mfc/windows-sockets-deriving-from-socket-classes.md).  
  
 Pour plus d'informations, consultez :  
  
-   [Windows Sockets : utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets : utilisation de sockets avec des archives](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets : arrière\-plan](../mfc/windows-sockets-background.md)  
  
-   [Windows Sockets : flux sockets](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets : datagramme sockets](../mfc/windows-sockets-datagram-sockets.md)  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)   
 [CAsyncSocket::OnSend](../Topic/CAsyncSocket::OnSend.md)