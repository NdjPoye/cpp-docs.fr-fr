---
title: CDynamicStringAccessorA, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CDynamicStringAccessorA
dev_langs:
- C++
helpviewer_keywords:
- CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: b7dfd677d0a0090946cfa7d6a19ac36e1da57a0f
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA, classe
Permet d’accéder à une source de données lorsque vous n’avez aucune connaissance du schéma de base de données (structure sous-jacente).  
  
## <a name="syntax"></a>Syntaxe

```cpp
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>Notes  
 Les deux demandent que le fournisseur récupère toutes les données accessibles à partir du magasin de données en tant que données de chaîne, mais `CDynamicStringAccessor` ANSI de demandes de données de chaîne.  
  
 `CDynamicStringAccessorA` hérite de **GetString** et `SetString` de `CDynamicStringAccessor`. Lorsque vous utilisez ces méthodes dans un `CDynamicStringAccessorA` objet, ***BaseType*** est **CHAR**.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête**: atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles de consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor (classe)](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor (classe)](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor (classe)](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor (classe)](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)