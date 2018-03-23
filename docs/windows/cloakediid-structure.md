---
title: CloakedIid (Structure) | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.reviewer: ''
ms.suite: ''
ms.technology:
- cpp-windows
ms.tgt_pltfrm: ''
ms.topic: reference
f1_keywords:
- implements/Microsoft::WRL::CloakedIid
dev_langs:
- C++
helpviewer_keywords:
- CloakedIid structure
ms.assetid: 82e0e377-ca3a-46bc-b850-ae2c46c15bb5
caps.latest.revision: ''
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 075694e83f4c0e2004ccc9a86b03a0f7b7ea7f78
ms.sourcegitcommit: 1d11412c8f5e6ddf4edded89e0ef5097cc89f812
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 03/22/2018
---
# <a name="cloakediid-structure"></a>CloakedIid (structure)
Indique aux modèles RuntimeClass, Implements et ChainInterfaces que l'interface spécifiée n'est pas accessible dans la liste des IID.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<typename T>  
struct CloakedIid : T;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 L’interface est masquée (masqué).  
  
## <a name="remarks"></a>Notes  
 Voici un exemple d’utilisation de CloakedIid : `struct MyRuntimeClass : RuntimeClass<CloakedIid<IMyCloakedInterface>> {}`.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `T`  
  
 `CloakedIid`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL, espace de noms](../windows/microsoft-wrl-namespace.md)