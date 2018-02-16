---
title: CCommand::Close | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CCommand.Close
- CCommand::Close
dev_langs:
- C++
helpviewer_keywords:
- Close method
ms.assetid: 4da9c02c-7082-4e47-a0fa-78b546f0f7d2
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 10d3ce633add0dea4a3b9a79a32fd380761b5a2f
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="ccommandclose"></a>CCommand::Close
Libère l’ensemble de lignes accesseur associé à la commande.  
  
## <a name="syntax"></a>Syntaxe

```cpp
void Close();  
```  
  
## <a name="remarks"></a>Notes  
 Une commande utilise un ensemble de lignes de résultat d’accesseur set et (éventuellement) un accesseur de paramètre (contrairement aux tables qui ne prennent pas en charge les paramètres et n’avez pas besoin d’un accesseur de paramètre).  
  
 Lorsque vous exécutez une commande, vous devez appeler à la fois `Close` et [ReleaseCommand](../../data/oledb/ccommand-releasecommand.md) après la commande.  
  
 Lorsque vous souhaitez exécuter la même commande plusieurs fois, vous devez libérer chaque accesseur de jeu de résultats en appelant `Close` avant d’appeler `Execute`. À la fin de la série, vous devez libérer de l’accesseur de paramètre en appelant `ReleaseCommand`. Un autre scénario courant appelle une procédure stockée qui a des paramètres de sortie. De nombreux fournisseurs (par exemple, le fournisseur OLE DB pour SQL Server) les valeurs de paramètre de sortie ne seront plus accessibles jusqu'à la fermeture de l’accesseur set de résultat. Appelez `Close` pour fermer l’ensemble de lignes retournée et accesseur de jeu de résultats, mais pas l’accesseur de paramètre, ce qui permet de récupérer les valeurs de paramètre de sortie.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment vous pouvez appeler `Close` et `ReleaseCommand` lorsque vous exécutez la même commande de façon répétée.  
  
 [!code-cpp[NVC_OLEDB_Consumer#2](../../data/oledb/codesnippet/cpp/ccommand-close_1.cpp)]  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CCommand (classe)](../../data/oledb/ccommand-class.md)   
 [CCommand::ReleaseCommand](../../data/oledb/ccommand-releasecommand.md)