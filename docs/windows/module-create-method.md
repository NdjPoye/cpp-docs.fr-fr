---
title: "Module::Create, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: module/Microsoft::WRL::Module::Create
dev_langs: C++
helpviewer_keywords: Create method
ms.assetid: bfa97fd7-5226-4604-92a5-3b9697053e64
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 0a5d3888657d491502b13283b5b9d7141940ade3
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="modulecreate-method"></a>Module::Create, méthode
Crée une instance d’un module.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
WRL_NOTHROW static Module& Create();  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   T callback  
);  
template<  
   typename T  
>  
WRL_NOTHROW static Module& Create(  
   _In_ T* object,  
   _In_ void (T::* method)()  
);  
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Type de module.  
  
 `callback`  
 Appelé lorsque le dernier objet d’instance du module est libéré.  
  
 `object`  
 Le `object` et `method` paramètres sont utilisés conjointement. Pointe vers le dernier objet d’instance lorsque le dernier objet d’instance dans le module est libéré.  
  
 `method`  
 Le `object` et `method` paramètres sont utilisés conjointement. Pointe vers la méthode du dernier objet d’instance lorsque le dernier objet d’instance dans le module est libéré.  
  
## <a name="return-value"></a>Valeur de retour  
 Référence au module.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** module.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
[Module, classe](../windows/module-class.md)

 