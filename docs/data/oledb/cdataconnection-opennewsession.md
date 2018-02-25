---
title: CDataConnection::OpenNewSession | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataConnection.OpenNewSession
- ATL.CDataConnection.OpenNewSession
- ATL::CDataConnection::OpenNewSession
- OpenNewSession
- CDataConnection::OpenNewSession
dev_langs:
- C++
helpviewer_keywords:
- OpenNewSession method
ms.assetid: 0a70e573-9498-4ca7-b524-45666dc7b0a3
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 65b20285bc46fddb8002a95ff77ce21c7a1018e5
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionopennewsession"></a>CDataConnection::OpenNewSession
Ouvre une nouvelle session à l’aide de la source de données de l’objet de connexion en cours.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
HRESULT OpenNewSession(CSession & session) throw();  
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