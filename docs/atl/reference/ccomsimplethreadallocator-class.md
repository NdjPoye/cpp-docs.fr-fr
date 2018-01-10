---
title: Classe de CComSimpleThreadAllocator | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator
- ATLBASE/ATL::CComSimpleThreadAllocator::GetThread
dev_langs: C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 244443692478d0391c2079e55995c1fef1e1655e
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ccomsimplethreadallocator-class"></a>Classe de CComSimpleThreadAllocator
Cette classe gère la sélection de thread pour la classe `CComAutoThreadModule`.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComSimpleThreadAllocator
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComSimpleThreadAllocator::GetThread](#getthread)|Sélectionne un thread.|  
  
## <a name="remarks"></a>Notes  
 `CComSimpleThreadAllocator`gère la sélection de thread pour [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread`simplement parcourt chaque thread et retourne le suivant dans la séquence.  
  
## <a name="requirements"></a>Configuration requise  
 **En-tête :** atlbase.h  
  
##  <a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 Sélectionne un thread en spécifiant le thread suivant dans la séquence.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>Paramètres  
 `pApt`  
 Pas utilisé dans l’implémentation par défaut ATL.  
  
 `nThreads`  
 Le nombre maximal de threads dans le module EXE.  
  
### <a name="return-value"></a>Valeur de retour  
 Un entier compris entre zéro et ( `nThreads` - 1). Identifie un des threads dans le module EXE.  
  
### <a name="remarks"></a>Notes  
 Vous pouvez substituer `GetThread` pour fournir une autre méthode de sélection ou utiliser le `pApt` paramètre.  
  
 `GetThread`est appelée par [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CComApartment](../../atl/reference/ccomapartment-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
