---
title: "Runtimeclass::getiids, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::GetIids
dev_langs: C++
helpviewer_keywords: GetIids method
ms.assetid: 826a67d1-ebc4-4940-b5d5-7cd66885e4a1
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: e26101377aaf85cbae24e400557280d06d1402fd
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="runtimeclassgetiids-method"></a>RuntimeClass::GetIids, méthode
Obtient un tableau qui contient l’interface ID implémentées par l’objet RuntimeClass en cours.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHOD(  
   GetIids  
)  
   (_Out_ ULONG *iidCount,   
   _Deref_out_ _Deref_post_cap_(*iidCount) IID **iids);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `iidCount`  
 Lorsque cette opération est terminée, le nombre total d’éléments du tableau `iids`.  
  
 `iids`  
 Lorsque cette opération est terminée, un pointeur vers un tableau d’ID de l’interface.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK en cas de réussite ; dans le cas contraire, E_OUTOFMEMORY.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [RuntimeClass, classe](../windows/runtimeclass-class.md)