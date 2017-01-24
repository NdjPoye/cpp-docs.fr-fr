---
title: "Windows Sockets dans MFC | Microsoft Docs"
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
  - "MFC (C++), Windows Sockets"
  - "sockets (C++), MFC"
  - "sockets (C++), modèles de programmation"
  - "Windows Sockets (C++), prise en charge des MFC"
  - "Windows Sockets (C++), modèles de programmation"
  - "WINSOCK.DLL"
  - "WSOCK32.DLL"
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets dans MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  MFC prend en charge Windows Socket 1 mais ne prend pas en charge [Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673).  Windows Sockets 2 fut d'abord fourni avec Windows 98 et est la version est incluse dans Windows 2000.  
  
 MFC fournit deux modèles pour écrire des programmes de communication réseau avec Windows Sockets, incorporés dans deux classes de MFC.  Cet article décrit ces modèles et davantages de détails de la prise en charge du protocole MFC.  Un « socket » est un point de terminaison de communication : objet dans lequel l'application communique avec d'autres applications de Windows Socket sur un réseau.  
  
 Pour plus d'informations sur Windows Sockets, notamment une explication du concept de socket, consultez [Windows Sockets : Arrière\-plan](../mfc/windows-sockets-background.md).  
  
##  <a name="_core_sockets_programming_models"></a> Modèles de programmation de sockets  
 Les deux modèles de programmation de sockets MFC Windows sont pris en charge par les classes suivantes :  
  
-   `CAsyncSocket`  
  
     Cette classe encapsule l'API de sockets Windows.  [CAsyncSocket](../mfc/reference/casyncsocket-class.md) est pour les programmeurs qui connaissent la programmation réseau et veulent la flexibilité de programmer directement sur l'API de sockets mais souhaitent aussi simplifier les fonctions de rappel pour les notifications d'événements réseau.  Autres que les sockets d'empaquetage des formulaires orientés objet à utiliser en C\+\+, la seule abstraction supplémentaire que la classe offre convertit certains messages windows liés aux sockets en rappels.  Pour plus d'informations, consultez [Protocole Windows : Notifications de socket](../mfc/windows-sockets-socket-notifications.md).  
  
-   `CSocket`  
  
     Cette classe dérivée, `CAsyncSocket` fournit une abstraction de niveau supérieur pour utiliser des sockets dans un objet MFC [CArchive](../mfc/reference/carchive-class.md).  L'utilisation d'un socket avec une archive ressemble fortement à l'utilisation d'un protocole de sérialisation de fichier dans MFC.  Cela le rend plus simple à utiliser que le modèle `CAsyncSocket`.  [CSocket](../mfc/reference/csocket-class.md) hérite de nombreuses fonctions membres de`CAsyncSocket` qui encapsulent les API de Windows Sockets ; vous devez utiliser certaines de ces fonctions et comprendre la programmation avec socket de manière générale.  Mais `CSocket` gère de nombreux aspects de la communication que vous devriez faire vous\-même en utilisant l'API brute ou la classe `CAsyncSocket`.  Avant tout, `CSocket` fournit un blocage \(avec traitement en arrière\-plan des messages Windows\), qui est essentiel au fonctionnement synchrone de `CArchive`.  
  
 La création et l'utilisation de `CSocket` et des objets `CAsyncSocket` est décrit dans [Windows Sockets : utilisation de sockets d'archive](../mfc/windows-sockets-using-sockets-with-archives.md) et [Windows Sockets : Utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md).  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a> Windows Sockets DLLs  
 Les systèmes d'exploitation Microsoft Windows fournissent des bibliothèques de liens dynamiques \(DLL\) Windows.  Visual C\+\+ fournit les fichiers d'en\-tête et les bibliothèques appropriés et la spécification Windows Sockets.  
  
> [!NOTE]
>  Sous Windows NT et Windows 2000, la prise en charge de Windows pour les applications 16 bits est basée sur WINSOCK.DLL.  Pour les applications 32 bits, la prise en charge est dans WSOCK32.DLL.  Les API fournies sont identiques à la différence que les versions 32 bits ont des paramètres élargis à 32 bits.  Sous Win32, la sécurité des threads est assurée.  
  
 Pour plus d'informations sur les Windows Sockets, consultez .  
  
-   [Windows Sockets : sockets flux](../mfc/windows-sockets-stream-sockets.md)  
  
-   [Windows Sockets : sockets datagramme](../mfc/windows-sockets-datagram-sockets.md)  
  
-   [Windows Sockets : utilisation de sockets avec des archives](../mfc/windows-sockets-using-sockets-with-archives.md)  
  
-   [Windows Sockets : ordre des opérations](../mfc/windows-sockets-sequence-of-operations.md)  
  
-   [Windows Sockets : exemple de sockets utilisant des archives](../mfc/windows-sockets-example-of-sockets-using-archives.md)  
  
-   [Windows Sockets : fonctionnement des sockets avec des archives](../mfc/windows-sockets-how-sockets-with-archives-work.md)  
  
-   [Windows Sockets : utilisation de la classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md)  
  
-   [Windows Sockets : dérivation à partir des classes de sockets](../mfc/windows-sockets-deriving-from-socket-classes.md)  
  
-   [Windows Sockets : notifications de socket](../mfc/windows-sockets-socket-notifications.md)  
  
-   [Windows Sockets : blocage](../mfc/windows-sockets-blocking.md)  
  
-   [Windows Sockets : classement des octets](../mfc/windows-sockets-byte-ordering.md)  
  
-   [Windows Sockets : conversion de chaînes](../mfc/windows-sockets-converting-strings.md)  
  
-   [Windows Sockets : ports et adresses de socket](../mfc/windows-sockets-ports-and-socket-addresses.md)  
  
## Voir aussi  
 [Windows Sockets](../mfc/windows-sockets.md)