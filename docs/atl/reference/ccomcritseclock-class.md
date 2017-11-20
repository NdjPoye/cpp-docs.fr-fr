---
title: Classe de CComCritSecLock | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComCritSecLock
- ATLBASE/ATL::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::CComCritSecLock
- ATLBASE/ATL::CComCritSecLock::Lock
- ATLBASE/ATL::CComCritSecLock::Unlock
dev_langs: C++
helpviewer_keywords: CComCritSecLock class
ms.assetid: 223152a1-86c3-4ef9-89a7-f455fe791b0e
caps.latest.revision: "19"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 3fb2bad67c6488f13297783a578118ebc022c4bd
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="ccomcritseclock-class"></a>Classe de CComCritSecLock
Cette classe fournit des méthodes de verrouillage et déverrouillage d’un objet de section critique.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template<class TLock> class CComCritSecLock
```  
  
#### <a name="parameters"></a>Paramètres  
 *TLock*  
 Objet à être verrouillé et déverrouillé.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComCritSecLock::CComCritSecLock](#ctor)|Constructeur.|  
|[CComCritSecLock :: ~ CComCritSecLock](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComCritSecLock::Lock](#lock)|Appelez cette méthode pour verrouiller l’objet de section critique.|  
|[CComCritSecLock::Unlock](#unlock)|Appelez cette méthode pour déverrouiller l’objet de section critique.|  
  
## <a name="remarks"></a>Remarques  
 Utilisez cette classe pour verrouiller et déverrouiller des objets d’une façon plus sûre qu’avec le [CComCriticalSection classe](../../atl/reference/ccomcriticalsection-class.md) ou [CComAutoCriticalSection classe](../../atl/reference/ccomautocriticalsection-class.md).  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="ctor"></a>CComCritSecLock::CComCritSecLock  
 Constructeur.  
  
```
CComCritSecLock(TLock& cs, bool bInitialLock = true);
```  
  
### <a name="parameters"></a>Paramètres  
 *cs*  
 L’objet de la section critique.  
  
 `bInitialLock`  
 L’état initial : **true** signifie verrouillé.  
  
### <a name="remarks"></a>Remarques  
 Initialise l’objet de section critique.  
  
##  <a name="dtor"></a>CComCritSecLock :: ~ CComCritSecLock  
 Destructeur.  
  
```
~CComCritSecLock() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Déverrouille l’objet de section critique.  
  
##  <a name="lock"></a>CComCritSecLock::Lock  
 Appelez cette méthode pour verrouiller l’objet de section critique.  
  
```
HRESULT Lock() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 En cas d’échec, retourne S_OK si l’objet a correctement été verrouillé, ou une erreur HRESULT.  
  
### <a name="remarks"></a>Remarques  
 Si l’objet est déjà verrouillé, une erreur d’assertion se produit dans les versions debug.  
  
##  <a name="unlock"></a>CComCritSecLock::Unlock  
 Appelez cette méthode pour déverrouiller l’objet de section critique.  
  
```
void Unlock() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Si l’objet est déjà déverrouillée, une erreur d’assertion se produit dans les versions debug.  
  
## <a name="see-also"></a>Voir aussi  
 [Classe de CComCriticalSection](../../atl/reference/ccomcriticalsection-class.md)   
 [CComAutoCriticalSection, classe](../../atl/reference/ccomautocriticalsection-class.md)
