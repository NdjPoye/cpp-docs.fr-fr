---
title: "Makeallocator::Allocate, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: implements/Microsoft::WRL::Details::MakeAllocator::Allocate
dev_langs: C++
helpviewer_keywords: Allocate method
ms.assetid: a01997bc-4ff1-4ed0-9def-e4aaa15b0598
caps.latest.revision: "5"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 997386e42851c6d4e15aceac006b4e27eea35c44
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="makeallocatorallocate-method"></a>MakeAllocator::Allocate, méthode
Prend en charge l’infrastructure WRL et n’est pas destinée à être utilisée directement depuis votre code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
__forceinline void* Allocate();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 En cas de réussite, un pointeur vers la mémoire allouée ; dans le cas contraire, `nullptr`.  
  
## <a name="remarks"></a>Notes  
 Alloue de la mémoire et l’associe à l’objet MakeAllocator en cours.  
  
 La taille de la mémoire allouée est la taille du type spécifié par le paramètre de modèle MakeAllocator actuel.  
  
 Un développeur doit substituer la méthode Allocate() uniquement pour implémenter un modèle d’allocation de mémoire différentes.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** implements.h  
  
 **Namespace :** Microsoft::WRL::Details  
  
## <a name="see-also"></a>Voir aussi  
 [MakeAllocator (classe)](../windows/makeallocator-class.md)   
 [Microsoft::WRL::Details, espace de noms](../windows/microsoft-wrl-details-namespace.md)