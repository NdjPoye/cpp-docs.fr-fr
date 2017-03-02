---
title: Fonction de rappel pour CDC::GrayString | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- Callback Function for CDC::GrayString
dev_langs:
- C++
helpviewer_keywords:
- callback functions, for CDC::GrayString
ms.assetid: 5217e183-df48-426b-931b-6245022ca36f
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
ms.openlocfilehash: 3ce3afefae9618420a8a97b27994c33604745677
ms.lasthandoff: 02/24/2017

---
# <a name="callback-function-for-cdcgraystring"></a>Fonction de rappel pour CDC::GrayString
*OutputFunc* est un espace réservé pour le nom de la fonction de rappel fournie par l’application.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
BOOL CALLBACK EXPORT OutputFunc(
    HDC hDC,  
    LPARAM lpData,  
    int nCount);
```  
  
#### <a name="parameters"></a>Paramètres  
 `hDC`  
 Identifie un contexte de périphérique de mémoire avec une bitmap au moins égale à la largeur et la hauteur spécifiées par `nWidth` et `nHeight` à `GrayString`.  
  
 `lpData`  
 Pointe vers la chaîne de caractères à ajouter.  
  
 `nCount`  
 Spécifie le nombre de caractères en sortie.  
  
## <a name="return-value"></a>Valeur de retour  
 Valeur de retour de la fonction de rappel doit être **TRUE** pour indiquer la réussite ; sinon, il est **FALSE**.  
  
## <a name="remarks"></a>Notes  
 La fonction de rappel (*OutputFunc*) doit dessiner une image par rapport aux coordonnées (0,0) au lieu de (*x*, *y*).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CDC::GrayString](../../mfc/reference/cdc-class.md#graystring)


