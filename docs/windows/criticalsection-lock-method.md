---
title: "CriticalSection::Lock, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::CriticalSection::Lock
dev_langs: C++
helpviewer_keywords: Lock method
ms.assetid: 37cb184c-e13c-49ef-b6a0-13908a956414
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 4df91ea9030ca4917f246bc05be1ba059673680e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="criticalsectionlock-method"></a>CriticalSection::Lock, méthode
Attend que la propriété de l’objet spécifié de section critique. La fonction retourne quand le thread appelant est accordé à la propriété.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SyncLock Lock();  
  
   static SyncLock Lock(  
   _In_ CRITICAL_SECTION* cs  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `cs`  
 Un objet spécifié par l’utilisateur une section critique.  
  
## <a name="return-value"></a>Valeur de retour  
 Un objet verrou qui peut être utilisé pour déverrouiller la section critique en cours.  
  
## <a name="remarks"></a>Remarques  
 La première **verrou** fonction affecte l’objet en cours de la section critique. La seconde **verrou** fonction affecte une section critique spécifié par l’utilisateur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [CriticalSection, classe](../windows/criticalsection-class.md)