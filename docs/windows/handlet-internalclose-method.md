---
title: "Handlet::internalclose, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: corewrappers/Microsoft::WRL::Wrappers::HandleT::InternalClose
dev_langs: C++
helpviewer_keywords: InternalClose method
ms.assetid: fe693c02-aa1f-4e00-8bdd-a0d7d736da0b
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: dfa2597daf24530284a55cf59e646a75d0704f39
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="handletinternalclose-method"></a>HandleT::InternalClose, méthode
Ferme l’objet HandleT en cours.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
virtual bool InternalClose();  
```  
  
## <a name="return-value"></a>Valeur de retour  
 `true`Si le HandleT actuel a été fermé avec succès ; dans le cas contraire, `false`.  
  
## <a name="remarks"></a>Notes  
 InternalClose() est protégé.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** corewrappers.h  
  
 **Namespace :** Microsoft::WRL::Wrappers  
  
## <a name="see-also"></a>Voir aussi  
 [HandleT, classe](../windows/handlet-class.md)