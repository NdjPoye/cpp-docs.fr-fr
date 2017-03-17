---
title: Classe de CAutoRevertImpersonation | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::CAutoRevertImpersonation
- ATLSECURITY/ATL::CAutoRevertImpersonation::Attach
- ATLSECURITY/ATL::CAutoRevertImpersonation::Detach
- ATLSECURITY/ATL::CAutoRevertImpersonation::GetAccessToken
dev_langs:
- C++
helpviewer_keywords:
- CAutoRevertImpersonation class
ms.assetid: 43732849-1940-4bd4-9d52-7a5698bb8838
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
ms.sourcegitcommit: 050e7483670bd32f633660ba44491c8bb3fc462d
ms.openlocfilehash: f86f1e5067583b3c4c615c8ca3095e8b67b3fffe
ms.lasthandoff: 02/24/2017

---
# <a name="cautorevertimpersonation-class"></a>CAutoRevertImpersonation (classe)
Cette classe rétablit [CAccessToken](../../atl/reference/caccesstoken-class.md) objets dans un état nonimpersonating lorsqu’il devient hors de portée.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAutoRevertImpersonation
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoRevertImpersonation::CAutoRevertImpersonation](#cautorevertimpersonation)|Construit un `CAutoRevertImpersonation` objet|  
|[CAutoRevertImpersonation :: ~ CAutoRevertImpersonation](#dtor)|Détruit l’objet et rétablit le jeton d’emprunt d’identité de l’accès.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAutoRevertImpersonation::Attach](#attach)|Automatise l’inversion de l’emprunt d’identité d’un jeton d’accès.|  
|[CAutoRevertImpersonation::Detach](#detach)|Annule l’inversion de l’emprunt d’identité automatique.|  
|[CAutoRevertImpersonation::GetAccessToken](#getaccesstoken)|Récupère l’actuel jeton accès associé à cet objet.|  
  
## <a name="remarks"></a>Remarques  
 Un [jeton d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374909) est un objet qui décrit le contexte de sécurité d’un processus ou un thread et alloué à chaque utilisateur connecté à un système Windows NT ou Windows 2000. Ces jetons d’accès peuvent être représentés avec la `CAccessToken` classe.  
  
 Il est parfois nécessaire d’emprunter l’identité des jetons d’accès. Cette classe est fournie pour des raisons pratiques, mais il n’effectue pas l’emprunt d’identité des jetons d’accès ; elle effectue uniquement l’inversion automatique à un état nonimpersonated. Il s’agit car l’emprunt d’identité du jeton d’accès peut être effectuée de différentes manières.  
  
 Pour une présentation du modèle de contrôle d’accès dans Windows, consultez la page [le contrôle d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsecurity.h  
  
##  <a name="attach"></a>CAutoRevertImpersonation::Attach  
 Automatise l’inversion de l’emprunt d’identité d’un jeton d’accès.  
  
```
void Attach(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pAT`  
 L’adresse de la [CAccessToken](../../atl/reference/caccesstoken-class.md) objet à rétablir automatiquement  
  
### <a name="remarks"></a>Remarques  
 Cette méthode doit être utilisée uniquement si la [CAutoRevertImpersonation](../../atl/reference/cautorevertimpersonation-class.md) objet a été créé avec une valeur NULL `CAccessToken` pointeur, ou si [détachement](#detach) a été appelé précédemment. Pour les cas simples, il n’est pas nécessaire d’utiliser cette méthode.  
  
##  <a name="cautorevertimpersonation"></a>CAutoRevertImpersonation::CAutoRevertImpersonation  
 Construit un objet `CAutoRevertImpersonation`.  
  
```
CAutoRevertImpersonation(const CAccessToken* pAT) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `pAT`  
 L’adresse de la [CAccessToken](../../atl/reference/caccesstoken-class.md) objet à être restauré automatiquement.  
  
### <a name="remarks"></a>Remarques  
 L’emprunt d’identité réelle du jeton d’accès doit être effectuée séparément à partir d’et de préférence avant la création d’un `CAutoRevertImpersonation` objet. Cet emprunt d’identité est automatiquement restauré lorsque le `CAutoRevertImpersonation` objet devient hors de portée.  
  
##  <a name="dtor"></a>CAutoRevertImpersonation :: ~ CAutoRevertImpersonation  
 Détruit l’objet et rétablit le jeton d’emprunt d’identité de l’accès.  
  
```
~CAutoRevertImpersonation() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Rétablit un emprunt d’identité actuellement en vigueur pour le [CAccessToken](../../atl/reference/caccesstoken-class.md) objet fourni à la construction ou via la [Attach](#attach) (méthode). Si aucune `CAccessToken` est associé, le destructeur n’a aucun effet.  
  
##  <a name="detach"></a>CAutoRevertImpersonation::Detach  
 Annule l’inversion de l’emprunt d’identité automatique.  
  
```
const CAccessToken* Detach() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’adresse d’associé précédemment [CAccessToken](../../atl/reference/caccesstoken-class.md), ou NULL si aucune association n’existe.  
  
### <a name="remarks"></a>Remarques  
 Appel de **détachement** empêche le `CAutoRevertImpersonation` objet de rétrograder un emprunt d’identité actuellement en vigueur pour le [CAccessToken](../../atl/reference/caccesstoken-class.md) objet associé à cet objet. `CAutoRevertImpersonation`peuvent être détruits sans aucune incidence ou réassocié à la même ou un autre `CAccessToken` à l’aide de l’objet [Attach](#attach).  
  
##  <a name="getaccesstoken"></a>CAutoRevertImpersonation::GetAccessToken  
 Récupère l’actuel jeton accès associé à cet objet.  
  
```
const CAccessToken* GetAccessToken() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’adresse d’associé précédemment [CAccessToken](../../atl/reference/caccesstoken-class.md), ou NULL si aucune association n’existe.  
  
### <a name="remarks"></a>Remarques  
 Si cette méthode est appelée dans le cadre qui incluent la nouvelle version d’un emprunt d’identité de le `CAccessToken` objet, le [détachement](#detach) méthode doit être utilisée à la place.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple ATLSecurity](../../visual-cpp-samples.md)   
 [Jetons d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374909)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

