---
title: critical_section, classe | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords:
- concrt/concurrency::critical_section
dev_langs:
- C++
helpviewer_keywords:
- critical_section class
ms.assetid: fa3c89d6-be5d-4d1b-bddb-8232814e6cf6
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
ms.sourcegitcommit: fc190feb08d9b221cd1cc21a9c91ad567c86c848
ms.openlocfilehash: 20a150c1aedbd9d78c84187bf29e6284a248fbc7
ms.lasthandoff: 02/24/2017

---
# <a name="criticalsection-class"></a>critical_section, classe
Mutex non réentrant qui a explicitement connaissance du runtime d'accès concurrentiel.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class critical_section;
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`native_handle_type`|Référence à un objet `critical_section`.|  
  
### <a name="public-classes"></a>Classes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[critical_section::scoped_lock, classe](#critical_section__scoped_lock_class)|Un wrapper RAII sécurisé pour un `critical_section` objet.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[critical_section, constructeur](#ctor)|Construit une nouvelle section critique.|  
|[~ critical_section, destructeur](#dtor)|Détruit une section critique.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[lock (méthode)](#lock)|Acquiert cette section critique.|  
|[native_handle (méthode)](#native_handle)|Retourne un handle natif de plateforme spécifique, s’il en existe.|  
|[try_lock (méthode)](#try_lock)|Tente d’acquérir le verrou sans se bloquer.|  
|[try_lock_for (méthode)](#try_lock_for)|Tente d’acquérir le verrou sans se bloquer pour un certain nombre de millisecondes.|  
|[Unlock (méthode)](#unlock)|Déverrouille la section critique.|  
  
## <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [des Structures de données de synchronisation](../../../parallel/concrt/synchronization-data-structures.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `critical_section`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** concrt.h  
  
 **Espace de noms :** concurrency  
  
##  <a name="a-namectora-criticalsection"></a><a name="ctor"></a>critical_section 

 Construit une nouvelle section critique.  
  
```
critical_section();
```  
  
##  <a name="a-namedtora-criticalsection"></a><a name="dtor"></a>~ critical_section 

 Détruit une section critique.  
  
```
~critical_section();
```  
  
### <a name="remarks"></a>Remarques  
 Il est probable que le verrou n’est plus maintenu lorsque le destructeur s’exécute. Autoriser la section critique détruire avec le verrou toujours détenus résultats un comportement non défini.  
  
##  <a name="a-namelocka-lock"></a><a name="lock"></a>verrou 

 Acquiert cette section critique.  
  
```
void lock();
```  
  
### <a name="remarks"></a>Remarques  
 Il est souvent plus sécurisé d’utiliser la [scoped_lock](#critical_section__scoped_lock_class) construction pour acquérir et libérer un `critical_section` objet une exception sûre.  
  
 Si le verrou est déjà contenu par le contexte d’appel, un [improper_lock](improper-lock-class.md) exception sera levée.  
  
##  <a name="a-namenativehandlea-nativehandle"></a><a name="native_handle"></a>native_handle 

 Retourne un handle natif de plateforme spécifique, s’il en existe.  
  
```
native_handle_type native_handle();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à la section critique.  
  
### <a name="remarks"></a>Remarques  
 Un `critical_section` objet n’est pas associé à un handle natif de plateforme spécifique pour le système d’exploitation Windows. La méthode retourne simplement une référence à l’objet lui-même.  
  
##  <a name="a-namecriticalsectionscopedlockclassa--criticalsectionscopedlock-class"></a><a name="critical_section__scoped_lock_class"></a>critical_section::scoped_lock, classe  
 Un wrapper RAII sécurisé pour un `critical_section` objet.  
  
```
class scoped_lock;
```  
  
##  <a name="a-namecriticalsectionscopedlockctora-scopedlockscopedlock"></a><a name="critical_section__scoped_lock_ctor"></a>scoped_lock::scoped_lock 

 Construit un `scoped_lock` de l’objet et acquiert le `critical_section` objet passé dans le `_Critical_section` paramètre. Si la section critique est détenue par un autre thread, cet appel se bloquera.  
  
```
explicit _CRTIMP scoped_lock(critical_section& _Critical_section);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Critical_section`  
 La section critique à verrouiller.  
  
##  <a name="a-namecriticalsectionscopedlockdtora-scopedlockscopedlock"></a><a name="critical_section__scoped_lock_dtor"></a>scoped_lock :: ~ scoped_lock 

 Détruit une `scoped_lock` de l’objet et libère la section critique fournie dans son constructeur.  
  
```
~scoped_lock();
```  
  
##  <a name="a-nametrylocka-trylock"></a><a name="try_lock"></a>try_lock 

 Tente d’acquérir le verrou sans se bloquer.  
  
```
bool try_lock();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si le verrou a été acquis, la valeur `true`; sinon, la valeur `false`.  
  
##  <a name="a-nametrylockfora-trylockfor"></a><a name="try_lock_for"></a>try_lock_for 

 Tente d’acquérir le verrou sans se bloquer pour un certain nombre de millisecondes.  
  
```
bool try_lock_for(unsigned int _Timeout);
```  
  
### <a name="parameters"></a>Paramètres  
 `_Timeout`  
 Le nombre de millisecondes à attendre avant l’expiration du délai.  
  
### <a name="return-value"></a>Valeur de retour  
 Si le verrou a été acquis, la valeur `true`; sinon, la valeur `false`.  
  
##  <a name="a-nameunlocka-unlock"></a><a name="unlock"></a>déverrouiller 

 Déverrouille la section critique.  
  
```
void unlock();
```  
  
## <a name="see-also"></a>Voir aussi  
 [accès concurrentiel Namespace](concurrency-namespace.md)   
 [reader_writer_lock, classe](reader-writer-lock-class.md)

