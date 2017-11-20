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
ms.openlocfilehash: 88ba3c853bbd12c1512dbb8c70c0941718b1396f
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
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
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atldbsch.h  
  
## <a name="see-also"></a>Voir aussi  
 [Modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-cpp.md)   
 [Référence des modèles du consommateur OLE DB](../../data/oledb/ole-db-consumer-templates-reference.md)