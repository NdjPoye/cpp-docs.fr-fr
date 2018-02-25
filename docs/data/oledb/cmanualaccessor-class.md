---
title: Classe CManualAccessor | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CManualAccessor
- ATL.CManualAccessor
- CManualAccessor
dev_langs:
- C++
helpviewer_keywords:
- CManualAccessor class
ms.assetid: a0088074-7135-465c-b228-69097a50b8cc
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: ecb9f31c862f62ddc2422f201aa824a959e961a0
ms.sourcegitcommit: d51ed21ab2b434535f5c1d553b22e432073e1478
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/23/2018
---
# <a name="cmanualaccessor-class"></a>CManualAccessor, classe
Représente un type d’accesseur conçu pour une utilisation avancée.  
  
## <a name="syntax"></a>Syntaxe

```cpp
class CManualAccessor : public CAccessorBase  
```  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)|Ajoute une entrée de liaison pour les colonnes de sortie.|  
|[AddParameterEntry](../../data/oledb/cmanualaccessor-addparameterentry.md)|Ajoute une entrée de paramètre dans l’accesseur de paramètre.|  
|[CreateAccessor](../../data/oledb/cmanualaccessor-createaccessor.md)|Alloue de la mémoire pour la colonne des structures de liaison et initialise les membres de données de colonne.|  
|[CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md)|Alloue de la mémoire pour le paramètre de structures de liaison et initialise les membres de données de paramètre.|  
  
## <a name="remarks"></a>Notes  
 À l’aide de `CManualAccessor`, vous pouvez spécifier le paramètre et liaison de colonne de sortie par les appels de fonction de l’exécution.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [DBViewer](../../visual-cpp-samples.md)   
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles de consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)   
 [CAccessor (classe)](../../data/oledb/caccessor-class.md)   
 [CDynamicAccessor (classe)](../../data/oledb/cdynamicaccessor-class.md)   
 [CDynamicParameterAccessor, classe](../../data/oledb/cdynamicparameteraccessor-class.md)