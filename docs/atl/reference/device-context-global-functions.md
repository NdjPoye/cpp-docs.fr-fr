---
title: "Fonctions globales de contexte de périphérique | Documents Microsoft"
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
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: 17
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
ms.openlocfilehash: 8c71781519b965717acbcefab6fe6a183686caef
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="device-context-global-functions"></a>Fonctions globales de contexte de périphérique
Cette fonction crée un contexte de périphérique pour un périphérique donné.  
  
|||  
|-|-|  
|[AtlCreateTargetDC](#atlcreatetargetdc)|Crée un contexte de périphérique.|  
  
##  <a name="atlcreatetargetdc"></a>AtlCreateTargetDC  
 Crée un contexte de périphérique pour le périphérique spécifié dans le [DVTARGETDEVICE](http://msdn.microsoft.com/library/windows/desktop/ms686613) structure.  
  
```
HDC AtlCreateTargetDC(HDC hdc, DVTARGETDEVICE* ptd);
```  
  
### <a name="parameters"></a>Paramètres  
 *HDC*  
 [in] Le handle d’un contexte de périphérique existant ou **NULL**.  
  
 `ptd`  
 [in] Un pointeur vers le **DVTARGETDEVICE** structure qui contient des informations sur le périphérique cible.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle d’un contexte de périphérique pour le périphérique spécifié dans le **DVTARGETDEVICE**. Si aucun périphérique n’est spécifié, retourne le handle vers le périphérique d’affichage par défaut.  
  
### <a name="remarks"></a>Remarques  
 Si la structure est **NULL** et *hdc* est **NULL**, crée un contexte de périphérique pour le périphérique d’affichage par défaut.  
  
 Si *hdc* n’est pas **NULL** et `ptd` est **NULL**, la fonction retourne existant *hdc*.  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
   
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)

