---
title: Structure de _AtlCreateWndData | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
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
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: cc8bf88ce5258dc36a06f32ebaa5e2cdf15092fc
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
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





