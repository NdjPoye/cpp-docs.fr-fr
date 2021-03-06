---
title: WeakReference::WeakReference, constructeur | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-windows
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::Details::WeakReference::WeakReference
dev_langs:
- C++
helpviewer_keywords:
- WeakReference, constructor
ms.assetid: 4959a9d7-78ea-423d-a46b-50d010d29fff
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 8e60b23a0c63ce1415765dd1f94863540849f975
ms.sourcegitcommit: d55ac596ba8f908f5d91d228dc070dad31cb8360
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/08/2018
---
# <a name="weakreferenceweakreference-constructor"></a>WeakReference::WeakReference, constructeur
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WeakReference();  
```  
  
## <a name="remarks"></a>Notes  
 Initialise une nouvelle instance de la [classe WeakReference](../windows/weakreference-class1.md).  
  
 Le pointeur de la référence forte pour l’objet WeakReference est initialisé à `nullptr`, et le nombre de référence forte est initialisé à 1.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
    
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)