---
title: "LINGER, structure | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "LINGER"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LINGER (structure)"
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# LINGER, structure
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

La structure `LINGER` est utilisée pour manipuler les options **SO\_LINGER** et **SO\_DONTLINGER** de `CAsyncSocket::GetSockOpt`.  
  
## Syntaxe  
  
```  
  
      struct linger {  
   u_short l_onoff;            // option on/off  
   u_short l_linger;           // linger time  
};  
```  
  
## Notes  
 Définir l'option **SO\_DONTLINGER** empêche de maintenir la sélection sur la fonction membre **Fermer** en attendant que les données à envoyer soient envoyées.  Cette option revient à définir **SO\_LINGER** avec **l\_onoff** défini sur 0.  
  
## Configuration requise  
 **En\-tête :** winsock2.h  
  
## Voir aussi  
 [Structures, styles, rappels et tables de messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../Topic/CAsyncSocket::GetSockOpt.md)   
 [CAsyncSocket::SetSockOpt](../Topic/CAsyncSocket::SetSockOpt.md)