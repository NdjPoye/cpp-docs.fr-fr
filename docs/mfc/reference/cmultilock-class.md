---
title: CMultiLock (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMultiLock
- AFXMT/CMultiLock
- AFXMT/CMultiLock::CMultiLock
- AFXMT/CMultiLock::IsLocked
- AFXMT/CMultiLock::Lock
- AFXMT/CMultiLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CMultiLock class
- synchronization objects, access control
ms.assetid: c5b7c78b-1f81-4387-b7dd-2c813c5b6b61
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: a58d59d8e4d7a1c542dee80295dd8eef6c8be338
ms.lasthandoff: 02/24/2017

---
# <a name="cmultilock-class"></a>CMultiLock (classe)
Représente le mécanisme de contrôle d'accès utilisé pour accéder aux ressources dans un programme multithread.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMultiLock  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMultiLock::CMultiLock](#cmultilock)|Construit un objet `CMultiLock`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMultiLock::IsLocked](#islocked)|Détermine si un objet de synchronisation spécifiques dans le tableau est verrouillé.|  
|[CMultiLock::Lock](#lock)|Attend sur le tableau d’objets de synchronisation.|  
|[CMultiLock::Unlock](#unlock)|Libère tous les objets de synchronisation lui appartenant.|  
  
## <a name="remarks"></a>Remarques  
 `CMultiLock`n’a pas d’une classe de base.  
  
 Pour utiliser les classes de synchronisation [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), et [CEvent](../../mfc/reference/cevent-class.md), vous pouvez créer soit un **CMultiLock** ou [CSingleLock](../../mfc/reference/csinglelock-class.md) objet attendent et libérer l’objet de synchronisation. Utilisez **CMultiLock** lorsqu’il existe plusieurs objets que vous pouvez utiliser à un moment donné. Utilisez `CSingleLock` quand vous devrez seulement attendre sur un seul objet à la fois.  
  
 Pour utiliser un **CMultiLock** d’objet, commencez par créer un tableau d’objets de synchronisation à attendre. Ensuite, appelez le **CMultiLock** constructeur de l’objet à l’intérieur d’une fonction membre de classe de la ressource contrôlée. Appelez ensuite la [verrou](#lock) fonction membre pour déterminer si une ressource est disponible (signalé). Si une est, continuer avec le reste de la fonction membre. Si aucune ressource n’est disponible, attendre un certain temps pour une ressource doit être publié ou renvoient une erreur. Au terme de l’utilisation d’une ressource, soit appeler le [Unlock](#unlock) fonctionner si le **CMultiLock** objet doit être utilisé à nouveau, ou autoriser le **CMultiLock** objet d’être détruites.  
  
 **CMultiLock** objets sont particulièrement utiles lorsqu’un thread possède un grand nombre de `CEvent` il peut répondre à des objets. Créer un tableau contenant tous les `CEvent` des pointeurs, puis appelez `Lock`. Cela entraîne le thread d’attente jusqu'à ce que l’un des événements est signalé.  
  
 Pour plus d’informations sur l’utilisation de **CMultiLock** , consultez l’article [Multithreading : comment utiliser les Classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CMultiLock`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmt.h  
  
##  <a name="cmultilock"></a>CMultiLock::CMultiLock  
 Construit un **CMultiLock** objet.  
  
```  
CMultiLock(
    CSyncObject* ppObjects [ ],  
    DWORD dwCount,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `ppObjects`  
 Tableau de pointeurs vers les objets de synchronisation à. Ne peut pas être **NULL**.  
  
 `dwCount`  
 Nombre d’objets de `ppObjects`. Doit être supérieure à 0.  
  
 `bInitialLock`  
 Spécifie s’il faut initialement que vous tentez d’accéder à tous les objets fournis.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée après la création d’un tableau d’objets de synchronisation à. Elle est généralement appelée dans le thread doit attendre un des objets de synchronisation soient disponibles.  
  
##  <a name="islocked"></a>CMultiLock::IsLocked  
 Détermine si l’objet spécifié est non signalé (non disponible).  
  
```  
BOOL IsLocked(DWORD dwItem);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwItem*  
 Index dans le tableau d’objets correspondant à l’objet dont l’état est interrogée.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet spécifié est verrouillé ; sinon 0.  
  
##  <a name="lock"></a>CMultiLock::Lock  
 Appelez cette fonction pour accéder à un ou plusieurs des ressources contrôlées par les objets de synchronisation fournis à la **CMultiLock** constructeur.  
  
```  
DWORD Lock(
    DWORD dwTimeOut = INFINITE,  
    BOOL bWaitForAll = TRUE,  
    DWORD dwWakeMask = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwTimeOut*  
 Spécifie la quantité de temps d’attente de l’objet de synchronisation soit disponible (signalé). Si **infinie**, `Lock` attendra jusqu'à ce que l’objet est signalé avant de retourner.  
  
 `bWaitForAll`  
 Spécifie si tous les objets attendus doivent être signalés en même temps avant de retourner. Si **FALSE**, `Lock` retourne lorsque l’un des objets attendu est signalé.  
  
 `dwWakeMask`  
 Spécifie les autres conditions qui sont autorisées à abandonner l’attente. Pour obtenir une liste complète des options disponibles pour ce paramètre, consultez la page [MsgWaitForMultipleObjects](http://msdn.microsoft.com/library/windows/desktop/ms684242) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Si `Lock` échoue, elle retourne-1. Si l’opération réussit, elle retourne une des valeurs suivantes :  
  
-   Entre **WAIT_OBJECT_0** et **WAIT_OBJECT_0** + (nombre d’objets – 1)  
  
     Si `bWaitForAll` est **TRUE**, tous les objets sont signalés (disponible). Si `bWaitForAll` est **FALSE**, la valeur de retour – **WAIT_OBJECT_0** est l’index dans le tableau d’objets de l’objet qui est signalé (disponible).  
  
- **WAIT_OBJECT_0** + (nombre d’objets)  
  
     Un événement spécifié dans `dwWakeMask` est disponible dans la file d’entrée du thread.  
  
-   Entre **WAIT_ABANDONED_0** et **WAIT_ABANDONED_0** + (nombre d’objets – 1)  
  
     Si `bWaitForAll` est **TRUE**, tous les objets sont signalés et au moins un des objets est un objet mutex abandonné. Si `bWaitForAll` est **FALSE**, la valeur de retour – **WAIT_ABANDONED_0** est l’index dans le tableau d’objets de l’objet mutex abandonné ayant respecté l’attente.  
  
- **WAIT_TIMEOUT**  
  
     L’intervalle de délai d’expiration spécifié dans *dwTimeOut* la réussite d’attente a expiré.  
  
### <a name="remarks"></a>Remarques  
 Si `bWaitForAll` est **TRUE**, `Lock` renvoie correctement dès que tous les objets de synchronisation soient signalés simultanément. Si `bWaitForAll` est **FALSE**, `Lock` retournera dès qu’un ou plusieurs des objets de synchronisation sont signalé.  
  
 Si `Lock` n’est pas en mesure de retourner immédiatement, il devra attendre ne dépasse pas le nombre de millisecondes spécifié dans le *dwTimeOut* paramètre avant de retourner. Si *dwTimeOut* est **infinie**, `Lock` ne renvoie pas jusqu'à ce que l’accès à un objet est acquise ou une condition spécifiée dans `dwWakeMask` a été remplie. Sinon, si `Lock` a été en mesure d’acquérir un objet de synchronisation, elle retournera avec succès ; dans le cas contraire, elle retournera l’échec.  
  
##  <a name="unlock"></a>CMultiLock::Unlock  
 Libère l’objet de synchronisation détenu par `CMultiLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lCount`  
 Numéro de référence du compte pour la version. Doit être supérieure à 0. Si la quantité spécifiée peut provoquer le nombre de l’objet dépasse sa valeur maximale, le nombre n’est pas modifié et la fonction retourne **FALSE**.  
  
 `lPrevCount`  
 Pointe vers une variable devant recevoir le nombre précédent de l’objet de synchronisation. Si **NULL**, le compteur précédent n’est pas retourné.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée par `CMultiLock`du destructeur.  
  
 La première forme de `Unlock` tente de déverrouiller l’objet de synchronisation géré par `CMultiLock`. La deuxième forme de `Unlock` tente de déverrouiller le `CSemaphore` objets possédés par `CMultiLock`. Si `CMultiLock` ne possède pas les verrouillé `CSemaphore` de l’objet, la fonction retourne **FALSE**; sinon, elle retourne **TRUE**. `lCount`et `lpPrevCount` sont exactement les mêmes que les paramètres de [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock). La deuxième forme de `Unlock` est rarement applicable aux situations multilock.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




