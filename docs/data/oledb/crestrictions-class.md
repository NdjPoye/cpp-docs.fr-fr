---
title: CRestrictions, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::CRestrictions
- CRestrictions
- ATL.CRestrictions
dev_langs: C++
helpviewer_keywords: CRestrictions class
ms.assetid: 0aaa2364-641c-4318-b110-7446aada4b4f
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 23b01a776a624f0fa463c7071e164b70111b2e8b
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="crestrictions-class"></a>CRestrictions, classe
Une classe générique qui vous permet de spécifier des restrictions pour les ensembles de lignes de schéma.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <   
   class T,   
   short nRestrictions,   
   const GUID* pguid   
>  
class CRestrictions : public CSchemaRowset <   
   T,   
   nRestrictions   
>  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 La classe utilisée pour l’accesseur.  
  
 `nRestrictions`  
 Le nombre de colonnes de restriction pour l’ensemble de lignes de schéma.  
  
 `pguid`  
 Pointeur vers le GUID pour le schéma.  
  
## <a name="members"></a>Membres  
  
### <a name="methods"></a>Méthodes  
  
|||  
|-|-|  
|[Ouvrir](../../data/oledb/crestrictions-open.md)|Retourne un résultat défini selon les restrictions fournies par l’utilisateur.|  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbsch.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)