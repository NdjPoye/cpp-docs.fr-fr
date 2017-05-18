---
title: Linger, Structure | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- LINGER
dev_langs:
- C++
helpviewer_keywords:
- LINGER structure
ms.assetid: 1fb1c5bf-a64e-4a6c-89d6-1734e4fdbb1b
caps.latest.revision: 11
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: ed880c29f43c074ba61f52b11f812a79eece0416
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="linger-structure"></a>LINGER, structure
Le `LINGER` structure est utilisée pour la manipulation de la **SO_LINGER** et **SO_DONTLINGER** options de `CAsyncSocket::GetSockOpt`.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct linger {  
    u_short l_onoff;            // option on/off  
    u_short l_linger;           // linger time  
};  
```  
  
## <a name="remarks"></a>Remarques  
 Définition de la **SO_DONTLINGER** option empêche le blocage sur la fonction membre **fermer** en attendant que les données non envoyées à envoyer. Cette option est équivalente à la définition **SO_LINGER** avec **l_onoff** la valeur 0.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winsock2.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CAsyncSocket::GetSockOpt](../../mfc/reference/casyncsocket-class.md#getsockopt)   
 [CAsyncSocket::SetSockOpt](../../mfc/reference/casyncsocket-class.md#setsockopt)


