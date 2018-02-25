---
title: CDataConnection::operator CDataSource&amp; | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDataSource&
- CDataConnection.operatorCDataSource&
- operatorCDataSource&
- CDataConnection::operatorCDataSource&
dev_langs:
- C++
helpviewer_keywords:
- CDataSource& operator
- operator & (CDataSource)
ms.assetid: 852faeee-f1b1-4465-9828-b261d1edf022
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 255d1fe1d6363277c300fee134c5c41473ee8c3b
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdataconnectionoperator-cdatasourceamp"></a>CDataConnection::operator CDataSource&amp;
Retourne une référence à la relation contenant-contenu `CDataSource` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
operator const CDataSource&() throw();  
  
```  
  
## <a name="remarks"></a>Notes  
 Cet opérateur retourne une référence à la relation contenant-contenu `CDataSource` objet, ce qui vous permet de passer un `CDataConnection` objet sur lequel un `CDataSource` référence est attendue.  
  
## <a name="example"></a>Exemple  
 Si vous avez une fonction (tel que `func` ci-dessous) qui prend un `CDataSource` référence, vous pouvez utiliser **CDataSource &** pour passer un `CDataConnection` à la place de l’objet.  
  
 [!code-cpp[NVC_OLEDB_Consumer#3](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#4](../../data/oledb/codesnippet/cpp/cdataconnection-operator-cdatasource-amp_2.cpp)]  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataConnection (classe)](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CDataSource*](../../data/oledb/cdataconnection-operator-cdatasource-star.md)