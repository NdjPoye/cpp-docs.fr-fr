---
title: CUtlProps::SetPropValue | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SetPropValue
- ATL::CUtlProps<T>::SetPropValue
- ATL.CUtlProps<T>.SetPropValue
- ATL.CUtlProps.SetPropValue
- CUtlProps::SetPropValue
- CUtlProps<T>::SetPropValue
- CUtlProps.SetPropValue
- CUtlProps<T>.SetPropValue
- ATL::CUtlProps::SetPropValue
dev_langs: C++
helpviewer_keywords: SetPropValue method
ms.assetid: 69a703c0-f640-4ca3-8850-0c4e75d52429
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- data-storage
ms.openlocfilehash: 389aa22addcc293131c5b4a1c60aa2601b354f3f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="cutlpropssetpropvalue"></a>CUtlProps::SetPropValue
Définit une propriété dans un jeu de propriétés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
      HRESULT SetPropValue(  
   const GUID* pguidPropSet,  
   DBPROPID dwPropId,  
   VARIANT* pvValue   
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `pguidPropSet`  
 [in] GUID pour le PropSet.  
  
 `dwPropId`  
 [in] L’index de la propriété.  
  
 `pvValue`  
 [in] Pointeur vers une variante qui contient la nouvelle valeur de propriété.  
  
## <a name="return-value"></a>Valeur de retour  
 `Failure`en cas d’échec et `S_OK` en cas de réussite.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atldb.h  
  
## <a name="see-also"></a>Voir aussi  
 [CUtlProps, classe](../../data/oledb/cutlprops-class.md)