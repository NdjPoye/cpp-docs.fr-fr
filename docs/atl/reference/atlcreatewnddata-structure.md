---
title: Structure de _AtlCreateWndData | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- ATL::_AtlCreateWndData
- ATL._AtlCreateWndData
- _AtlCreateWndData
dev_langs:
- C++
helpviewer_keywords:
- _AtlCreateWndData structure
- AtlCreateWndData structure
ms.assetid: 76ed5382-bfbf-4b8b-8a29-912688dfd2ae
caps.latest.revision: 15
author: mikeblome
ms.author: mblome
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: c55726a1728185f699afbac4ba68a6dc0f70c2bf
ms.openlocfilehash: a5b0811e88188bb29ef3153f739804cbdac66083
ms.contentlocale: fr-fr
ms.lasthandoff: 10/09/2017

---
# <a name="atlcreatewnddata-structure"></a>Structure de _AtlCreateWndData
Cette structure contient les données d’instance de classe dans le code de fenêtrage dans ATL.  
  
## <a name="syntax"></a>Syntaxe  
  
```
    struct _AtlCreateWndData{
    void* m_pThis;
    DWORD m_dwThreadID;
    _AtlCreateWndData* m_pNext;
};
```  
  
## <a name="members"></a>Membres  
 **m_pThis**  
 Le **cela** pointeur utilisé pour accéder à l’instance de classe dans les procédures de fenêtre.  
  
 `m_dwThreadID`  
 L’ID de thread de l’instance actuelle de la classe.  
  
 **m_pNext**  
 Pointeur vers la prochaine `_AtlCreateWndData` objet.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
## <a name="see-also"></a>Voir aussi  
 [Structures](../../atl/reference/atl-structures.md)






