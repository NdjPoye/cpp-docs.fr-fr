---
title: SYSTEMTIME Structure1 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: SYSTEMTIME
dev_langs: C++
helpviewer_keywords: SYSTEMTIME structure [MFC]
ms.assetid: 9aaef4d6-de79-4fa1-8158-86b245ef5bff
caps.latest.revision: "15"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 07af222a3d51ff1cc71076d5bbcc3513a3d6cad4
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="systemtime-structure1"></a>SYSTEMTIME Structure1
Le `SYSTEMTIME` structure représente une date et heure à l’aide des membres individuels pour les mois, jour, année, semaine, heure, minute, seconde et milliseconde.  
  
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
 Le jour actuel de la semaine ; Dimanche est 0, lundi est 1 et ainsi de suite.  
  
 *wDay*  
 Le jour du mois actuel.  
  
 *exactes*  
 L’heure actuelle.  
  
 *Absolu*  
 La minute actuelle.  
  
 *wSecond*  
 La seconde actuelle.  
  
 *Heure*  
 La milliseconde en cours.  
  
## <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities#39](../../mfc/codesnippet/cpp/systemtime-structure1_1.cpp)]  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** winbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

