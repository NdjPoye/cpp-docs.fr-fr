---
title: BEGIN_COLUMN_MAP | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: BEGIN_COLUMN_MAP
dev_langs: C++
helpviewer_keywords: BEGIN_COLUMN_MAP macro
ms.assetid: d6ffe633-e0da-4e33-8faa-f7f259d05420
caps.latest.revision: "9"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 9edcaa47bccf0665ddeabf4e65e16ab1642de885
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="begincolumnmap"></a>BEGIN_COLUMN_MAP
Marque le début d’une entrée de mappage de colonnes.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
BEGIN_COLUMN_MAP(  
x  
 )  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 *x*  
 [in] Nom de la classe d’enregistrement utilisateur dérivée de `CAccessor`.  
  
## <a name="remarks"></a>Notes  
 Cette macro est utilisée dans le cas d’un seul accesseur sur un ensemble de lignes. Si vous avez plusieurs accesseurs sur un ensemble de lignes, utilisez [BEGIN_ACCESSOR_MAP](../../data/oledb/begin-accessor-map.md).  
  
 La macro `BEGIN_COLUMN_MAP` se termine avec la macro `END_COLUMN_MAP` . Cette macro est utilisée quand un seul accesseur est obligatoire dans l’enregistrement utilisateur.  
  
 Les colonnes correspondent aux champs de l’ensemble de lignes à lier.  
  
## <a name="example"></a>Exemple  
 Voici un exemple de mappage de colonnes et de paramètres :  
  
 <!--[!CODE [NVC_OLEDB_Consumer#16](../codesnippet/vs_snippets_cpp/nvc_oledb_consumer#16)]  -->
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)   
 [COLUMN_ENTRY](../../data/oledb/column-entry.md)   
 [COLUMN_ENTRY_EX](../../data/oledb/column-entry-ex.md)