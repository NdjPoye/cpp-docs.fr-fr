---
title: CCriticalSection (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- synchronization objects, critical section
- CCriticalSection class
- critical sections
- synchronization classes, CCriticalSection class
ms.assetid: f776f74b-5b0b-4f32-9c13-2b8e4a0d7b2b
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
translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 25d4b124d089441503e9cb457e648695fc54660d
ms.lasthandoff: 02/24/2017

---
# <a name="ccriticalsection-class"></a>CCriticalSection (classe)
Représente une « section critique », un objet de synchronisation qui permet à un seul thread à la fois pour accéder à une ressource ou une section de code.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CCriticalSection : public CSyncObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CCriticalSection::CCriticalSection](#ccriticalsection)|Construit un objet `CCriticalSection`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CCriticalSection::Lock](#lock)|Permet d’accéder à la `CCriticalSection` objet.|  
|[CCriticalSection::Unlock](#unlock)|Libère l'objet `CCriticalSection`.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CCriticalSection::operator CRITICAL_SECTION *](#operator_critical_section_star)|Récupère un pointeur vers l’interne **CRITICAL_SECTION** objet.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CCriticalSection::m_sect](#m_sect)|A **CRITICAL_SECTION** objet.|  
  
## <a name="remarks"></a>Remarques  
 Les sections critiques sont utiles lorsqu’un seul thread à la fois peut être autorisé à modifier des données ou une autre ressource contrôlée. Par exemple, l’ajout de nœuds à une liste liée est un processus qui ne doivent être autorisé par un seul thread à la fois. En utilisant un `CCriticalSection` objet pour contrôler la liste liée, seul un thread à la fois peut accéder à la liste.  
  
> [!NOTE]
>  Les fonctionnalités de la `CCriticalSection` classe est fournie par une réelle Win32 **CRITICAL_SECTION** objet.  
  
 Les sections critiques sont utilisées au lieu du mutex (voir [CMutex](../../mfc/reference/cmutex-class.md)) lorsque la vitesse est essentielle et la ressource ne sera pas utilisée au-delà des limites de processus.  
  
 Il existe deux méthodes pour utiliser un `CCriticalSection` objet : autonome et incorporé dans une classe.  
  
-   Méthode autonome autonome `CCriticalSection` objet, construire le `CCriticalSection` de l’objet lorsqu’il est nécessaire. Après un retour réussi à partir du constructeur, verrouiller explicitement l’objet avec un appel à [verrou](#lock). Appelez [Unlock](#unlock) lorsque vous avez terminé l’accès à la section critique. Lors de la façon la plus claire à une personne lisant votre code source, cette méthode est plus sujette aux erreurs que vous devez penser à verrouiller et déverrouiller la section critique avant et après l’accès.  
  
     Une méthode préférable consiste à utiliser le [CSingleLock](../../mfc/reference/csinglelock-class.md) classe. Elle comporte également un `Lock` et `Unlock` (méthode), mais vous n’avez à vous soucier de déverrouillage de la ressource si une exception se produit.  
  
-   Incorporé de méthode, vous pouvez également partager une classe avec plusieurs threads en ajoutant un `CCriticalSection`-membre de données de type à la classe et le membre de données en cas de verrouillage.  
  
 Pour plus d’informations sur l’utilisation de `CCriticalSection` , consultez l’article [Multithreading : comment utiliser les Classes de synchronisation](../../parallel/multithreading-how-to-use-the-synchronization-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CSyncObject](../../mfc/reference/csyncobject-class.md)  
  
 `CCriticalSection`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxmt.h  
  
##  <a name="a-nameccriticalsectiona--ccriticalsectionccriticalsection"></a><a name="ccriticalsection"></a>CCriticalSection::CCriticalSection  
 Construit un objet `CCriticalSection`.  
  
```  
CCriticalSection();
```  
  
### <a name="remarks"></a>Remarques  
 Pour accéder ou libérer un `CCriticalSection` d’objet, de créer un [CSingleLock](../../mfc/reference/csinglelock-class.md) objet et appeler ses [verrou](../../mfc/reference/csinglelock-class.md#lock) et [Unlock](../../mfc/reference/csinglelock-class.md#unlock) fonctions membres. Si le `CCriticalSection` objet est utilisé autonome, appelez sa [Unlock](#unlock) fonction membre pour le libérer.  
  
 Si le constructeur ne peut pas allouer la mémoire système requis, une exception de mémoire (de type [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) est automatiquement levée.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CCriticalSection::Lock](#lock).  
  
##  <a name="a-namelocka--ccriticalsectionlock"></a><a name="lock"></a>CCriticalSection::Lock  
 Appelez cette fonction membre pour accéder à l’objet de section critique.  
  
```  
BOOL Lock();  
BOOL Lock(DWORD dwTimeout);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwTimeout`  
 `Lock`ignore cette valeur de paramètre.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction réussit ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 `Lock`est un appel bloquant qui ne retourne pas jusqu'à ce que l’objet de section critique est signalé (disponible).  
  
 Si les attentes temporisées sont nécessaires, vous pouvez utiliser un [CMutex](../../mfc/reference/cmutex-class.md) de l’objet au lieu d’un `CCriticalSection` objet.  
  
 Si `Lock` ne parvient pas à allouer la mémoire nécessaire du système, une exception de mémoire (de type [CMemoryException](../../mfc/reference/cmemoryexception-class.md)) est automatiquement levée.  
  
### <a name="example"></a>Exemple  
 Cet exemple illustre l’approche de section critique imbriquées en contrôlant l’accès à une ressource partagée (statiques `_strShared` objet) à l’aide d’un élément partagé `CCriticalSection` objet. Le `SomeMethod` fonction montre la mise à jour d’une ressource partagée de manière sécurisée.  
  
 [!code-cpp[NVC_MFC_Utilities&#11;](../../mfc/codesnippet/cpp/ccriticalsection-class_1.h)]  
  
##  <a name="a-namemsecta--ccriticalsectionmsect"></a><a name="m_sect"></a>CCriticalSection::m_sect  
 Contient un objet de section critique qui est utilisé par tous les `CCriticalSection` méthodes.  
  
```  
CRITICAL_SECTION m_sect;  
```  
  
##  <a name="a-nameoperatorcriticalsectionstara--ccriticalsectionoperator-criticalsection"></a><a name="operator_critical_section_star"></a>CCriticalSection::operator CRITICAL_SECTION *  
 Récupère un **CRITICAL_SECTION** objet.  
  
```  
operator CRITICAL_SECTION*();
```   
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction pour récupérer un pointeur vers l’interne **CRITICAL_SECTION** objet.  
  
##  <a name="a-nameunlocka--ccriticalsectionunlock"></a><a name="unlock"></a>CCriticalSection::Unlock  
 Versions du `CCriticalSection` objet pour une utilisation par un autre thread.  
  
```  
BOOL Unlock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si le `CCriticalSection` objet a été détenu par le thread et la version a réussi ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Si le `CCriticalSection` utilisé autonome, `Unlock` doit être appelée immédiatement après avoir terminé l’utilisation de la ressource contrôlée par la section critique. Si un [CSingleLock](../../mfc/reference/csinglelock-class.md) objet est utilisé, `CCriticalSection::Unlock` sera appelé par l’objet de verrouillage `Unlock` fonction membre.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CCriticalSection::Lock](#lock).  
  
## <a name="see-also"></a>Voir aussi  
 [CSyncObject (classe)](../../mfc/reference/csyncobject-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classe CMutex](../../mfc/reference/cmutex-class.md)

