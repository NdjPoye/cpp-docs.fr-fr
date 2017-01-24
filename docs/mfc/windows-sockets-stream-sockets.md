---
title: "Windows Sockets&#160;: sockets flux | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "sockets (C++), sockets flux"
  - "sockets flux (C++)"
  - "Windows Sockets (C++), sockets flux"
ms.assetid: 31faaa34-a995-493f-a30b-b8115293d619
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Windows Sockets&#160;: sockets flux
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit les flux de sockets, l'un des deux types de Windows Socket disponibles. \(L'autre type est le [datagramme de socket](../mfc/windows-sockets-datagram-sockets.md).\)  
  
 Les flux de sockets fournissent pour un flux de données sans limites d'enregistrement: un flux d'octets pouvant être bidirectionnels \(l'application est totalement bidirectionnelle: elle peut transmettre et recevoir à travers le socket\).  Les flux peut être reliés afin de fournir des données organisées et non dupliquées. \(« Ordonnancé » signifie que des paquets sont remis dans l'ordre envoyé. « Non dupliqué » signifie que vous obtenez un paquet particulier une seule fois. La réception des messages de flux est garantie, et les flux sont bien adaptés pour gérer de grands nombre de données.  
  
 La couche de transport réseau peut se diviser ou regrouper des données dans des paquets de taille raisonnable.  La classe d' `CSocket` gère l'emballage et la décompression à votre place.  
  
 Les flux sont basés sur des connexions explicites: le socket A demande une connexion au socket B; le socket B accepte ou refuse la demande de connexion.  
  
 Un appel téléphonique fournit une bonne analogie d'un flux.  Dans des conditions normales, la partie réceptrice entend ce que vous indiquez dans l'ordre que vous lui indiquez, sans duplication ou perte.  Les sockets de flux sont appropriés, par exemple, pour les implémentations telles que Protocole de Transfert de Fichiers \(FTP\), qui permet de transférer des fichier ASCII ou binaires de taille arbitraire.  
  
 Les sockets de flux sont préférables aux sockets de datagramme lorsque l'arrivée des données doivent être nécessairement garanties et lorsque la taille des données est importante.  Pour plus d'informations sur les sockets de flux, consultez la spécification de sockets Windows.  La spécification est disponible dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
 L'utilisation de sockets de flux peut être supérieure aux applications conçues pour utiliser un socket de datagramme pour la distribution à tous les sockets destinataires sur le réseau car  
  
-   Le modèle de diffusion est soumis à des problèmes d'inondation \(ou « tempête »\) du réseau.  
  
-   Le modèle client\-serveur adopté par la suite est plus efficace.  
  
-   Le modèle de flux de données fournit un transfert de données fiable, là où le modèle de datagramme échoue.  
  
-   Le modèle final bénéficie de la capacité de communiquer entre les applications de Socket Unicode et ANSI qui classent les prêts CArchive à la classe CSocket.  
  
    > [!NOTE]
    >  Si vous utilisez la classe `CSocket`, vous devez utiliser un flux de données.  Une assertion de MFC échoue si vous spécifiez le type de socket comme **SOCK\_DGRAM**.  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)   
 [Windows Sockets : arrière\-plan](../mfc/windows-sockets-background.md)