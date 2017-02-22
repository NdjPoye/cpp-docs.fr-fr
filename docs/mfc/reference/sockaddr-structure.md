---
title: "SOCKADDR, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SOCKADDR"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SOCKADDR (structure)"
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 13
---
# SOCKADDR, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `SOCKADDR` est utilisée pour stocker une adresse de protocole Internet \(IP\) pour un ordinateur participant à une communication Windows Sockets.  
  
## Syntaxe  
  
```  
  
      struct sockaddr {  
   unsigned short sa_family;  
   char sa_data[14];  
};  
```  
  
#### Paramètres  
 *sa\_family*  
 Famille d'adresses de socket .  
  
 *sa\_data*  
 Taille maximale de toutes les différentes structures d'adresse de socket.  
  
## Notes  
 Le Kit du développeur de sockets Microsoft TCP\/IP prend uniquement en charge les champs d'adresse Internet.  Pour réellement remplir des valeurs pour chaque partie d'une adresse, vous utilisez la structure de données de `SOCKADDR_IN`, qui est spécifiquement pour cette structure d'adresse.  Les structures de données `SOCKADDR` et `SOCKADDR_IN` sont de même taille.  Vous distribuez simplement pour passer d'un type de structure à un autre.  
  
## Configuration requise  
 **En\-tête :** winsock2.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR\_IN, structure](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../Topic/CAsyncSocket::Create.md)   
 [CSocket::Create](../Topic/CSocket::Create.md)