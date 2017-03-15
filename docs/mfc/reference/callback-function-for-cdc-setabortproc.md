---
title: Fonction de rappel pour CDC::SetAbortProc | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::SetAbortProc
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::SetAbortProc
ms.assetid: daa36d5d-15de-40fc-8d37-a865d06c4710
caps.latest.revision: 11
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 1ba16ea60d8b18abd1962ded2da7e11ff2ef09a1
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcsetabortproc"></a>Fonction de rappel pour CDC::SetAbortProc
Le nom *AbortFunc* est un espace réservé pour le nom de fonction fourni par l’application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
BOOL CALLBACK EXPORT AbortFunc(
    HDC hPr,  
    int code);
```  
  
#### <a name="parameters"></a>Paramètres  
 *hPr*  
 Identifie le contexte de périphérique.  
  
 `code`  
 Spécifie si une erreur s’est produite. Il est 0 si aucune erreur ne se n’est produite. Il est **SP_OUTOFDISK** si le Gestionnaire d’impression n’est pas l’espace disque et davantage d’espace disque devient disponible si l’application attend. Si `code` est **SP_OUTOFDISK**, l’application ne doit pas abandonner le travail d’impression. Si elle n’est pas le cas, il doit être cédée le Gestionnaire d’impression en appelant le **PeekMessage** ou **GetMessage** fonction Windows.  
  
## <a name="return-value"></a>Valeur de retour  
 La valeur de retour de la fonction de gestionnaire d’abandon est différent de zéro si le travail d’impression doit continuer et 0 si elle est annulée.  
  
## <a name="remarks"></a>Remarques  
 Le nom doit être exporté comme décrit dans la section Notes de [CDC::SetAbortProc](../../mfc/reference/cdc-class.md#setabortproc).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::SETABORTPROC](../../mfc/reference/cdc-class.md#setabortproc)


