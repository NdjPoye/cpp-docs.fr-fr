---
title: "Windows Sockets&#160;: sockets datagramme | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "sockets datagramme (C++)"
  - "sockets (C++), flux de données bidirectionnel"
  - "sockets (C++), datagramme"
  - "Windows Sockets (C++), flux de données bidirectionnel"
  - "Windows Sockets (C++), datagramme"
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Windows Sockets&#160;: sockets datagramme
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article décrit les datagramme de sockets, l'un des deux types de Windows Socket disponibles. \(L'autre type est [flux de socket](../mfc/windows-sockets-stream-sockets.md).\)  
  
 Les datagrammes de sockets prennent en charge un flux bidirectionnel qui n'est pas forcément en séquence ou sans doublons.  Les datagrammes ne sont pas garantis fiables ; il se peut qu'ils n'arrivent pas.  Les données de datagramme peuvent arriver en désordre et éventuellement en doublons, mais les limites de l'enregistrement de données sont conservées, tant que les enregistrements sont plus petits que la limite interne de la taille du récepteur.  Vous êtes chargé de la gestion du séquencement et de la fiabilité. \(La fiabilité a tendance à être bonne sur les réseaux locaux \[LAN\] mais moins sur les réseaux étendus \[WAN\], comme Internet.\)  
  
 Les datagrammes sont « sans connexion », c'est\-à\-dire qu'aucune connexion explicite n'est créée ; vous envoyez un message de datagramme à un socket spécifié et vous recevez des messages d'un socket spécifié.  
  
 Un exemple de datagramme de socket est une application qui fait en srote que les horloges des systèmes du réseau restent synchronisées.  Ceci illustre une capacité supplémentaire des datagrammes de sockets dans au moins quelques options : diffuser des messages à un grand nombre d'adresses réseau.  
  
 Les datagrammes de socket sont plus performants que les flux de socket pour des données orientées vers l'enregistrement.  Pour plus d'informations sur les datagrammes de socket, consultez la spécification de Windows Socket, disponible dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)   
 [Windows Sockets : arrière\-plan](../mfc/windows-sockets-background.md)