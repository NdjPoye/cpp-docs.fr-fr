---
title: Classe de Win32ThreadTraits | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits
- ATLBASE/ATL::Win32ThreadTraits::CreateThread
dev_langs:
- C++
helpviewer_keywords:
- threading [ATL], Windows threads
- threading [ATL], creation functions
- Win32ThreadTraits class
ms.assetid: 50279c38-eae1-4301-9ea6-97ccea580f3e
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
translationtype: Machine Translation
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: fa331e05d647b5e2b9a0a76581e75d6b40366f95
ms.lasthandoff: 02/24/2017

---
# <a name="win32threadtraits-class"></a>Win32ThreadTraits (classe)
Cette classe fournit la fonction de création d’un thread Windows. Utilisez cette classe si le thread ne doit pas utiliser les fonctions CRT.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class Win32ThreadTraits
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[Win32ThreadTraits::CreateThread](#createthread)|(Statique) Appelez cette fonction pour créer un thread qui ne doit pas utiliser les fonctions CRT.|  
  
## <a name="remarks"></a>Notes  
 Caractéristiques de thread sont des classes qui fournissent une fonction de création d’un type particulier de thread. La fonction de création a la même signature et la même sémantique que les fenêtres [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) (fonction).  
  
 Caractéristiques de thread sont utilisées par les classes suivantes :  
  
- [CThreadPool](../../atl/reference/cthreadpool-class.md)  
  
- [CWorkerThread](../../atl/reference/cworkerthread-class.md)  
  
 Si le thread utilise des fonctions CRT, utilisez [CRTThreadTraits](../../atl/reference/crtthreadtraits-class.md) à la place.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="createthread"></a>Win32ThreadTraits::CreateThread  
 Appelez cette fonction pour créer un thread qui ne doit pas utiliser les fonctions CRT.  
  
```
static HANDLE CreateThread(
    LPSECURITY_ATTRIBUTES lpsa,
    DWORD dwStackSize,
    LPTHREAD_START_ROUTINE pfnThreadProc,
    void* pvParam,
    DWORD dwCreationFlags,
    DWORD* pdwThreadId) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpsa`  
 Les attributs de sécurité pour le nouveau thread.  
  
 `dwStackSize`  
 La taille de pile pour le nouveau thread.  
  
 `pfnThreadProc`  
 La procédure de thread du nouveau thread.  
  
 `pvParam`  
 Le paramètre à passer à la procédure de thread.  
  
 `dwCreationFlags`  
 La création des indicateurs (0 ou CREATE_SUSPENDED).  
  
 `pdwThreadId`  
 [out] Adresse de la variable DWORD qui, en cas de réussite, reçoit l’ID de thread du thread nouvellement créé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle du thread nouvellement créé ou NULL en cas d’échec. Appelez [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) pour obtenir des informations d’erreur étendues.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [CreateThread](http://msdn.microsoft.com/library/windows/desktop/ms682453) pour plus d’informations sur les paramètres de cette fonction.  
  
 Cette fonction appelle `CreateThread` pour créer le thread.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

