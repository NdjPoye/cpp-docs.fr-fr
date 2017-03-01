---
title: Classe CMutex | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- Mutex
- CMutex
dev_langs:
- C++
helpviewer_keywords:
- CMutex class
- synchronization classes, CMutex class
- synchronization objects, mutex
- mutex
ms.assetid: 6330c050-4f01-4195-a099-2029b92f8cf1
caps.latest.revision: 22
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
ms.openlocfilehash: 159f2e02dfe44d74ebcaad687a23cef734b61fc9
ms.lasthandoff: 02/24/2017

---
# <a name="cmutex-class"></a>Classe CMutex
Représente un « mutex », un objet de synchronisation qui permet à un thread l’accès mutuellement exclusif à une ressource.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMutex : public CSyncObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMutex::CMutex](#cmutex)|Construit un objet `CMutex`.|  
  
## <a name="remarks"></a>Notes  
 Les mutex sont utiles lorsqu’un seul thread à la fois peut être autorisé à modifier des données ou une autre ressource contrôlée. Par exemple, l’ajout de nœuds à une liste liée est un processus qui ne doivent être autorisé par un seul thread à la fois. En utilisant un `CMutex` objet pour contrôler la liste liée, seul un thread à la fois peut accéder à la liste.  
  
 Pour utiliser un `CMutex` objet, construire le `CMutex` de l’objet lorsqu’il est nécessaire. Spécifiez le nom du mutex pour attendre, et que votre application doit initialement appartient. Vous pouvez consulter le mutex lorsque le constructeur retourne. Appelez [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) lorsque vous avez terminé l’accès à la ressource contrôlée.  
  
 Une autre méthode pour l’utilisation de `CMutex` objets consiste à ajouter une variable de type `CMutex` comme membre de données à la classe que vous souhaitez contrôler. Pendant la construction de l’objet contrôlé, appelez le constructeur de le `CMutex` membre de données en spécifiant si le mutex est possédé initialement, le nom du mutex (s’il doit être utilisé au-delà des limites de processus) et les attributs de sécurité souhaités.  
  
 Pour accéder aux ressources contrôlé par `CMutex` les objets de cette manière, créez tout d’abord une variable de type [CSingleLock](../../mfc/reference/csinglelock-class.md) ou [CMultiLock](../../mfc/reference/cmultilock-class.md) dans la fonction de membre de l’accès de la ressource. Appelez ensuite l’objet de verrouillage `Lock` fonction membre (par exemple, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). À ce stade, votre thread sera soit accéder à la ressource, attendez que la ressource libérée et y accéder, ou attendre que la ressource doit être publié et le délai d’expiration, ne peut pas accéder à la ressource. Dans tous les cas, la ressource a été accédée de manière thread-safe. Pour libérer la ressource, utilisez l’objet de verrouillage `Unlock` fonction membre (par exemple, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), ou permettre à l’objet verrou tombent hors de portée.  
  
 Pour plus d’informations sur l’utilisation de `CMutex` , consultez l’article [Multithreading : comment utiliser les Classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CMutex`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmt.h  
  
##  <a name="a-namecmutexa--cmutexcmutex"></a><a name="cmutex"></a>CMutex::CMutex  
 Construit un nommées ou non `CMutex` objet.  
  
```  
CMutex(
    BOOL bInitiallyOwn = FALSE,  
    LPCTSTR lpszName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttribute = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `bInitiallyOwn`  
 Spécifie si le thread créant la `CMutex` objet a initialement l’accès à la ressource contrôlée par le mutex.  
  
 `lpszName`  
 Nom de l'objet `CMutex`. Si un autre mutex portant le même nom existe, `lpszName` doit être fournie si l’objet doit être utilisé au-delà des limites de processus. Si **NULL**, l’exclusion mutuelle est sans nom. Si le nom correspond à un mutex existant, le constructeur crée un nouveau `CMutex` objet qui fait référence à l’exclusion mutuelle de ce nom. Si le nom correspond à un objet de synchronisation existant qui n’est pas un mutex, la construction échoue.  
  
 `lpsaAttribute`  
 Attributs de sécurité pour l’objet mutex. Pour obtenir une description complète de cette structure, consultez [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 Pour accéder ou libérer un `CMutex` d’objet, de créer un [CMultiLock](../../mfc/reference/cmultilock-class.md) ou [CSingleLock](../../mfc/reference/csinglelock-class.md) objet et appeler ses [verrou](../../mfc/reference/csinglelock-class.md#lock) et [Unlock](../../mfc/reference/csinglelock-class.md#unlock) fonctions membres. Si le `CMutex` objet est utilisé autonome, appelez sa `Unlock` fonction membre pour le libérer.  
  
> [!IMPORTANT]
>  Après avoir créé le `CMutex` de l’objet, utilisez [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) pour vous assurer que le mutex n’existe pas. Si le mutex n’existait inattendu, cela peut indiquer un processus non autorisés est occupation et peut être ayant l’intention d’utiliser l’exclusion mutuelle à des fins malveillantes. Dans ce cas, la procédure en termes de sécurité recommandée consiste à fermer le handle et poursuit comme si un problème est survenu lors de la création de l’objet.  
  
## <a name="see-also"></a>Voir aussi  
 [CSyncObject (classe)](../../mfc/reference/csyncobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




