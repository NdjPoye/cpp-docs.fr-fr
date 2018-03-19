---
title: "ComPtrRefBase::operator IUnknown**, opérateur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::Details::ComPtrRefBase::operator IUnknown**
dev_langs:
- C++
helpviewer_keywords:
- operator IUnknown** operator
ms.assetid: c2950abf-a7aa-480a-ba41-615703e7f931
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 04eaa2992c74b4cb46954ac73aa7b5a8ae735f82
ms.sourcegitcommit: 9239c52c05e5cd19b6a72005372179587a47a8e4
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/16/2018
---
# <a name="comptrrefbaseoperator-iunknown-operator"></a>ComPtrRefBase::operator IUnknown**, opérateur
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
operator IUnknown**() const;  
```  
  
## <a name="remarks"></a>Notes  
 Convertit en cours [ptr_](../windows/comptrrefbase-ptr-data-member.md) membre de données pour un pointeur à une-pointeur-à l’interface IUnknown.  
  
 Une erreur est générée si le ComPtrRefBase actuelle ne dérive pas de IUnknown.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** client.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [ComPtrRefBase (classe)](../windows/comptrrefbase-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)