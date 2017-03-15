---
title: Macros des Messages Windows | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
ms.assetid: 63abd22c-372d-4148-bb04-c605950ae64f
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
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: be814c0a2ade7df8f7a4d6863627e79efe0a48bc
ms.lasthandoff: 02/24/2017

---
# <a name="windows-messages-macros"></a>Macros des Messages Windows
Cette macro transfère les messages de fenêtre.  
  
|||  
|-|-|  
|[WM_FORWARDMSG](#wm_forwardmsg)|Permet de transférer un message reçu par une fenêtre à une autre fenêtre pour le traitement.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h 
   
##  <a name="a-namewmforwardmsga--wmforwardmsg"></a><a name="wm_forwardmsg"></a>WM_FORWARDMSG  
 Cette macro transmet un message reçu par une fenêtre à une autre fenêtre pour le traitement.  
  
```
WM_FORWARDMSG
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le message a été traité, zéro dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Utilisez `WM_FORWARDMSG` pour transférer un message reçu par une fenêtre à une autre fenêtre pour le traitement. Les paramètres LPARAM et WPARAM sont utilisées comme suit :  
  
|Paramètre|Utilisation|  
|---------------|-----------|  
|WPARAM|Données définies par l’utilisateur|  
|LPARAM|Un pointeur vers un `MSG` structure qui contient des informations sur un message|  
  
### <a name="example"></a>Exemple  
 Dans l’exemple suivant, `m_hWndOther` représente l’autre fenêtre qui reçoit le message.  
  
 [!code-cpp[NVC_ATL_Windowing&#137;](../../atl/codesnippet/cpp/windows-messages-macros_1.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [Macros](../../atl/reference/atl-macros.md)

