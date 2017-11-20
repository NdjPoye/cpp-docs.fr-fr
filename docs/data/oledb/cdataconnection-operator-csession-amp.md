---
title: CDataConnection::operator CSession&amp; | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CSession&
- CDataConnection::operatorCSession&
- CDataConnection.operatorCSession&
- operatorCSession&
dev_langs: C++
helpviewer_keywords:
- operator CSession&
- CSession& operator
ms.assetid: fba1e498-e482-4dda-8e0f-2542163bf627
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 526d7957eacaca5c6198c369e08d23e0d3ecc319
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cdataconnectionoperator-csessionamp"></a>CDataConnection::operator CSession&amp;
Retourne une référence à la relation contenant-contenu `CSession` objet.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
operator const CSession&();  
  
```  
  
## <a name="remarks"></a>Remarques  
 Cet opérateur retourne une référence à la relation contenant-contenu `CSession` objet, ce qui vous permet de passer un `CDataConnection` objet sur lequel un `CSession` référence est attendue.  
  
## <a name="example"></a>Exemple  
 Si vous avez une fonction (tel que `func` ci-dessous) qui prend un `CSession` référence, vous pouvez utiliser **CSession &** pour passer un `CDataConnection` à la place de l’objet.  
  
 [!code-cpp[NVC_OLEDB_Consumer#5](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_1.cpp)]  
  
 [!code-cpp[NVC_OLEDB_Consumer#6](../../data/oledb/codesnippet/cpp/cdataconnection-operator-csession-amp_2.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CDataConnection (classe)](../../data/oledb/cdataconnection-class.md)   
 [CDataConnection::operator CSession*](../../data/oledb/cdataconnection-operator-csession-star.md)