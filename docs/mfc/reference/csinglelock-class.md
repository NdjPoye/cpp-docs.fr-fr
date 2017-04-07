---
title: CSingleLock (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSingleLock
- AFXMT/CSingleLock
- AFXMT/CSingleLock::CSingleLock
- AFXMT/CSingleLock::IsLocked
- AFXMT/CSingleLock::Lock
- AFXMT/CSingleLock::Unlock
dev_langs:
- C++
helpviewer_keywords:
- CSingleLock class
- threading [MFC], access control
- synchronization objects, access control
- threading [MFC], synchronization
ms.assetid: 7dae7288-8066-4a3e-85e0-78d28bfc6bc8
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
ms.openlocfilehash: b1efc2daf1c3714446223cc69f9cc2a6a3401173
ms.lasthandoff: 02/24/2017

---
# <a name="csinglelock-class"></a>CSingleLock (classe)
Représente le mécanisme de contrôle d'accès utilisé dans le contrôle de l'accès à une ressource dans un programme multithread.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSingleLock  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSingleLock::CSingleLock](#csinglelock)|Construit un objet `CSingleLock`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSingleLock::IsLocked](#islocked)|Détermine si l’objet est verrouillé.|  
|[CSingleLock::Lock](#lock)|Attend sur un objet de synchronisation.|  
|[CSingleLock::Unlock](#unlock)|Libère un objet de synchronisation.|  
  
## <a name="remarks"></a>Notes  
 `CSingleLock`n’a pas d’une classe de base.  
  
 Pour pouvoir utiliser les classes de synchronisation [CSemaphore](../../mfc/reference/csemaphore-class.md), [CMutex](../../mfc/reference/cmutex-class.md), [CCriticalSection](../../mfc/reference/ccriticalsection-class.md), et [CEvent](../../mfc/reference/cevent-class.md), vous devez créer un `CSingleLock` ou [CMultiLock](../../mfc/reference/cmultilock-class.md) objet attendent et libérer l’objet de synchronisation. Utilisez `CSingleLock` quand vous devrez seulement attendre sur un seul objet à la fois. Utilisez **CMultiLock** lorsqu’il existe plusieurs objets que vous pouvez utiliser à un moment donné.  
  
 Pour utiliser un `CSingleLock` d’objet, appeler son constructeur à l’intérieur d’une fonction membre de classe de la ressource contrôlée. Appelez ensuite la [IsLocked](#islocked) fonction membre pour déterminer si la ressource est disponible. Si c’est le cas, passez le reste de la fonction membre. Si la ressource n’est pas disponible, attendre un certain temps pour la ressource doit être publié ou renvoient une erreur. Après utilisation de la ressource, soit appeler le [Unlock](#unlock) fonctionner si les `CSingleLock` objet doit être utilisé à nouveau, ou autoriser le `CSingleLock` objet à détruire.  
  
 `CSingleLock`objets nécessitent la présence d’un objet dérivé de [CSyncObject](../../mfc/reference/csyncobject-class.md). Cela est généralement un membre de données de classe de la ressource contrôlée. Pour plus d’informations sur l’utilisation de `CSingleLock` , consultez l’article [Multithreading : comment utiliser les Classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CSingleLock`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmt.h  
  
##  <a name="csinglelock"></a>CSingleLock::CSingleLock  
 Construit un objet `CSingleLock`.  
  
```  
explicit CSingleLock(
    CSyncObject* pObject,  
    BOOL bInitialLock = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 `pObject`  
 Pointe vers l’objet de synchronisation à utiliser. Ne peut pas être **NULL**.  
  
 `bInitialLock`  
 Spécifie s’il faut initialement que vous tentez d’accéder à l’objet fourni.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est généralement appelée depuis une fonction membre de l’accès de la ressource contrôlée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities n °&19;](../../mfc/codesnippet/cpp/csinglelock-class_1.h)]  
  
##  <a name="islocked"></a>CSingleLock::IsLocked  
 Détermine si l’objet associé à le `CSingleLock` objet est "non signalé" (non disponible).  
  
```  
BOOL IsLocked();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’objet est verrouillé ; sinon 0.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities&#20;](../../mfc/codesnippet/cpp/csinglelock-class_2.h)]  
  
##  <a name="lock"></a>CSingleLock::Lock  
 Appelez cette fonction pour accéder à la ressource contrôlée par l’objet de synchronisation fourni à la `CSingleLock` constructeur.  
  
```  
BOOL Lock(DWORD dwTimeOut = INFINITE);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwTimeOut*  
 Spécifie la quantité de temps d’attente de l’objet de synchronisation soit disponible (signalé). Si **infinie**, `Lock` attendra jusqu'à ce que l’objet est signalé avant de retourner.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Si l’objet de synchronisation est signalé, `Lock` renvoie correctement et que le thread possède maintenant l’objet. Si l’objet de synchronisation est "non signalé" (non disponible), `Lock` attend que l’objet de synchronisation soient signalés jusqu’au nombre de millisecondes spécifié dans le *dwTimeOut* paramètre. Si l’objet de synchronisation s’est pas signalé dans le laps de temps, `Lock` échoue.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities n °&21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
##  <a name="unlock"></a>CSingleLock::Unlock  
 Libère l’objet de synchronisation détenu par `CSingleLock`.  
  
```  
BOOL Unlock();

 
BOOL Unlock(
    LONG lCount,  
    LPLONG lPrevCount = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lCount`  
 Nombre d’accès à la version. Doit être supérieure à 0. Si la quantité spécifiée peut provoquer le nombre de l’objet dépasse sa valeur maximale, le nombre n’est pas modifié et la fonction retourne **FALSE**.  
  
 `lPrevCount`  
 Pointe vers une variable devant recevoir le décompte précédent de l’objet de synchronisation. Si **NULL**, le compteur précédent n’est pas retourné.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction est appelée par `CSingleLock`du destructeur.  
  
 Si vous devez libérer plus d’un nombre d’accès d’un sémaphore, utilisez la deuxième forme de `Unlock` et spécifiez le nombre d’accès à la version.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFC_Utilities n °&21;](../../mfc/codesnippet/cpp/csinglelock-class_3.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CMultiLock (classe)](../../mfc/reference/cmultilock-class.md)

