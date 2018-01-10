---
title: "Implementshelper::fillarraywithiid, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::ImplementsHelper::FillArrayWithIid
dev_langs: C++
helpviewer_keywords: FillArrayWithIid method
ms.assetid: f60035ee-b7d6-4a08-966d-f88c646944c3
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: eeb2254933dc0f9f5e4b99ba4e010dbe3afbb7cc
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="implementshelperfillarraywithiid-method"></a>ImplementsHelper::FillArrayWithIid, méthode
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void FillArrayWithIid(  
   _Inout_ unsigned long *index,   
   _Inout_ IID* iids) throw();  
```  
  
#### <a name="parameters"></a>Paramètres  
 `index`  
 Index de base zéro qui indique l’élément de tableau de départ pour cette opération. Lorsque cette opération est terminée, `index` est incrémentée de 1.  
  
 `iids`  
 Un tableau de type IID.  
  
## <a name="remarks"></a>Notes  
 Insère l’ID d’interface spécifié par le paramètre de modèle actuel placée dans l’élément de tableau spécifié.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [ImplementsHelper (Structure)](../windows/implementshelper-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)