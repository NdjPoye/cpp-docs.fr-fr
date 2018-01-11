---
title: CDataConnection::CDataConnection | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CDataConnection.CDataConnection
- ATL.CDataConnection.CDataConnection
- CDataConnection::CDataConnection
- ATL::CDataConnection::CDataConnection
dev_langs: C++
helpviewer_keywords: CDataConnection class, constructor
ms.assetid: ac25c9a0-44d3-4083-b13f-76c07772e12d
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: fd2deb3978ef3c01d5d70297599be54aabb90cb6
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cdataconnectioncdataconnection"></a>CDataConnection::CDataConnection
Instancie et initialise un `CDataConnection` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      CDataConnection();   
CDataConnection(  
   const CDataConnection &ds  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `ds`  
 [in] Une référence à une connexion de données existante.  
  
## <a name="remarks"></a>Notes  
 La première substitution crée un nouveau `CDataConnection` objet avec les paramètres par défaut.  
  
 La deuxième substitution crée un nouveau `CDataConnection` objet avec les paramètres équivalents à l’objet de connexion de données vous spécifiez.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataConnection, classe](../../data/oledb/cdataconnection-class.md)