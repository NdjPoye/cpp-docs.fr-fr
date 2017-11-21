---
title: "Macros de l’état de l’objet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: atlcom/ATL::DECLARE_OLEMISC_STATUS
dev_langs: C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: "16"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: fc74d545388199eab2aca63ecdea1fdd62a9ef23
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="object-status-macros"></a>Objet état Macros
Cette macro définit des indicateurs qui appartiennent à des contrôles ActiveX.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Utilisé dans les contrôles ActiveX ATL pour définir le **OLEMISC** indicateurs.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  

##  <a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS  
 Utilisé dans les contrôles ActiveX ATL pour définir les indicateurs OLEMISC.  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>Paramètres  
 *MiscStatus*  
 Indicateurs OLEMISC toutes applicables.  
  
### <a name="remarks"></a>Remarques  
 Cette macro est utilisée pour définir les indicateurs OLEMISC pour un contrôle ActiveX. Reportez-vous à [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) pour plus d’informations.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing#124](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)
