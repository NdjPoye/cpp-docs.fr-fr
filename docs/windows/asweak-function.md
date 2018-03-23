---
title: AsWeak (fonction) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- client/Microsoft::WRL::AsWeak
dev_langs:
- C++
helpviewer_keywords:
- AsWeak function
ms.assetid: a6f10cfc-c1d6-4761-adb9-1a119cc99913
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 75d732758bac53edc40aeac50e0184d80145890d
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="asweak-function"></a>AsWeak (fonction)
Récupère une référence faible à une instance spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<typename T>  
HRESULT AsWeak(  
   _In_ T* p,  
   _Out_ WeakRef* pWeak  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Un pointeur vers le type de paramètre `p`.  
  
 `p`  
 Une instance d’un type.  
  
 `pWeak`  
 Lorsque cette opération est terminée, un pointeur vers une référence faible au paramètre `p`.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK, si cette opération a réussi ; Sinon, une erreur HRESULT qui indique la cause de l’échec.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** client.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)