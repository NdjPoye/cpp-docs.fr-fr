---
title: END_ACCESSOR | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: END_ACCESSOR
dev_langs: C++
helpviewer_keywords: END_ACCESSOR macro
ms.assetid: 26f74167-68c4-4909-a474-73dc7ebc9542
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: f0dceb1fe648a67d10fb18b353a5de54fa39caee
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="endaccessor"></a>END_ACCESSOR
Marque la fin d’une entrée de l’accesseur.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
END_ACCESSOR( )  
  
```  
  
## <a name="remarks"></a>Notes  
 Pour les accesseurs multiples sur un ensemble de lignes, vous devez spécifier `BEGIN_ACCESSOR_MAP` et utiliser le `BEGIN_ACCESSOR` macro pour chaque accesseur individuel. La macro `BEGIN_ACCESSOR` se termine avec la macro `END_ACCESSOR` . Le `BEGIN_ACCESSOR_MAP` macro s’est terminée avec le `END_ACCESSOR_MAP` (macro).  
  
## <a name="example"></a>Exemple  
 Consultez [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md)   
 [BEGIN_ACCESSOR](../../data/oledb/begin-accessor.md)   
 [END_ACCESSOR_MAP](../../data/oledb/end-accessor-map.md)