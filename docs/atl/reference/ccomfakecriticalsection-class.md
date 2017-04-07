---
title: Classe de la classe CComFakeCriticalSection | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection
- ATLCORE/ATL::CComFakeCriticalSection::Init
- ATLCORE/ATL::CComFakeCriticalSection::Lock
- ATLCORE/ATL::CComFakeCriticalSection::Term
- ATLCORE/ATL::CComFakeCriticalSection::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CComFakeCriticalSection class
ms.assetid: a4811b97-96bb-493b-ab9f-62822aeddb10
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 2c1269288e03a8ac9f359dad9acf1a81ddbc84c2
ms.lasthandoff: 02/24/2017

---
# <a name="ccomfakecriticalsection-class"></a>Classe de la classe CComFakeCriticalSection
Cette classe fournit les mêmes méthodes que [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md) mais ne fournit ne pas une section critique.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComFakeCriticalSection
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComFakeCriticalSection::Init](#init)|Ne fait rien, car il n’existe pas de section critique.|  
|[CComFakeCriticalSection::Lock](#lock)|Ne fait rien, car il n’existe pas de section critique.|  
|[CComFakeCriticalSection::Term](#term)|Ne fait rien, car il n’existe pas de section critique.|  
|[CComFakeCriticalSection::Unlock](#unlock)|Ne fait rien, car il n’existe pas de section critique.|  
  
## <a name="remarks"></a>Remarques  
 `CComFakeCriticalSection`reflète les méthodes de [CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md). Toutefois, `CComFakeCriticalSection` ne fournit pas une section critique ; par conséquent, ses méthodes ne rien font.  
  
 En général, vous utilisez `CComFakeCriticalSection` via un `typedef` nom, soit `AutoCriticalSection` ou `CriticalSection`. Lorsque vous utilisez [CComSingleThreadModel](../../atl/reference/ccomsinglethreadmodel-class.md) ou [CComMultiThreadModelNoCS](../../atl/reference/ccommultithreadmodelnocs-class.md), ces deux `typedef` noms font référence à `CComFakeCriticalSection`. Lorsque vous utilisez [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md), ils font référence à [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md) et `CComCriticalSection`, respectivement.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcore.h  
  
##  <a name="init"></a>CComFakeCriticalSection::Init  
 Ne fait rien, car il n’existe pas de section critique.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK.  
  
##  <a name="lock"></a>CComFakeCriticalSection::Lock  
 Ne fait rien, car il n’existe pas de section critique.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK.  
  
##  <a name="term"></a>CComFakeCriticalSection::Term  
 Ne fait rien, car il n’existe pas de section critique.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK.  
  
##  <a name="unlock"></a>CComFakeCriticalSection::Unlock  
 Ne fait rien, car il n’existe pas de section critique.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

