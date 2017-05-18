---
title: Classe de CComApartment | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComApartment
- ATLBASE/ATL::CComApartment
- ATLBASE/ATL::CComApartment::CComApartment
- ATLBASE/ATL::CComApartment::Apartment
- ATLBASE/ATL::CComApartment::GetLockCount
- ATLBASE/ATL::CComApartment::Lock
- ATLBASE/ATL::CComApartment::Unlock
- ATLBASE/ATL::CComApartment::m_dwThreadID
- ATLBASE/ATL::CComApartment::m_hThread
- ATLBASE/ATL::CComApartment::m_nLockCnt
dev_langs:
- C++
helpviewer_keywords:
- apartments in ATL EXE modules
- CComApartment class
ms.assetid: dbc177d7-7ee4-45f2-b563-d578a467ca93
caps.latest.revision: 20
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: 9359e2ab8c4a84ab66441e3eb8cfd39520fd4e8d
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomapartment-class"></a>CComApartment (classe)
Cette classe prend en charge la gestion d’un appartement dans un module EXE pool de thread.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComApartment
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComApartment::CComApartment](#ccomapartment)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComApartment::Apartment](#apartment)|Marque l’adresse de départ du thread.|  
|[CComApartment::GetLockCount](#getlockcount)|Retourne le nombre de verrous en cours du thread.|  
|[CComApartment::Lock](#lock)|Incrémente le nombre de verrous du thread.|  
|[CComApartment::Unlock](#unlock)|Décrémente verrou du thread du nombre.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComApartment::m_dwThreadID](#m_dwthreadid)|Contient l’identificateur de la thread.|  
|[CComApartment::m_hThread](#m_hthread)|Contient le handle du thread.|  
|[CComApartment::m_nLockCnt](#m_nlockcnt)|Contient le nombre de verrous en cours du thread.|  
  
## <a name="remarks"></a>Notes  
 `CComApartment`est utilisé par [CComAutoThreadModule](../../atl/reference/ccomautothreadmodule-class.md) pour gérer un thread cloisonné dans un module EXE pool de thread. `CComApartment`Fournit des méthodes pour incrémenter et décrémenter le verrou comptent sur un thread.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="apartment"></a>CComApartment::Apartment  
 Marque l’adresse de départ du thread.  
  
```
DWORD Apartment();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Toujours 0.  
  
### <a name="remarks"></a>Remarques  
 Définir automatiquement au cours de [CComAutoThreadModule::Init](../../atl/reference/ccomautothreadmodule-class.md#init).  
  
##  <a name="ccomapartment"></a>CComApartment::CComApartment  
 Constructeur.  
  
```
CComApartment();
```  
  
### <a name="remarks"></a>Remarques  
 Initialise le `CComApartment` les membres de données [m_nLockCnt](#m_nlockcnt) et [m_hThread](#m_hthread).  
  
##  <a name="getlockcount"></a>CComApartment::GetLockCount  
 Retourne le nombre de verrous en cours du thread.  
  
```
LONG GetLockCount();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de verrous sur le thread.  
  
##  <a name="lock"></a>CComApartment::Lock  
 Incrémente le nombre de verrous du thread.  
  
```
LONG Lock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
### <a name="remarks"></a>Remarques  
 Appelé par [CComAutoThreadModule::Lock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 Le nombre de verrous sur le thread est utilisé à des fins statistiques.  
  
##  <a name="m_dwthreadid"></a>CComApartment::m_dwThreadID  
 Contient l’identificateur de la thread.  
  
```
DWORD m_dwThreadID;
```  
  
##  <a name="m_hthread"></a>CComApartment::m_hThread  
 Contient le handle du thread.  
  
```
HANDLE m_hThread;
```  
  
##  <a name="m_nlockcnt"></a>CComApartment::m_nLockCnt  
 Contient le nombre de verrous en cours du thread.  
  
```
LONG m_nLockCnt;
```  
  
##  <a name="unlock"></a>CComApartment::Unlock  
 Décrémente verrou du thread du nombre.  
  
```
LONG Unlock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur qui peut être utile pour les tests de diagnostic ou de test.  
  
### <a name="remarks"></a>Remarques  
 Appelé par [CComAutoThreadModule::Unlock](../../atl/reference/ccomautothreadmodule-class.md#lock).  
  
 Le nombre de verrous sur le thread est utilisé à des fins statistiques.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

