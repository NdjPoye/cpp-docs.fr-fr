---
title: Fonction de rappel pour CDC::EnumObjects | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::EnumObjects
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::EnumObjects
ms.assetid: 380088b1-88a5-4fb4-bbb5-dd9e8386572b
caps.latest.revision: 10
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
ms.openlocfilehash: e4b24b5f5333d5514b9fdf69d204bca5d7947d7a
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcenumobjects"></a>Fonction de rappel pour CDC::EnumObjects
Le *ObjectFunc* nom est un espace réservé pour le nom de fonction fourni par l’application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
int CALLBACK EXPORT ObjectFunc(
    LPSTR lpszLogObject,  
    LPSTR* lpData);
```  
  
#### <a name="parameters"></a>Paramètres  
 *lpszLogObject*  
 Pointe vers une [LOGPEN](../../mfc/reference/logpen-structure.md) ou [LOGBRUSH](../../mfc/reference/logbrush-structure.md) structure de données qui contient des informations sur les attributs logiques de l’objet.  
  
 `lpData`  
 Les points de données fourni par l’application passé à la `EnumObjects` (fonction).  
  
## <a name="return-value"></a>Valeur de retour  
 La fonction de rappel renvoie un `int`. La valeur de ce retour est définie par l’utilisateur. Si la fonction de rappel renvoie la valeur 0, `EnumObjects` arrête l’énumération au début.  
  
## <a name="remarks"></a>Remarques  
 Le nom doit être exporté.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::EnumObjects](../../mfc/reference/cdc-class.md#enumobjects)


