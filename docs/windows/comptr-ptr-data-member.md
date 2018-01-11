---
title: "Comptr::PTR, données de membre | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: client/Microsoft::WRL::ComPtr::ptr_
dev_langs: C++
helpviewer_keywords: ptr_ data member
ms.assetid: c84f9dda-8ff9-422d-91f2-1a41206bf9ad
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 2048c4a6885889e9f398c7eded60807956e3e5cd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="comptrptr-data-member"></a>ComPtr::ptr_, données de membre
Contient un pointeur vers l’interface associée à ce ComPtr, et gérée par ce dernier.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
InterfaceType *ptr_;  
```  
  
## <a name="remarks"></a>Notes  
 `ptr_`est un membre interne des données protégées.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [ComPtr, classe](../windows/comptr-class.md)