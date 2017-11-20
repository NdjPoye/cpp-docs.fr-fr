---
title: COLUMN_ENTRY_TYPE_SIZE | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: COLUMN_ENTRY_TYPE_SIZE
dev_langs: C++
helpviewer_keywords: COLUMN_ENTRY_TYPE_SIZE macro
ms.assetid: d8b169e8-af22-464b-8cb3-eaa346f7a739
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0bfcb73413aff9cab90c0e4bec3623053f0759c7
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="columnentrytypesize"></a>COLUMN_ENTRY_TYPE_SIZE
Représente une liaison à la colonne dans la base de données. Prend en charge `type` et `size` paramètres.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
COLUMN_ENTRY_TYPE_SIZE(  
nOrdinal  
,   
wType  
,   
nLength  
,   
data  
 )  
  
```  
  
#### <a name="parameters"></a>Paramètres  
 `nOrdinal`  
 [in] Le numéro de colonne.  
  
 `wType`  
 [in] Type de données d’entrée de la colonne.  
  
 `nLength`  
 [in] Taille de l’entrée de la colonne en octets.  
  
 `data`  
 [in] Le membre de données correspondant dans l’enregistrement utilisateur.  
  
## <a name="remarks"></a>Remarques  
 Cette macro est une variante spécialisée de la [COLUMN_ENTRY](../../data/oledb/column-entry.md) macro qui fournit un moyen de spécifier la taille des données et le type.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [Macros et fonctions globales pour les modèles du consommateur OLE DB](../../data/oledb/macros-and-global-functions-for-ole-db-consumer-templates.md)   
 [BEGIN_COLUMN_MAP](../../data/oledb/begin-column-map.md)   
 [END_COLUMN_MAP](../../data/oledb/end-column-map.md)