---
title: "SRWLOCK::lockexclusive, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::SRWLock::LockExclusive
dev_langs: C++
helpviewer_keywords: LockExclusive method
ms.assetid: f361b672-fca6-45cc-a9b4-310cc0d23fdc
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: bb389b0aee2e995981e3d4570d3609ecae0dcaa5
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="srwlocklockexclusive-method"></a>SRWLock::LockExclusive, méthode
Acquiert un objet SRWLock en mode exclusif.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
SyncLockExclusive LockExclusive();  
  
static SyncLockExclusive LockExclusive(  
   _In_ SRWLOCK* lock  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `lock`  
 Pointeur vers un objet SRWLock.  
  
## <a name="return-value"></a>Valeur de retour  
 Un objet SRWLock en mode exclusif.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [SRWLock, classe](../windows/srwlock-class.md)