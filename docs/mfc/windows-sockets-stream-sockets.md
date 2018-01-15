---
title: "Windows Sockets : Sockets de flux | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- Windows Sockets [MFC], stream sockets
- sockets [MFC], stream sockets
- stream sockets [MFC]
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: bc112bd3cfbf1194a2898afecb513edcbc456747
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="windows-sockets-stream-sockets"></a>Windows Sockets : sockets flux
Cet article décrit les flux de sockets, l'un des deux types de Windows Socket disponibles. (L’autre type est le [socket datagramme](../mfc/windows-sockets-datagram-sockets.md).)  
  
 Les flux de sockets fournissent pour un flux de données sans limites d'enregistrement : un flux d'octets pouvant être bidirectionnel (l'application est totalement bidirectionnelle : elle peut transmettre et recevoir via le socket). Les flux peut être reliés afin de fournir des données organisées et non dupliquées. ("Ordonnancé" signifie que des paquets sont remis dans l'ordre envoyé. "Non dupliqué » signifie que vous obtenez un paquet particulier une seule fois. La réception des messages de flux est garantie, et les flux sont bien adaptés pour gérer de grandes quantités de données.  
  
 La couche de transport réseau peut se diviser ou regrouper des données dans des paquets de taille raisonnable. La classe `CSocket` gère la compression et la décompression à votre place.  
  
 Les flux sont basés sur des connexions explicites : le socket A demande une connexion au socket B ; le socket B accepte ou refuse la demande de connexion.  
  
 Un appel téléphonique fournit une bonne analogie d'un flux. Dans des conditions normales, la partie réceptrice entend ce que vous indiquez dans l'ordre que vous lui indiquez, sans duplication ni perte. Les sockets de flux sont appropriés, par exemple, pour les implémentations telles que le protocole FTP (File Transfer Protocol), qui permet de transférer des fichier ASCII ou binaires de taille arbitraire.  
  
 Les sockets de flux sont préférables aux sockets datagramme lorsque l'arrivée des données doit être nécessairement garanti et que la taille des données est importante. Pour plus d'informations sur les sockets de flux, consultez la spécification de sockets Windows. La spécification est disponible dans le SDK Windows.  
  
 L'utilisation de sockets de flux peut être supérieure aux applications conçues pour utiliser un socket de datagramme pour la distribution à tous les sockets destinataires sur le réseau.  
  
-   Le modèle de diffusion est soumis à des problèmes de surcharge (ou "tempête") du réseau.  
  
-   Le modèle client-serveur adopté par la suite est plus efficace.  
  
-   Le modèle de flux de données fournit un transfert de données fiable, là où le modèle de datagramme échoue.  
  
-   Le modèle final bénéficie de la capacité de communiquer entre les applications Socket Unicode et ANSI que la classe CArchive prête à la classe CSocket.  
  
    > [!NOTE]
    >  Si vous utilisez la classe `CSocket`, vous devez utiliser un flux de données. Une assertion MFC échoue si vous spécifiez le type de socket **SOCK_DGRAM**.  
  
## <a name="see-also"></a>Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)   
 [Windows Sockets : arrière-plan](../mfc/windows-sockets-background.md)
