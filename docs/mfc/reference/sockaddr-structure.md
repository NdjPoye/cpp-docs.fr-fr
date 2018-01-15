---
title: Structure SOCKADDR | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SOCKADDR
dev_langs: C++
helpviewer_keywords: SOCKADDR structure [MFC]
ms.assetid: df1ed66a-f4b8-43f8-8db8-8c2533d25f68
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 55b310ec83aae35c7386d61849663752811651d4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="sockaddr-structure"></a>SOCKADDR, structure
Le `SOCKADDR` structure est utilisée pour stocker une adresse IP (Internet Protocol) pour un ordinateur participant à une communication de Windows Sockets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
struct sockaddr {  
    unsigned short sa_family;  
    char sa_data[14];  
};  
```  
  
#### <a name="parameters"></a>Paramètres  
 *sa_family*  
 Famille d’adresses de socket.  
  
 *sa_data*  
 Taille maximale de toutes les structures d’adresse de socket différentes.  
  
## <a name="remarks"></a>Notes  
 Kit de développement de Sockets de TCP/IP Microsoft prend uniquement en charge les domaines d’adresse Internet. Pour remplir les valeurs pour chaque partie d’une adresse en fait, vous utilisez la `SOCKADDR_IN` structure de données, qui est spécifiquement pour ce format d’adresse. Le `SOCKADDR` et `SOCKADDR_IN` des structures de données ont la même taille. Vous effectuez un cast simplement pour basculer entre les types de structure.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** winsock2.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [Sockaddr_in, Structure](../../mfc/reference/sockaddr-in-structure.md)   
 [CAsyncSocket::Create](../../mfc/reference/casyncsocket-class.md#create)   
 [CSocket::Create](../../mfc/reference/csocket-class.md#create)

