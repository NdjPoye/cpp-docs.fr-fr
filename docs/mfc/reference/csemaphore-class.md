---
title: CSemaphore (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSemaphore
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, semaphores
- CSemaphore class
- semaphores
ms.assetid: 385fc7e4-8f86-4be2-85e1-d23b38c12f7f
caps.latest.revision: 23
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
ms.openlocfilehash: 31de1e553ea2facea6b70c284aecdbf10e22c89f
ms.lasthandoff: 02/24/2017

---
# <a name="csemaphore-class"></a>CSemaphore (classe)
Un objet de la classe `CSemaphore` représente un « sémaphore », un objet de synchronisation qui permet à un nombre limité de threads dans un ou plusieurs processus pour accéder à un maintien du nombre de threads qui accèdent à une ressource spécifiée.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSemaphore : public CSyncObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSemaphore::CSemaphore](#csemaphore)|Construit un objet `CSemaphore`.|  
  
## <a name="remarks"></a>Notes  
 Les sémaphores sont utiles pour contrôler l’accès à une ressource partagée prenant uniquement en charge un nombre limité d’utilisateurs. Le nombre actuel de la `CSemaphore` objet est le nombre d’utilisateurs supplémentaires autorisés. Lorsque le décompte atteint zéro, toutes les tentatives d’utiliser les ressources contrôlées par le **CSemaphore** objet est inséré dans une file d’attente du système et ils attendre un délai d’attente ou le nombre s’élève au-dessus de 0. Le nombre maximal d’utilisateurs pouvant accéder simultanément à la ressource contrôlée est spécifié pendant la construction de la `CSemaphore` objet.  
  
 Pour utiliser un **CSemaphore** objet, construire le `CSemaphore` de l’objet lorsqu’il est nécessaire. Spécifiez le nom du sémaphore pour attendre, et que votre application doit initialement appartient. Vous pouvez consulter le sémaphore lorsque le constructeur retourne. Appelez [CSyncObject::Unlock](../../mfc/reference/csyncobject-class.md#unlock) lorsque vous avez terminé l’accès à la ressource contrôlée.  
  
 Une autre méthode pour l’utilisation de `CSemaphore` objets consiste à ajouter une variable de type `CSemaphore` comme membre de données à la classe que vous souhaitez contrôler. Pendant la construction de l’objet contrôlé, appelez le constructeur de le `CSemaphore` membre de données en spécifiant le premier accéder au nombre total d’accès maximal, nom du sémaphore (s’il doit être utilisé au-delà des limites de processus) et les attributs de sécurité souhaités.  
  
 Pour accéder aux ressources contrôlé par `CSemaphore` les objets de cette manière, créez tout d’abord une variable de type [CSingleLock](../../mfc/reference/csinglelock-class.md) ou [CMultiLock](../../mfc/reference/cmultilock-class.md) dans la fonction de membre de l’accès de la ressource. Appelez ensuite l’objet de verrouillage `Lock` fonction membre (par exemple, [CSingleLock::Lock](../../mfc/reference/csinglelock-class.md#lock)). À ce stade, votre thread sera soit accéder à la ressource, attendez que la ressource libérée et y accéder, ou attendre que la ressource doit être publié et le délai d’expiration, ne peut pas accéder à la ressource. Dans tous les cas, la ressource a été accédée de manière thread-safe. Pour libérer la ressource, utilisez l’objet de verrouillage `Unlock` fonction membre (par exemple, [CSingleLock::Unlock](../../mfc/reference/csinglelock-class.md#unlock)), ou permettre à l’objet verrou tombent hors de portée.  
  
 Vous pouvez également créer un **CSemaphore** autonome de l’objet et y accéder explicitement avant de tenter d’accéder à la ressource contrôlée. Lors de la façon la plus claire à une personne lisant votre code source, cette méthode est plus sujette aux erreurs.  
  
 Pour plus d’informations sur l’utilisation de **CSemaphore** , consultez l’article [Multithreading : comment utiliser les Classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CSemaphore`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmt.h  
  
##  <a name="a-namecsemaphorea--csemaphorecsemaphore"></a><a name="csemaphore"></a>CSemaphore::CSemaphore  
 Construit un nommées ou non `CSemaphore` objet.  
  
```  
CSemaphore(
    LONG lInitialCount = 1,  
    LONG lMaxCount = 1,  
    LPCTSTR pstrName = NULL,  
    LPSECURITY_ATTRIBUTES lpsaAttributes = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 *lInitialCount*  
 Le décompte d’utilisation initial pour le sémaphore. Doit être supérieur ou égal à 0 et inférieur ou égal à `lMaxCount`.  
  
 `lMaxCount`  
 Le décompte d’utilisation maximale pour le sémaphore. Doit être supérieure à 0.  
  
 `pstrName`  
 Nom du sémaphore. Doit être fourni si le sémaphore est accessible au-delà des limites de processus. Si `NULL,` l’objet est sans nom. Si le nom correspond à un sémaphore existant, le constructeur crée un nouveau `CSemaphore` objet qui référence le sémaphore de ce nom. Si le nom correspond à un objet de synchronisation existant qui n’est pas un sémaphore, la construction échoue.  
  
 *lpsaAttributes*  
 Attributs de sécurité pour l’objet de sémaphore. Pour obtenir une description complète de cette structure, consultez [SECURITY_ATTRIBUTES](http://msdn.microsoft.com/library/windows/desktop/aa379560) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="remarks"></a>Notes  
 Pour accéder ou libérer un `CSemaphore` d’objet, de créer un [CMultiLock](../../mfc/reference/cmultilock-class.md) ou [CSingleLock](../../mfc/reference/csinglelock-class.md) objet et appeler ses [verrou](../../mfc/reference/csinglelock-class.md#lock) et [Unlock](../../mfc/reference/csinglelock-class.md#unlock) fonctions membres.  
  
> [!IMPORTANT]
>  Après avoir créé le `CSemaphore` de l’objet, utilisez [GetLastError](http://msdn.microsoft.com/library/windows/desktop/ms679360) pour vous assurer que le mutex n’existe pas. Si le mutex n’existait inattendu, cela peut indiquer un processus non autorisés est occupation et peut être ayant l’intention d’utiliser l’exclusion mutuelle à des fins malveillantes. Dans ce cas, la procédure en termes de sécurité recommandée consiste à fermer le handle et poursuit comme si un problème est survenu lors de la création de l’objet.  
  
## <a name="see-also"></a>Voir aussi  
 [CSyncObject (classe)](../../mfc/reference/csyncobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




