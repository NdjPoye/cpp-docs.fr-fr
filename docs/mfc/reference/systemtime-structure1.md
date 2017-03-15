---
title: SYSTEMTIME Structure1 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- SYSTEMTIME
dev_langs:
- C++
helpviewer_keywords:
- SYSTEMTIME structure
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: 15
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
ms.openlocfilehash: 298b2673a3eb05525683f8269fcd415d5be1c80a
ms.lasthandoff: 02/24/2017

---
# <a name="systemtime-structure1"></a>SYSTEMTIME Structure1
Le `SYSTEMTIME` structure représente une date et une heure à l’aide de membres individuels pour les mois, jour, année, jour de la semaine, heure, minute, seconde et milliseconde.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _SYSTEMTIME {  
    WORD wYear;  
    WORD wMonth;  
    WORD wDayOfWeek;  
    WORD wDay;  
    WORD wHour;  
    WORD wMinute;  
    WORD wSecond;  
    WORD wMilliseconds;  
} SYSTEMTIME;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *wYear*  
 L’année en cours.  
  
 *Propriété*  
 Le mois en cours ; Janvier est 1.  
  
 *wDayOfWeek*  
 Le jour actuel de la semaine ; 0 étant le dimanche, lundi est 1 et ainsi de suite.  
  
 *wDay*  
 Le jour du mois actuel.  
  
 *exactes*  
 L’heure actuelle.  
  
 *Absolu*  
 La minute en cours.  
  
 *wSecond*  
 La seconde actuelle.  
  
 *Heure*  
 La milliseconde en cours.  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities n °&39;](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** winbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)


