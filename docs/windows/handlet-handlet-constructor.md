---
title: Handlet::handlet, constructeur | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::HandleT
dev_langs: C++
helpviewer_keywords: HandleT, constructor
ms.assetid: 4def6891-7e53-46f1-a197-a80e10744dd5
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 8cca827bb8ba7fa43619a6e61e2c16ffba5e4563
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="handlethandlet-constructor"></a>HandleT::HandleT, constructeur
Initialise une nouvelle instance de la classe HandleT.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
explicit HandleT(  
   typename HandleTraits::Type h =   
      HandleTraits::GetInvalidValue()  
);  
  
HandleT(  
   _Inout_ HandleT&& h  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `h`  
 Un handle.  
  
## <a name="remarks"></a>Notes  
 Le premier constructeur initialise un objet HandleT qui n’est pas un handle valide d’un objet. Le deuxième constructeur crée un objet HandleT à partir du paramètre `h`.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [HandleT, classe](../windows/handlet-class.md)