---
title: Classe de CHandle | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL.CHandle
- ATL::CHandle
- CHandle
dev_langs:
- C++
helpviewer_keywords:
- CHandle class
ms.assetid: 883e9db5-40ec-4e29-9c74-4dd2ddd2e35d
caps.latest.revision: 19
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: bbc0703ae5eaab01c0819be7e378509c7dc579ef
ms.lasthandoff: 02/24/2017

---
# <a name="chandle-class"></a>CHandle (classe)
Cette classe fournit des méthodes pour créer et utiliser un objet handle.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CHandle
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CHandle::CHandle](#chandle)|Constructeur.|  
|[CHandle :: ~ CHandle](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CHandle::Attach](#attach)|Appelez cette méthode pour attacher le `CHandle` objet à un handle existant.|  
|[CHandle::Close](#close)|Appelez cette méthode pour fermer une `CHandle` objet.|  
|[CHandle::Detach](#detach)|Appelez cette méthode pour détacher un handle d’un `CHandle` objet.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CHandle::operator descripteur](#operator_handle)|Retourne la valeur du handle stockée.|  
|[CHandle::operator =](#operator_eq)|Opérateur d'assignation.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CHandle::m_h](#m_h)|La variable de membre qui stocke le descripteur.|  
  
## <a name="remarks"></a>Notes  
 A `CHandle` objet peut être utilisé chaque fois qu’un descripteur est nécessaire : la principale différence est que le `CHandle` objet sera automatiquement supprimé.  
  
> [!NOTE]
>  Certaines fonctions API utilisera NULL en tant que handle vide ou non valide, tandis que d’autres utilisent INVALID_HANDLE_VALUE. `CHandle`utilise NULL et ne traitez INVALID_HANDLE_VALUE comme un handle réel. Si vous appelez une API qui peut retourner INVALID_HANDLE_VALUE, vous devez vérifier cette valeur avant d’appeler [CHandle::Attach](#attach) ou en le passant à la `CHandle` constructeur et passer à la place la valeur NULL.  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlbase.h  
  
##  <a name="a-nameattacha--chandleattach"></a><a name="attach"></a>CHandle::Attach  
 Appelez cette méthode pour attacher le `CHandle` objet à un handle existant.  
  
```
void Attach(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `h`  
 `CHandle`prend possession du handle `h`.  
  
### <a name="remarks"></a>Remarques  
 Affecte le `CHandle` de l’objet à le `h` gérer. Dans les versions débogue une ATLASSERT ; sera déclenchée si `h` a la valeur NULL. Aucune autre vérification sur la validité de la poignée est effectuée.  
  
##  <a name="a-namechandlea--chandlechandle"></a><a name="chandle"></a>CHandle::CHandle  
 Constructeur.  
  
```
CHandle() throw();
CHandle(CHandle& h) throw();
explicit CHandle(HANDLE h) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `h`  
 Un handle existant ou `CHandle`.  
  
### <a name="remarks"></a>Notes  
 Crée un objet `CHandle` de l’objet, en utilisant éventuellement un handle existant ou `CHandle` objet.  
  
##  <a name="a-namedtora--chandlechandle"></a><a name="dtor"></a>CHandle :: ~ CHandle  
 Destructeur.  
  
```
~CHandle() throw();
```  
  
### <a name="remarks"></a>Notes  
 Libère le `CHandle` objet en appelant [CHandle::Close](#close).  
  
##  <a name="a-nameclosea--chandleclose"></a><a name="close"></a>CHandle::Close  
 Appelez cette méthode pour fermer une `CHandle` objet.  
  
```
void Close() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Ferme le handle d’objet ouvert. Si le handle est NULL, ce qui sera le cas si **fermer** a déjà été appelée, une ATLASSERT ; sera déclenchée dans les versions debug.  
  
##  <a name="a-namedetacha--chandledetach"></a><a name="detach"></a>CHandle::Detach  
 Appelez cette méthode pour détacher un handle d’un `CHandle` objet.  
  
```
HANDLE Detach() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le handle qui est détaché.  
  
### <a name="remarks"></a>Remarques  
 Libère la possession du handle.  
  
##  <a name="a-namemha--chandlemh"></a><a name="m_h"></a>CHandle::m_h  
 La variable de membre qui stocke le descripteur.  
  
```
HANDLE m_h;
```  
  
##  <a name="a-nameoperatoreqa--chandleoperator-"></a><a name="operator_eq"></a>CHandle::operator =  
 L’opérateur d’assignation.  
  
```
CHandle& operator=(CHandle& h) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `h`  
 `CHandle`prend possession du handle `h`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence à la nouvelle `CHandle` objet.  
  
### <a name="remarks"></a>Remarques  
 Si le `CHandle` objet contient actuellement un handle, il va être fermée. Le `CHandle` de l’objet passé dans aura sa référence handle la valeur NULL. Cela garantit que deux `CHandle` objets ne contient jamais le même handle actif.  
  
##  <a name="a-nameoperatorhandlea--chandleoperator-handle"></a><a name="operator_handle"></a>CHandle::operator descripteur  
 Retourne la valeur du handle stockée.  
  
```  
operator HANDLE() const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Retourne la valeur stockée dans [CHandle::m_h](#m_h).  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

