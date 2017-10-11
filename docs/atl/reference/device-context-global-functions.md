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
f1_keywords:
- atlwin/ATL::AtlCreateTargetDC
dev_langs:
- C++
ms.assetid: 08ec28f6-daff-4882-9544-e8a4639d05c4
caps.latest.revision: 17
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: d2560043bc97c384846696b76d8e38b459ae4a34
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

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
 [in] Le handle existant d’un contexte de périphérique, ou **NULL**.  
  
 `ptd`  
 [in] Un pointeur vers le **DVTARGETDEVICE** structure qui contient des informations sur l’appareil cible.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle vers un contexte de périphérique pour le périphérique spécifié dans le **DVTARGETDEVICE**. Si aucun périphérique n’est spécifié, retourne le handle vers le périphérique d’affichage par défaut.  
  
### <a name="remarks"></a>Remarques  
 Si la structure est **NULL** et *hdc* est **NULL**, crée un contexte de périphérique pour le périphérique d’affichage par défaut.  
  
 Si *hdc* n’est pas **NULL** et `ptd` est **NULL**, la fonction retourne existants *hdc*.  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
   
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)

