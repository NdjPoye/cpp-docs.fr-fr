---
title: "Windows Sockets : Sockets datagramme | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs: C++
helpviewer_keywords:
- sockets [MFC], datagram
- Windows Sockets [MFC], bi-directional data flow
- datagram sockets [MFC]
- Windows Sockets [MFC], datagram
- sockets [MFC], bi-directional data flow
ms.assetid: bec16a1c-74c0-4ff9-8c18-c2d87897d264
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d004bae6e4a15ab9c2aa76da76eb450c92572199
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="windows-sockets-datagram-sockets"></a>Windows Sockets : sockets datagramme
Cet article décrit les sockets datagramme, un des deux types de Windows Socket disponibles. (L’autre type est le [socket flux](../mfc/windows-sockets-stream-sockets.md).)  
  
 Sockets datagramme prend en charge un flux de données bidirectionnel qui n’est pas garanti pour être séquencées ni non dupliqué. Datagrammes également ne sont pas obligatoirement fiable ; elles peuvent n’arrivent pas. Datagramme données arrivent en désordre et éventuellement en double, mais les limites d’enregistrement dans les données sont conservées, tant que les enregistrements sont plus petites que la limite de taille interne du destinataire. Vous êtes chargé de gérer la mise en séquence et la fiabilité. (La fiabilité a tendance à être correctement sur les réseaux locaux [LAN] mais moins étendu etc. réseaux [WAN], tel qu’Internet).  
  
 Les datagrammes sont « sans connexion », autrement dit, aucune connexion explicite n’est établie ; vous envoyez un message de datagramme à un socket spécifié et que vous pouvez recevoir des messages à partir d’un socket spécifié.  
  
 Un exemple d’un socket datagramme est une application qui conserve les horloges système sur le réseau synchronisé. Cet exemple illustre une fonctionnalité supplémentaire de sockets datagramme au moins certains paramètres : diffuser des messages à un grand nombre d’adresses réseau.  
  
 Sockets datagramme soient préférable que les sockets flux orienté par enregistrement de données. Pour plus d’informations sur les sockets datagramme, consultez la spécification Windows Sockets, disponible dans le SDK Windows.  
  
## <a name="see-also"></a>Voir aussi  
 [Windows Sockets dans MFC](../mfc/windows-sockets-in-mfc.md)   
 [Windows Sockets : arrière-plan](../mfc/windows-sockets-background.md)

