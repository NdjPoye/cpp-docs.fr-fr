---
title: "Factorycache::cookie, données de membre | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::FactoryCache::cookie
dev_langs: C++
helpviewer_keywords: cookie data member
ms.assetid: b1bc79af-a896-4e3b-8afa-64733022eddf
caps.latest.revision: "7"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: c3cca7b708f7fc2a0fdaa5b975396958b967210a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="factorycachecookie-data-member"></a>FactoryCache::cookie, données de membre
Prend en charge l’infrastructure de la bibliothèque de modèles Windows Runtime C++ et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
union {   
   WINRT_REGISTRATION_COOKIE winrt;  
   DWORD com;   
} cookie;  
```  
  
## <a name="remarks"></a>Remarques  
 Contient une valeur qui identifie un objet de classe Windows Runtime ou COM inscrit et est utilisée ultérieurement pour annuler l’inscription de l’objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [FactoryCache (Structure)](../windows/factorycache-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)