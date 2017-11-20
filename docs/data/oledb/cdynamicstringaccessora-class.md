---
title: CDynamicStringAccessorA, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: CDynamicStringAccessorA
dev_langs: C++
helpviewer_keywords: CDynamicStringAccessorA class
ms.assetid: ed0d9821-a655-41f1-a902-43c3042ac49c
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: a9e7e2119bf25fda107ff529781efa5c517b01fc
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="cdynamicstringaccessora-class"></a>CDynamicStringAccessorA, classe
Permet d’accéder à une source de données lorsque vous n’avez aucune connaissance du schéma de base de données (structure sous-jacente).  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef CDynamicStringAccessorT<CHAR, DBTYPE_STR> CDynamicStringAccessorA;  
```  
  
## <a name="remarks"></a>Remarques  
 Les deux demandent que le fournisseur récupère toutes les données accessibles à partir du magasin de données en tant que données de chaîne, mais `CDynamicStringAccessor` ANSI de demandes de données de chaîne.  
  
 `CDynamicStringAccessorA`hérite de **GetString** et `SetString` de `CDynamicStringAccessor`. Lorsque vous utilisez ces méthodes dans un `CDynamicStringAccessorA` objet, ***BaseType*** est **CHAR**.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête**: atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles de consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor (classe)](../../data/oledb/caccessor-class.md)   
 [CDynamicParameterAccessor (classe)](../../data/oledb/cdynamicparameteraccessor-class.md)   
 [CManualAccessor (classe)](../../data/oledb/cmanualaccessor-class.md)   
 [CDynamicAccessor (classe)](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicStringAccessor, classe](../../data/oledb/cdynamicstringaccessor-class.md)