---
title: Sockaddr_in, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SOCKADDR_IN
dev_langs:
- C++
helpviewer_keywords:
- SOCKADDR_IN structure
ms.assetid: e8cd7c34-78bd-4e28-a990-eb3ca070b7a6
caps.latest.revision: 13
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: a82768750e6a7837bb81edd8a51847f83c294c20
ms.openlocfilehash: a1283740c0abb0538e5912efa11500c46b45bb9f
ms.lasthandoff: 04/04/2017

---
# <a name="sockaddrin-structure"></a>SOCKADDR_IN, structure
Dans la famille d’adresses Internet, le `SOCKADDR_IN` structure est utilisée par Windows Sockets pour spécifier une adresse de point de terminaison local ou distant auquel se connecter un socket.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct sockaddr_in{  
    short sin_family;  
    unsigned short sin_port;  
struct in_addr sin_addr;  
    char sin_zero[8];  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 *sin_family*  
 Famille d’adresses (doit être **AF_INET**).  
  
 *sin_port*  
 Port IP.  
  
 *sin_addr*  
 Adresse IP.  
  
 *Sin_zero*  
 Remplissage afin que structure de la même taille que `SOCKADDR`.  
  
## <a name="remarks"></a>Notes  
 C’est la forme de la `SOCKADDR` structure spécifique pour la famille d’adresses Internet et peut être converti en `SOCKADDR`.  
  
 Le composant d’adresse IP de cette structure est de type **IN_ADDR**. Le **IN_ADDR** structure est définie dans le fichier d’en-tête Windows Sockets WINSOCK. H comme suit :  
  
```  
struct in_addr {
    union {
        struct {  
            unsigned char s_b1, s_b2, s_b3, s_b4;  
        } S_un_b;  
        struct {  
            unsigned short s_w1, s_w2;
        } S_un_w;
        unsigned long S_addr;
    } S_un;  
};  
```  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winsock2.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [SOCKADDR, structure](../../mfc/reference/sockaddr-structure.md)

