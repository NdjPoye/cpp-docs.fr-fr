---
title: CDataConnection::operator CDataSource * | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource*
- CDataConnection::operatorCDataSource*
- CDataConnection.operatorCDataSource*
- operatorCDataSource*
dev_langs:
- C++
helpviewer_keywords:
- CDataSource* operator
- operator * (CDataSource)
ms.assetid: 9118e324-e68d-45c5-a791-03f041d420ed
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 60eba58d4a3884b191afdca1da0934453a303d8c
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-cdatasource"></a>CDataConnection::operator CDataSource*
Retourne un pointeur vers la relation contenant-contenu `CDataSource` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
operator const CDataSource*() throw();  
  
```  
  
## <a name="remarks"></a>Notes  
 Cet opérateur retourne un pointeur vers la relation contenant-contenu `CDataSource` objet, ce qui vous permet de passer un `CDataConnection` objet sur lequel un `CDataSource` pointeur est attendu.  
  
 Consultez [opérateur CDataSource &](../../data/oledb/cdataconnection-operator-cdatasource-amp.md) pour obtenir un exemple d’utilisation.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataConnection (classe)](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource&](../../data/oledb/cdataconnection-operator-cdatasource-amp.md)