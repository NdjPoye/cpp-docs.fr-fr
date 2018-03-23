---
title: Move (fonction) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- internal/Microsoft::WRL::Details::Move
dev_langs:
- C++
helpviewer_keywords:
- Move function
ms.assetid: c9525426-97e8-4d8c-9877-b689d8a0dc67
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 879bd0a0652e593c968bbc286cf977d7ec8d4e56
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="move-function"></a>Move (fonction)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<class T>  
inline typename RemoveReference<T>::Type&& Move(  
   _Inout_ T&& arg  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type de l’argument.  
  
 `arg`  
 Argument à déplacer.  
  
## <a name="return-value"></a>Valeur de retour  
 Paramètre `arg` après les caractéristiques de référence ou une référence rvalue, le cas échéant, ont été supprimées.  
  
## <a name="remarks"></a>Notes  
 Déplace l’argument spécifié à partir d’un emplacement vers un autre.  
  
 Pour plus d’informations, consultez la **sémantique de déplacement** section de [déclarateur de référence Rvalue : & &](../cpp/rvalue-reference-declarator-amp-amp.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** internal.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)