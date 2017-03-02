---
title: Classe de CComSimpleThreadAllocator | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComSimpleThreadAllocator
- ATL::CComSimpleThreadAllocator
- ATL.CComSimpleThreadAllocator
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], selecting threads
- ATL threads
- CComSimpleThreadAllocator class
- ATL threads, allocating
ms.assetid: 66b2166a-8c50-49fd-b8e4-7f293470327d
caps.latest.revision: 19
author: mikeblome
ms.author: mblome
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 377e7f2fa6d8377d46e98b52e9c8f075b10956a8
ms.lasthandoff: 02/24/2017

---
# <a name="ccomsimplethreadallocator-class"></a>CComSimpleThreadAllocator (classe)
Cette classe gère la sélection du thread pour la classe `CComAutoThreadModule`.  
  
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
 `CComSimpleThreadAllocator`gère la sélection du thread pour [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md). `CComSimpleThreadAllocator::GetThread`simplement parcourt chaque thread et retourne le suivant dans la séquence.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="a-namegetthreada--ccomsimplethreadallocatorgetthread"></a><a name="getthread"></a>CComSimpleThreadAllocator::GetThread  
 Sélectionne un thread en spécifiant le thread suivant dans la séquence.  
  
```
int GetThread(CComApartment* /* pApt */, int nThreads);
```  
  
### <a name="parameters"></a>Paramètres  
 `pApt`  
 Pas utilisé dans l’implémentation par défaut ATL.  
  
 `nThreads`  
 Le nombre maximal de threads dans le module du fichier EXE.  
  
### <a name="return-value"></a>Valeur de retour  
 Un entier compris entre zéro et ( `nThreads` – 1). Identifie un des threads dans le module du fichier EXE.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez remplacer `GetThread` pour fournir une autre méthode de sélection ou utiliser le `pApt` paramètre.  
  
 `GetThread`est appelée par [CComAutoThreadModule::CreateInstance](../../atl/reference/ccomautothreadmodule-class.md#createinstance).  
  
## <a name="see-also"></a>Voir aussi  
 [CComApartment (classe)](../../atl/reference/ccomapartment-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

