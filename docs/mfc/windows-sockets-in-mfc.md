---
title: Windows Sockets dans MFC | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- WINSOCK.DLL
- sockets [MFC], programming models
- MFC, Windows Sockets
- Windows Sockets [MFC], MFC support
- Windows Sockets [MFC], programming models
- WSOCK32.DLL
- sockets [MFC], MFC
ms.assetid: 1f3c476a-9c68-49fe-9a25-d22971a334d0
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bdade770449b7ae5db9db9a170198b81cbeaf970
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-in-mfc"></a>Windows Sockets dans MFC
> [!NOTE]
>  MFC prend en charge Windows Sockets 1, mais ne prend pas en charge [Windows Sockets 2](http://msdn.microsoft.com/library/windows/desktop/ms740673). Windows Sockets 2 tout d’abord fourni avec Windows 98 et est la version fournie avec Windows 2000.  
  
 MFC fournit deux modèles pour l’écriture de programmes de communication réseau avec Windows Sockets, représentées de deux classes MFC. Cet article décrit ces modèles et des informations détaillées MFC sockets prise en charge. Un « socket » est un point de terminaison de communication : un objet via lequel votre application communique avec d’autres applications Windows Sockets sur un réseau.  
  
 Pour plus d’informations sur les Sockets Windows, y compris une explication du concept de socket, consultez [Windows Sockets : arrière-plan](../mfc/windows-sockets-background.md).  
  
##  <a name="_core_sockets_programming_models"></a>Modèles de programmation de sockets  
 Les modèles de programmation MFC Windows Sockets deux sont pris en charge par les classes suivantes :  
  
-   `CAsyncSocket`  
  
     Cette classe encapsule l’API Windows Sockets. [CAsyncSocket](../mfc/reference/casyncsocket-class.md) est destiné aux programmeurs qui connaître la programmation réseau et la flexibilité de programmation directement dans l’API sockets mais également la commodité de fonctions de rappel de notification des événements réseau. Packaging sockets sous forme d’orientée objet pour une utilisation en C++, l’abstraction uniquement supplémentaire de que cette classe fournit convertit certains messages Windows liés aux sockets en rappels. Pour plus d’informations, consultez [Windows Sockets : Notifications de Socket](../mfc/windows-sockets-socket-notifications.md).  
  
-   `CSocket`  
  
     Cette classe, dérivée de `CAsyncSocket`, fournit un niveau d’abstraction plus élevé pour travailler avec des sockets via une MFC [CArchive](../mfc/reference/carchive-class.md) objet. Utilisation d’un socket avec une archive considérablement est semblable à l’aide du protocole de sérialisation du MFC fichier. Cela facilite l’utilisation par rapport à la `CAsyncSocket` modèle. [CSocket](../mfc/reference/csocket-class.md) hérite de nombreuses fonctions membres de `CAsyncSocket` qui encapsulent les API Windows Sockets ; vous devez utiliser certaines de ces fonctions et de comprendre la programmation généralement de sockets. Mais `CSocket` gère de nombreux aspects de la communication que vous devriez vous-même à l’aide de l’API brute ou classe `CAsyncSocket`. Plus important encore, `CSocket` fournit un blocage (avec traitement en arrière-plan des messages Windows), qui est indispensable au fonctionnement synchrone de `CArchive`.  
  
 Création et utilisation de `CSocket` et `CAsyncSocket` objets est décrit dans [Windows Sockets : utilisation de Sockets avec des Archives](../mfc/windows-sockets-using-sockets-with-archives.md) et [Windows Sockets : à l’aide de classe CAsyncSocket](../mfc/windows-sockets-using-class-casyncsocket.md).  
  
##  <a name="_core_mfc_socket_samples_and_windows_sockets_dlls"></a>DLL de Sockets Windows  
 Les systèmes d’exploitation Microsoft Windows fournissent les bibliothèques de liens dynamiques (DLL) de Windows Sockets. Visual C++ fournit les fichiers d’en-tête approprié et les bibliothèques et la spécification Windows Sockets.  
  
> [!NOTE]
>  Sous Windows NT et Windows 2000, prise en charge de Windows Sockets pour les applications 16 bits est basée sur WINSOCK. DLL. Pour les applications 32 bits, la prise en charge incombe à WSOCK32. DLL. Les API fournies sont identiques, sauf que les versions 32 bits ont des paramètres élargis à 32 bits. Sous Win32, la sécurité des threads sont fourni.  
  
 Pour plus d’informations sur les Sockets Windows, consultez :  
  
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
  
## <a name="see-also"></a>Voir aussi  
 [Windows Sockets](../mfc/windows-sockets.md)

