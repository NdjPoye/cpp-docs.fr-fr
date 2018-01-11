---
title: FILETIME (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: FILETIME
dev_langs: C++
helpviewer_keywords: FILETIME structure [MFC]
ms.assetid: e09557e2-b6d7-4dd5-a5b9-6328bca88595
caps.latest.revision: "11"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: f23f9d4a508158b392de6eb5c872f0b5762e1ae3
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="filetime-structure"></a>FILETIME, structure
Le `FILETIME` structure est une valeur 64 bits représentant le nombre d’intervalles de 100 nanosecondes depuis le 1er janvier 1601.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
typedef struct _FILETIME {  
    DWORD dwLowDateTime;   /* low 32 bits */  
    DWORD dwHighDateTime;  /* high 32 bits */  
} FILETIME, *PFILETIME, *LPFILETIME;  
```  
  
#### <a name="parameters"></a>Paramètres  
 *dwLowDateTime*  
 Spécifie la faible 32 bits de l’heure de fichier.  
  
 *FILETIME*  
 Spécifie la haute 32 bits de l’heure de fichier.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** windef.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures, Styles, rappels et tables des messages](../../mfc/reference/structures-styles-callbacks-and-message-maps.md)   
 [CTime::CTime](../../atl-mfc-shared/reference/ctime-class.md#ctime)

