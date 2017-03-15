---
title: Classe de CComCriticalSection | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CComCriticalSection
- CComCriticalSection
- ATL::CComCriticalSection
dev_langs:
- C++
helpviewer_keywords:
- CComCriticalSection class
ms.assetid: 44e1edd2-90be-4bfe-9739-58e8b419e7d1
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: a7c4fbc87ff06bb09766eb3e4ad0d7c5275eed65
ms.lasthandoff: 02/24/2017

---
# <a name="ccomcriticalsection-class"></a>CComCriticalSection (classe)
Cette classe fournit des méthodes permettant d’obtenir et de libérer la possession d’un objet de section critique.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CComCriticalSection
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComCriticalSection::CComCriticalSection](#ccomcriticalsection)|Constructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComCriticalSection::Init](#init)|Crée et initialise un objet de section critique.|  
|[CComCriticalSection::Lock](#lock)|Obtient la propriété de l’objet de section critique.|  
|[CComCriticalSection::Term](#term)|Libère les ressources système utilisées par l’objet de section critique.|  
|[CComCriticalSection::Unlock](#unlock)|Libère la possession de l’objet de section critique.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComCriticalSection::m_sec](#m_sec)|A **CRITICAL_SECTION** objet.|  
  
## <a name="remarks"></a>Remarques  
 `CComCriticalSection`est semblable à la classe [CComAutoCriticalSection](../../atl/reference/ccomautocriticalsection-class.md), mais vous devez explicitement initialiser et libèrera la section critique.  
  
 En général, vous utilisez `CComCriticalSection` via la `typedef` nom [CriticalSection](ccommultithreadmodel-class.md#criticalsection). Ce nom fait référence à `CComCriticalSection` lorsque [CComMultiThreadModel](../../atl/reference/ccommultithreadmodel-class.md) est utilisé.  

  
 Consultez la page [CComCritSecLock classe](../../atl/reference/ccomcritseclock-class.md) un moyen plus sûr d’utiliser cette classe à appeler la méthode `Lock` et `Unlock` directement.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcore.h  
  
##  <a name="a-nameccomcriticalsectiona--ccomcriticalsectionccomcriticalsection"></a><a name="ccomcriticalsection"></a>CComCriticalSection::CComCriticalSection  
 Constructeur.  
  
```
CComCriticalSection() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Définit les [m_sec](#m_sec) membre de données null **.**  
  
##  <a name="a-nameinita--ccomcriticalsectioninit"></a><a name="init"></a>CComCriticalSection::Init  
 Appelle la fonction Win32 [InitializeCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms683472), ce qui initialise l’objet de section critique contenue dans le [m_sec](#m_sec) membre de données.  
  
```
HRESULT Init() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` en cas de réussite, **E_OUTOFMEMORY** ou **E_FAIL** en cas d’échec.  
  
##  <a name="a-namelocka--ccomcriticalsectionlock"></a><a name="lock"></a>CComCriticalSection::Lock  
 Appelle la fonction Win32 [EnterCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682608), qui attend jusqu'à ce que le thread peut prendre possession de l’objet de section critique contenue dans le [m_sec](#m_sec) membre de données.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK` en cas de réussite, **E_OUTOFMEMORY** ou **E_FAIL** en cas d’échec.  
  
### <a name="remarks"></a>Notes  
 L’objet de section critique doit tout d’abord être initialisé avec un appel à la [Init](#init) méthode. Lorsque le code protégé a terminé son exécution, le thread doit appeler [Unlock](#unlock) pour libérer la possession de la section critique.  
  
##  <a name="a-namemseca--ccomcriticalsectionmsec"></a><a name="m_sec"></a>CComCriticalSection::m_sec  
 Contient un objet de section critique qui est utilisé par tous les `CComCriticalSection` méthodes.  
  
```
CRITICAL_SECTION m_sec;
```  
  
##  <a name="a-nameterma--ccomcriticalsectionterm"></a><a name="term"></a>CComCriticalSection::Term  
 Appelle la fonction Win32 [DeleteCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms682552), ce qui libère toutes les ressources utilisées par l’objet de section critique contenue dans le [m_sec](#m_sec) membre de données.  
  
```
HRESULT Term() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Une fois `Term` a été appelée, la critique section ne peut plus être utilisée pour la synchronisation.  
  
##  <a name="a-nameunlocka--ccomcriticalsectionunlock"></a><a name="unlock"></a>CComCriticalSection::Unlock  
 Appelle la fonction Win32 [LeaveCriticalSection](http://msdn.microsoft.com/library/windows/desktop/ms684169), ce qui libère la possession de l’objet de section critique contenue dans le [m_sec](#m_sec) membre de données.  
  
```
HRESULT Unlock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
### <a name="remarks"></a>Remarques  
 Pour obtenir la propriété tout d’abord, le thread doit appeler le [verrou](#lock) méthode. Chaque appel à `Lock` nécessite un appel à `Unlock` pour libérer la possession de la section critique.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de la classe CComFakeCriticalSection](../../atl/reference/ccomfakecriticalsection-class.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [CComCritSecLock (classe)](../../atl/reference/ccomcritseclock-class.md)

