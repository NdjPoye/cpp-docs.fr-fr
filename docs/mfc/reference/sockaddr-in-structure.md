---
title: "SOCKADDR_IN, structure | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "SOCKADDR_IN"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "SOCKADDR_IN (structure)"
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# SOCKADDR_IN, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Dans la famille d'adresses Internet, la structure `SOCKADDR_IN` est utilisée par Windows Sockets pour spécifier une adresse de point de terminaison locale ou distante à laquelle connecter un socket.  
  
## Syntaxe  
  
```  
  
      struct sockaddr_in{  
   short sin_family;  
   unsigned short sin_port;  
   struct in_addr sin_addr;  
   char sin_zero[8];  
};  
```  
  
#### Paramètres  
 *sin\_family*  
 Famille d'adresses \(doit être **AF\_INET**\).  
  
 *sin\_port*  
 Port IP.  
  
 *sin\_addr*  
 Adresse IP.  
  
 *sin\_zero*  
 Remplissage pour donner à la structure la même taille que `SOCKADDR`.  
  
## Notes  
 Forme de la structure `SOCKADDR` spécifique à la famille d'adresses Internet et un cast en `SOCKADDR` peut lui être appliqué.  
  
 Le composant d'adresse IP de cette structure est du type **IN\_ADDR**.  La structure **IN\_ADDR** est définie dans le fichier d'en\-tête WINSOCK.H Windows Sockets, comme suit :  
  
 `struct   in_addr {`  
  
 `union   {`  
  
 `struct{`  
  
 `unsigned  char   s_b1,`  
  
 `s_b2,`  
  
 `s_b3,`  
  
 `s_b4;`  
  
 `}  S_un_b;`  
  
 `struct  {`  
  
 `unsigned  short  s_w1,`  
  
 `s_w2;`  
  
 `}  S_un_w;`  
  
 `unsigned long  S_addr;`  
  
 `} S_un;`  
  
 `};`  
  
## Configuration requise  
 **En\-tête :** winsock2.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR, structure](../../mfc/reference/sockaddr-structure.md)