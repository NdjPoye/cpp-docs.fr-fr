---
title: "Comment WinInet facilite la création d’Applications de Client Internet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], vs. WinInet
- WinInet classes [MFC], vs. WinSock
- WinInet classes [MFC], Internet client applications
ms.assetid: dc0f9f47-3184-4e7a-8074-2c63e0359885
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 9c79404f296df09afb177930897064b8455217d1
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="how-wininet-makes-it-easier-to-create-internet-client-applications"></a>Comment WinInet facilite la création d'applications clientes Internet
Les Extensions Win32 Internet, ou WinInet, donnent accès à des protocoles Internet courants, y compris HTTP, FTP et gopher. À l’aide de WinInet, vous pouvez écrire des applications clientes Internet à un niveau supérieur de la programmation, sans avoir à gérer avec WinSock, TCP/IP ou les détails des protocoles Internet spécifiques. WinInet fournit un ensemble cohérent de fonctions pour les trois protocoles, avec une interface API Win32 familière. Cette cohérence réduit les modifications du code que vous devez faire si le protocole sous-jacent change (par exemple, à partir de FTP sur HTTP).  
  
 Visual C++ fournit deux façons d’utiliser WinInet. Vous pouvez appeler directement les fonctions Win32 Internet (consultez la documentation OLE dans le SDK Windows pour plus d’informations) ou vous pouvez utiliser WinInet via la [classes WinInet MFC](../mfc/mfc-classes-for-creating-internet-client-applications.md).  
  
 **Vous pouvez utiliser WinInet pour :**  
  
-   Télécharger des pages HTML.  
  
     HTTP est un protocole utilisé pour transférer des pages HTML à partir d’un serveur vers un navigateur client.  
  
-   Envoyer des demandes FTP pour télécharger ou de télécharger des fichiers ou d’obtenir des listes de répertoires.  
  
     Une demande par défaut est une connexion anonyme pour télécharger un fichier.  
  
-   Utilisez le système de menus de gopher pour accéder aux ressources sur Internet.  
  
     Éléments de menu peuvent contenir plusieurs types, y compris d’autres menus, une base de données indexé, que vous pouvez effectuer une recherche, un groupe de discussion ou un fichier.  
  
 Pour les trois protocoles, établir une connexion, effectuer des demandes au serveur et fermer la connexion.  
  
 **Les classes WinInet MFC facilitent les :**  
  
-   Lire les informations à partir de serveurs HTTP, FTP et gopher aussi facilement que la lecture des fichiers à partir d’un disque dur.  
  
-   Utiliser les protocoles HTTP, FTP et gopher sans programmer directement WinSock ni TCP/IP.  
  
     Les développeurs qui utilisent les fonctions Win32 Internet n’avez pas besoin de se familiariser avec TCP/IP ou de Windows Sockets. Vous pouvez toujours programmer au niveau du socket, à l’aide de protocoles WinSock et TCP/IP directement, mais il est plus facile à utiliser les classes WinInet MFC pour l’accès HTTP, FTP et les protocoles gopher via Internet. Pour de nombreuses opérations courantes, les développeurs est inutile de connaître les détails du protocole particulier qu’ils utilisent.  
  
 Nombre d’opérations qui peut être effectuée par votre ordinateur en tant que client à d’autres ordinateurs sur Internet peut prendre un certain temps. La vitesse de ces opérations est généralement limitée par la vitesse de votre connexion réseau, mais ils peuvent également être affectées par tout autre trafic réseau et la complexité de l’opération. Connexion à un serveur FTP distant, par exemple, nécessite que votre ordinateur tout d’abord rechercher le nom de ce serveur pour trouver son adresse. Votre application tente alors de se connecter au serveur à l’adresse. Une fois que la connexion est ouverte, votre ordinateur et le serveur à distance initie une conversation avec le protocole de transfert de fichier avant de pouvoir utiliser réellement la connexion pour récupérer des fichiers.  
  
## <a name="see-also"></a>Voir aussi  
 [Extension Internet Win32 (WinInet)](../mfc/win32-internet-extensions-wininet.md)   
 [Comment MFC facilite la création d’applications clientes Internet](../mfc/how-mfc-makes-it-easier-to-create-internet-client-applications.md)

