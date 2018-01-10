---
title: "Asyncbase::firecompletion, méthode | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords: async/Microsoft::WRL::AsyncBase::FireCompletion
dev_langs: C++
helpviewer_keywords: FireCompletion method
ms.assetid: b5e29d6d-52e7-4148-a7f3-a313b1359819
caps.latest.revision: "3"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
- uwp
ms.openlocfilehash: 49716e31148c119d5a8c9eca05b449cea75b405a
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="asyncbasefirecompletion-method"></a>AsyncBase::FireCompletion, méthode
Appelle le Gestionnaire d’événements de fin, ou réinitialise le délégué de progression interne.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
void FireCompletion(  
   void  
) override;  
  
virtual void FireCompletion();  
```  
  
## <a name="remarks"></a>Notes  
 La première version de FireCompletion() réinitialise la variable de délégué progression interne. La deuxième version appelle le Gestionnaire d’événements de fin si l’opération asynchrone est terminée.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** async.h  
  
 **Espace de noms :** Microsoft::WRL  
  
## <a name="see-also"></a>Voir aussi  
 [AsyncBase, classe](../windows/asyncbase-class.md)