---
title: auto_gcroot, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- msclr::auto_gcroot
- msclr.auto_gcroot
- auto_gcroot
dev_langs:
- C++
helpviewer_keywords:
- auto_gcroot
ms.assetid: b5790912-265d-463e-a486-47302e91042a
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- dotnet
ms.openlocfilehash: bb203193d1568056c631d90a2e1f5b1cf1d00e5a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="autogcroot-class"></a>auto_gcroot, classe
Gestion des ressources automatique (comme [auto_ptr, classe](../standard-library/auto-ptr-class.md)) qui peut être utilisé pour incorporer un handle virtuel dans un type natif.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template<typename _element_type>  
class auto_gcroot;  
```  
  
#### <a name="parameters"></a>Paramètres  
 `_element_type`  
 Le type managé à incorporer.  
  
## <a name="requirements"></a>Configuration requise  
 **Fichier d’en-tête** \<msclr\auto_gcroot.h >  
  
 **Namespace** msclr  
  
## <a name="see-also"></a>Voir aussi  
 [auto_gcroot](../dotnet/auto-gcroot.md)   
 [auto_gcroot, membres](../dotnet/auto-gcroot-members.md)   
 [Comment : déclarer des Handles dans les Types natifs](../dotnet/how-to-declare-handles-in-native-types.md)   
 [auto_handle, classe](../dotnet/auto-handle-class.md)