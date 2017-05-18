---
title: "Macros de l’état de l’objet | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 727dbef2-a342-4157-9d64-a421805d9747
caps.latest.revision: 16
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
ms.translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 433a816b19690f22f482f26f6ab70c73ed102673
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="object-status-macros"></a>Objet état Macros
Cette macro définit des indicateurs qui appartiennent à des contrôles ActiveX.  
  
|||  
|-|-|  
|[DECLARE_OLEMISC_STATUS](#declare_olemisc_status)|Utilisé dans les contrôles ActiveX ATL pour définir le **OLEMISC** indicateurs.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  

##  <a name="declare_olemisc_status"></a>DECLARE_OLEMISC_STATUS  
 Pour définir les indicateurs OLEMISC, utilisé dans les contrôles ActiveX ATL.  
  
```
DECLARE_OLEMISC_STATUS( miscstatus )
```  
  
### <a name="parameters"></a>Paramètres  
 *MiscStatus*  
 Indicateurs OLEMISC toutes applicables.  
  
### <a name="remarks"></a>Remarques  
 Cette macro est utilisée pour définir les indicateurs OLEMISC pour un contrôle ActiveX. Reportez-vous à [IOleObject::GetMiscStatus](http://msdn.microsoft.com/library/windows/desktop/ms678521) pour plus de détails.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#124;](../../atl/codesnippet/cpp/object-status-macros_1.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)

