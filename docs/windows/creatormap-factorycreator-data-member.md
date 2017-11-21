---
title: "Creatormap::FactoryCreator, données de membre | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Details::CreatorMap::factoryCreator
dev_langs: C++
helpviewer_keywords: factoryCreator data member
ms.assetid: c9aac363-8f38-4cfd-9605-1e6ac74c5097
caps.latest.revision: "6"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 6e80b63a82a37350595e673e5f57b9e508d0bf9a
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="creatormapfactorycreator-data-member"></a>CreatorMap::factoryCreator, données de membre
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
HRESULT (*factoryCreator)(  
   unsigned int* currentflags,  
   const CreatorMap* entry,  
   REFIID iidClassFactory,  
 IUnknown** factory);  
```  
  
## <a name="parameters"></a>Paramètres  
 `currentflags`  
 Parmi les [RuntimeClassType](../windows/runtimeclasstype-enumeration.md) énumérateurs.  
  
 `entry`  
 Un CreatorMap.  
  
 `iidClassFactory`  
 L’ID d’interface d’une fabrique de classe.  
  
 `factory`  
 Lorsque l’opération terminée, l’adresse d’une fabrique de classe.  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.  
  
## <a name="remarks"></a>Remarques  
 Crée une fabrique pour le CreatorMap spécifié.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [CreatorMap (Structure)](../windows/creatormap-structure.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)