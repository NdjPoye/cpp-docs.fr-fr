---
title: DerefHelper (Structure) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::Details::DerefHelper
dev_langs: C++
helpviewer_keywords: DerefHelper structure
ms.assetid: 86ded58b-c3ee-4a4f-bb86-4f67b895d427
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c97a348b1f979f21edda5faf5b0c77a91ac5950a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="derefhelper-structure"></a>DerefHelper (structure)
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <  
   typename T  
>  
struct DerefHelper;  
  
template <  
   typename T  
>  
struct DerefHelper<T*>;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Un paramètre de modèle.  
  
## <a name="remarks"></a>Notes  
 Représenter un pointeur déréférencé vers le `T*` paramètre de modèle.  
  
 DerefHelper est utilisée dans une expression, telles que : `ComPtr<Details::DerefHelper<ProgressTraits::Arg1Type>::DerefType> operationInterface;`.  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`DerefType`|Identificateur du paramètre de modèle déréférencé `T*`.|  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d'héritage  
 `DerefHelper`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** async.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)