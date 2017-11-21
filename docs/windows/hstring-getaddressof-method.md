---
title: "Hstring::getaddressof, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HString::GetAddressOf
dev_langs: C++
ms.assetid: 6050decf-5f99-49f0-9497-1c8192c485ae
caps.latest.revision: "2"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0432a8f5966f6544808ffa4668777d2900ee5066
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="hstringgetaddressof-method"></a>HString::GetAddressOf, méthode
Récupère un pointeur vers le handle HSTRING sous-jacent.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HSTRING* GetAddressOf() throw()  
```  
  
## <a name="return-value"></a>Valeur de retour  
 Pointeur vers le handle HSTRING sous-jacent.  
  
## <a name="remarks"></a>Notes  
 Après cette opération, la valeur de chaîne du handle HSTRING sous-jacent est détruite.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [HString, classe](../windows/hstring-class.md)