---
title: "Synclockwithstatust::IsLocked, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::Details::SyncLockWithStatusT::IsLocked
dev_langs: C++
helpviewer_keywords: IsLocked method
ms.assetid: e1b75b7b-c145-471a-aa5d-71abf31f5990
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: e31f0931a53e8bdd977e82fcef56f1bacc45f76b
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="synclockwithstatustislocked-method"></a>SyncLockWithStatusT::IsLocked, méthode
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
bool IsLocked() const;  
```  
  
## <a name="remarks"></a>Remarques  
 Indique si l’objet SyncLockWithStatusT actuel possède une ressource ; l’objet SyncLockWithStatusT est *verrouillé*.  
  
## <a name="return-value"></a>Valeur de retour  
 **true** si l’objet SyncLockWithStatusT est verrouillée ; sinon, **false**.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers::Details  
  
## <a name="see-also"></a>Voir aussi  
 [SyncLockWithStatusT, classe](../windows/synclockwithstatust-class.md)