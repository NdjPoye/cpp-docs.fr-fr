---
title: CDataConnection::operator CSession&amp; | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
dev_langs:
- C++
helpviewer_keywords:
- operator CSession&
- CSession& operator
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 1ce7a03d90225457c482c12a4d7df1d6135cd8ac
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="cdataconnectionoperator-csessionamp"></a>CDataConnection::operator CSession&amp;
Retourne une référence à la relation contenant-contenu `CSession` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```cpp
operator const CSession&();  
  
```  
  
## <a name="remarks"></a>Notes  
 Cet opérateur retourne une référence à la relation contenant-contenu `CSession` objet, ce qui vous permet de passer un `CDataConnection` objet sur lequel un `CSession` référence est attendue.  
  
## <a name="example"></a>Exemple  
 Si vous avez une fonction (tel que `func` ci-dessous) qui prend un `CSession` référence, vous pouvez utiliser **CSession &** pour passer un `CDataConnection` à la place de l’objet.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataConnection (classe)](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession*](../../data/oledb/cdataconnection-operator-csession-star.md)