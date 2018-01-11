---
title: CDataConnection::OpenNewSession | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
dev_langs: C++
helpviewer_keywords: OpenNewSession method
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 4d89fe8af9f2d06974f09439c1fc51be11df78f7
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectionopennewsession"></a>CDataConnection::OpenNewSession
Ouvre une nouvelle session à l’aide de la source de données de l’objet de connexion en cours.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT OpenNewSession(   
   CSession & session    
) throw( );  
```  
  
#### <a name="parameters"></a>Paramètres  
 `session`  
 [entrée/sortie] Une référence à l’objet de la nouvelle session.  
  
 **Remarques**  
 La nouvelle session utilise un objet de source de données de contenu de l’objet de connexion en cours en tant que son parent et peut accéder à tous les mêmes informations que la source de données.  
  
## <a name="return-value"></a>Valeur de retour  
 `HRESULT` standard.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataConnection, classe](../../data/oledb/cdataconnection-class.md)