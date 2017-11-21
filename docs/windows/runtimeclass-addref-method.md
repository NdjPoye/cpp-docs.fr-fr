---
title: "Runtimeclass::AddRef, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::RuntimeClass::AddRef
dev_langs: C++
helpviewer_keywords: AddRef method
ms.assetid: 9c705749-680b-4308-bbec-5b601e8e7dbd
caps.latest.revision: "4"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: d99623b75aabf17a0f23090889077db5196924ac
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="runtimeclassaddref-method"></a>RuntimeClass::AddRef, méthode
Incrémente le décompte de références pour l’objet RuntimeClass actuel.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
STDMETHOD_(  
   ULONG,  
   AddRef  
)();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 S_OK si l'opération réussit. Sinon, une valeur HRESULT indique l'erreur.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [RuntimeClass, classe](../windows/runtimeclass-class.md)