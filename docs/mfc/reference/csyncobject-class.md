---
title: CSyncObject (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSyncObject
- AFXMT/CSyncObject
- AFXMT/CSyncObject::CSyncObject
- AFXMT/CSyncObject::Lock
- AFXMT/CSyncObject::Unlock
- AFXMT/CSyncObject::m_hObject
dev_langs:
- C++
helpviewer_keywords:
- CSyncObject class
- synchronization classes, CSyncObject
ms.assetid: c62ea6eb-a17b-4e01-aed4-321fc435a5f4
caps.latest.revision: 21
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: a1f0c8ddfbfaf129bb18c14d36b998dd37d35899
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="csyncobject-class"></a>CSyncObject (classe)
Classe virtuelle pure qui fournit une fonctionnalité commune aux objets de synchronisation dans Win32.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSyncObject : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSyncObject::CSyncObject](#csyncobject)|Construit un objet `CSyncObject`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSyncObject::Lock](#lock)|Accède à l’objet de synchronisation.|  
|[CSyncObject::Unlock](#unlock)|Accède à l’objet de synchronisation.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSyncObject::operator descripteur](#operator_handle)|Fournit l’accès à l’objet de synchronisation.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSyncObject::m_hObject](#m_hobject)|Handle de l’objet de synchronisation sous-jacent.|  
  
## <a name="remarks"></a>Notes  
 La bibliothèque Microsoft Foundation Class fournit plusieurs classes dérivées de `CSyncObject`. Il s’agit des [CEvent](../../mfc/reference/cevent-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), et [CSemaphore](../../mfc/reference/csemaphore-class.md).  
  
 Pour plus d’informations sur l’utilisation des objets de synchronisation, consultez l’article [Multithreading : comment utiliser les Classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSyncObject`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmt.h  
  
##  <a name="csyncobject"></a>CSyncObject::CSyncObject  
 Construit un objet de synchronisation avec le nom fourni.  
  
```  
explicit CSyncObject(LPCTSTR pstrName);  
virtual ~CSyncObject();
```  
  
### <a name="parameters"></a>Paramètres  
 `pstrName`  
 Nom de l'objet. Si **NULL**, *pstrName* est null.  
  
##  <a name="lock"></a>CSyncObject::Lock  
 Appelez cette fonction pour accéder à la ressource contrôlée par l’objet de synchronisation.  
  
```  
virtual BOOL Lock(DWORD dwTimeout = INFINITE);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwTimeout`  
 Spécifie la quantité de temps en millisecondes à attendre pour l’objet de synchronisation soit disponible (signalé). Si **infinie**, `Lock` attendra jusqu'à ce que l’objet est signalé avant de retourner.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Si l’objet de synchronisation est signalé, `Lock` renvoie correctement et que le thread possède maintenant l’objet. Si l’objet de synchronisation est "non signalé" (non disponible), `Lock` attend que l’objet de synchronisation soient signalés jusqu’au nombre de millisecondes spécifié dans le *dwTimeOut* paramètre. Si l’objet de synchronisation s’est pas signalé dans le laps de temps, `Lock` échoue.  
  
##  <a name="m_hobject"></a>CSyncObject::m_hObject  
 Handle de l’objet de synchronisation sous-jacent.  
  
```  
HANDLE m_hObject;  
```  
  
##  <a name="operator_handle"></a>CSyncObject::operator descripteur  
 Utilisez cet opérateur pour obtenir le handle de la `CSyncObject` objet.  
  
```  
operator HANDLE() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si l’opération réussit, le handle de l’objet de synchronisation. dans le cas contraire, **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez utiliser le handle pour appeler directement les API Windows.  
  
##  <a name="unlock"></a>CSyncObject::Unlock  
 La déclaration de `Unlock` sans paramètres est une fonction virtuelle pure et doit être substituée par toutes les classes dérivées de `CSyncObject`.  
  
```  
virtual BOOL Unlock() = 0; virtual BOOL Unlock(
    LONG lCount,  
    LPLONG lpPrevCount = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lCount`  
 Pas utilisé par l’implémentation par défaut.  
  
 `lpPrevCount`  
 Pas utilisé par l’implémentation par défaut.  
  
### <a name="return-value"></a>Valeur de retour  
 Par défaut implémentation retourne toujours **TRUE**.  
  
### <a name="remarks"></a>Notes  
 Retourne l’implémentation par défaut de la déclaration avec deux paramètres toujours **TRUE**. Cette fonction est appelée pour libérer l’accès à l’objet de synchronisation détenu par le thread appelant. La seconde déclaration est fournie pour les objets de synchronisation tels que les sémaphores qui autorisent l’accès de plusieurs d’une ressource contrôlée.  
  
## <a name="see-also"></a>Voir aussi  
 [CObject (classe)](../../mfc/reference/cobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




