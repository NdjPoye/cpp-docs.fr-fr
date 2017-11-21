---
title: "MakeAllocator :: ~ MakeAllocator, destructeur | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAllocator::~MakeAllocator
dev_langs: C++
helpviewer_keywords: ~MakeAllocator, destructor
ms.assetid: f1299c5f-cc6b-4d4e-85d4-aee1be0e2b0a
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 70d89466cd71fb9884b67f9545f1fe6a7c1f5061
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="makeallocatormakeallocator-destructor"></a>MakeAllocator::~MakeAllocator, destructeur
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
~MakeAllocator();  
```  
  
## <a name="remarks"></a>Remarques  
 Désinitialise l’instance actuelle de la classe MakeAllocator.  
  
 Ce destructeur supprime également la mémoire allouée sous-jacent si nécessaire.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [MakeAllocator (classe)](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)