---
title: GetActivationFactory (fonction) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- module/Microsoft::WRL::Details::GetActivationFactory
- client/ABI::Windows::Foundation::GetActivationFactory
- client/Windows::Foundation::GetActivationFactory
dev_langs:
- C++
helpviewer_keywords:
- GetActivationFactory function
ms.assetid: 5736d285-6beb-42aa-8788-e261c0010afe
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: dd269b8c2e1c671944305d385064d60e8bf9b8a1
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="getactivationfactory-function"></a>GetActivationFactory (fonction)
Récupère la fabrique d’activation pour le type spécifié par le paramètre de modèle.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<typename T>  
inline HRESULT GetActivationFactory(  
   _In_ HSTRING activatableClassId,  
   _Out_ Microsoft::WRL::Details::ComPtrRef<T> factory  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Un paramètre de modèle qui spécifie le type de la fabrique d’activation.  
  
 `activatableClassId`  
 Le nom de la classe qui permet de créer la fabrique d’activation.  
  
 `factory`  
 Lorsque cette opération est terminée, une référence à la fabrique d’activation pour le type `T`.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK en cas de réussite ; Sinon, une erreur HRESULT qui indique la raison pour laquelle cette opération a échoué.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** client.h  
  
 **Namespace:** Windows::Foundation  
  
## <a name="see-also"></a>Voir aussi  
 [Windows::Foundation, espace de noms](../windows/windows-foundation-namespace.md)