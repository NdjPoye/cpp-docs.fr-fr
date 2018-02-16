---
title: CManualAccessor::AddParameterEntry | Microsoft Docs
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- CManualAccessor::AddParameterEntry
- ATL.CManualAccessor.AddParameterEntry
- CManualAccessor.AddParameterEntry
- AddParameterEntry
- ATL::CManualAccessor::AddParameterEntry
dev_langs:
- C++
helpviewer_keywords:
- AddParameterEntry method
ms.assetid: 9048b164-052b-41b1-a861-227fc529e0b5
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: e0b730ad81eb827fb86b77b95d4abb96ac73b3c3
ms.sourcegitcommit: 6002df0ac79bde5d5cab7bbeb9d8e0ef9920da4a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 02/14/2018
---
# <a name="cmanualaccessoraddparameterentry"></a>CManualAccessor::AddParameterEntry
Ajoute une entrée de paramètre pour les structures d’entrée de paramètre.  
  
## <a name="syntax"></a>Syntaxe  
  
```
void AddParameterEntry(DBORDINAL nOrdinal,  
   DBTYPE wType,  DBLENGTH nColumnSize,  
   void* pData,  
   void* pLength = NULL,  
   void* pStatus = NULL,  
   DBPARAMIO eParamIO = DBPARAMIO_INPUT) throw ();  
```  
  
#### <a name="parameters"></a>Paramètres  
 Consultez [DBBINDING](https://msdn.microsoft.com/en-us/library/ms716845.aspx) dans les *de référence du programmeur OLE DB*.  
  
 `nOrdinal`  
 [in] Numéro de paramètre.  
  
 `wType`  
 [in] Type de données.  
  
 `nColumnSize`  
 [in] Taille de la colonne en octets.  
  
 `pData`  
 [in] Pointeur vers les données de colonne stockées dans la mémoire tampon.  
  
 `pLength`  
 [in] Pointeur vers la longueur de champ, si nécessaire.  
  
 `pStatus`  
 [in] Pointeur vers la variable à lier à l’état de la colonne, si nécessaire.  
  
 *eParamIO*  
 [in] Spécifie si le paramètre auquel la liaison est associée est un paramètre d’entrée, d’entrée/sortie ou de sortie.  
  
## <a name="remarks"></a>Notes  
 Pour utiliser cette fonction, vous devez d’abord appeler [CreateParameterAccessor](../../data/oledb/cmanualaccessor-createparameteraccessor.md).  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldbcli.h  
  
## <a name="see-also"></a>Voir aussi  
 [CManualAccessor (classe)](../../data/oledb/cmanualaccessor-class.md)   
 [CManualAccessor::AddBindEntry](../../data/oledb/cmanualaccessor-addbindentry.md)   
 [Exemple DBVIEWER](../../visual-cpp-samples.md)