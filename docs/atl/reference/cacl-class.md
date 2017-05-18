---
title: Classe de CAcl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CAcl
- ATLSECURITY/ATL::CAcl
- ATLSECURITY/ATL::CAcl::CAccessMaskArray
- ATLSECURITY/ATL::CAcl::CAceFlagArray
- ATLSECURITY/ATL::CAcl::CAceTypeArray
- ATLSECURITY/ATL::CAcl::CAcl
- ATLSECURITY/ATL::CAcl::GetAceCount
- ATLSECURITY/ATL::CAcl::GetAclEntries
- ATLSECURITY/ATL::CAcl::GetAclEntry
- ATLSECURITY/ATL::CAcl::GetLength
- ATLSECURITY/ATL::CAcl::GetPACL
- ATLSECURITY/ATL::CAcl::IsEmpty
- ATLSECURITY/ATL::CAcl::IsNull
- ATLSECURITY/ATL::CAcl::RemoveAce
- ATLSECURITY/ATL::CAcl::RemoveAces
- ATLSECURITY/ATL::CAcl::SetEmpty
- ATLSECURITY/ATL::CAcl::SetNull
dev_langs:
- C++
helpviewer_keywords:
- CAcl class
ms.assetid: 20bcb9af-dc1c-4737-b923-3864776680d6
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
ms.openlocfilehash: 52de083664c2e9ca00a140450cb43372aff28428
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cacl-class"></a>CAcl (classe)
Cette classe est un wrapper pour un `ACL` structure (liste de contrôle d’accès).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CAcl
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAcl::CAccessMaskArray](#caccessmaskarray)|Un tableau de `ACCESS_MASK`s.|  
|[CAcl::CAceFlagArray](#caceflagarray)|Un tableau de `BYTE`s.|  
|[CAcl::CAceTypeArray](#cacetypearray)|Un tableau de `BYTE`s.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAcl::CAcl](#cacl)|Constructeur.|  
|[CAcl :: ~ CAcl](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAcl::GetAceCount](#getacecount)|Retourne le nombre de contrôle d’accès aux objets d’entrée (ACE).|  
|[CAcl::GetAclEntries](#getaclentries)|Récupère les entrées de contrôle d’accès (ACL) à partir de la `CAcl` objet.|  
|[CAcl::GetAclEntry](#getaclentry)|Récupère toutes les informations sur une entrée dans une `CAcl` objet.|  
|[CAcl::GetLength](#getlength)|Retourne la longueur de la liste ACL.|  
|[CAcl::GetPACL](#getpacl)|Retourne un PACL (pointeur vers une liste ACL).|  
|[CAcl::IsEmpty](#isempty)|Tests du `CAcl` objet pour les entrées.|  
|[CAcl::IsNull](#isnull)|Retourne l’état de la `CAcl` objet.|  
|[CAcl::RemoveAce](#removeace)|Supprime un ACE spécifique (entrée de contrôle d’accès) de la `CAcl` objet.|  
|[CAcl::RemoveAces](#removeaces)|Supprime toutes les ACE (entrées de contrôle d’accès) de la `CAcl` qui s’appliquent à la donnée `CSid`.|  
|[CAcl::SetEmpty](#setempty)|Marque le `CAcl` de l’objet comme étant vide.|  
|[CAcl::SetNull](#setnull)|Marque le `CAcl` de l’objet en tant que `NULL`.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[ACL const CAcl::operator *](#operator_const_acl__star)|Les casts un `CAcl` de l’objet à un `ACL` structure.|  
|[CAcl::operator =](#operator_eq)|Opérateur d'assignation.|  
  
## <a name="remarks"></a>Remarques  
 Le **ACL** structure est l’en-tête d’une liste ACL (liste de contrôle d’accès). Une ACL inclut une liste séquentielle de zéro ou plusieurs [ACE](http://msdn.microsoft.com/library/windows/desktop/aa374868) (entrées de contrôle d’accès). L’ACE dans la ACL individuels sont numérotés de 0 à *n-1*, où *n* est le nombre d’entrées dans la liste ACL. Lors de la modification d’une ACL, une application fait référence à une entrée de contrôle d’accès (ACE) dans la liste ACL par son index.  
  
 Il existe deux types d’ACL :  
  
-   Discrétionnaire  
  
-   Système  
  
 Une ACL est contrôlée par le propriétaire d’un objet ou de toute personne accordées **WRITE_DAC** accès à l’objet. Il spécifie que les groupes et des utilisateurs spécifiques accès peuvent avoir à un objet. Par exemple, le propriétaire d’un fichier peut utiliser une ACL pour contrôler quels utilisateurs et groupes peuvent et ne peut pas accéder au fichier.  
  
 Un objet peut également avoir des informations de sécurité au niveau du système associées, sous la forme d’un système ACL contrôlée par un administrateur système. Un ACL du système peut permettre à l’administrateur système auditer les tentatives d’accéder à un objet.  
  
 Pour plus d’informations, consultez la [ACL](http://msdn.microsoft.com/library/windows/desktop/aa374872) discussion dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour une présentation du modèle de contrôle d’accès dans Windows, consultez la page [le contrôle d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsecurity.h  
  
##  <a name="caccessmaskarray"></a>CAcl::CAccessMaskArray  
 Tableau d’objets ACCESS_MASK.  
  
```
typedef CAtlArray<ACCESS_MASK> CAccessMaskArray;
```  
  
### <a name="remarks"></a>Remarques  
 Ce typedef Spécifie le type de tableau qui peut être utilisé pour stocker des droits d’accès utilisés dans les entrées de contrôle d’accès (ACE).  
  
##  <a name="caceflagarray"></a>CAcl::CAceFlagArray  
 Un tableau d’octets.  
  
```
typedef CAtlArray<BYTE> CAceFlagArray;
```  
  
### <a name="remarks"></a>Remarques  
 Ce typedef Spécifie le type de tableau permet de définir les indicateurs de contrôle spécifiques au type de contrôle d’accès d’entrée. Consultez le [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) définition pour une liste complète des indicateurs possibles.  
  
##  <a name="cacetypearray"></a>CAcl::CAceTypeArray  
 Un tableau d’octets.  
  
```
typedef CAtlArray<BYTE> CAceTypeArray;
```  
  
### <a name="remarks"></a>Remarques  
 Ce typedef Spécifie le type de tableau permet de définir la nature des objets d’entrée contrôle d’accès, telles que ACCESS_ALLOWED_ACE_TYPE ou ACCESS_DENIED_ACE_TYPE. Consultez le [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) définition pour une liste complète des types possibles.  
  
##  <a name="cacl"></a>CAcl::CAcl  
 Constructeur.  
  
```
CAcl() throw();
CAcl(const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rhs`  
 Objet `CAcl` existant.  
  
### <a name="remarks"></a>Remarques  
 Le `CAcl` objet peut être éventuellement créé à l’aide d’un fichier `CAcl` objet.  
  
##  <a name="dtor"></a>CAcl :: ~ CAcl  
 Destructeur.  
  
```
virtual ~CAcl() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Le destructeur libère les ressources acquises par l’objet.  
  
##  <a name="getacecount"></a>CAcl::GetAceCount  
 Retourne le nombre de contrôle d’accès aux objets d’entrée (ACE).  
  
```
virtual UINT GetAceCount() const throw() = 0;
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le nombre d’entrées ACE dans le `CAcl` objet.  
  
##  <a name="getaclentries"></a>CAcl::GetAclEntries  
 Récupère les entrées de contrôle d’accès (ACL) à partir de la `CAcl` objet.  
  
```
void GetAclEntries(
    CSid::CSidArray* pSids,
    CAccessMaskArray* pAccessMasks = NULL,
    CAceTypeArray* pAceTypes = NULL,
    CAceFlagArray* pAceFlags = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSids`  
 Un pointeur vers un tableau de [CSid](../../atl/reference/csid-class.md) objets.  
  
 *pAccessMasks*  
 Les masques d’accès.  
  
 *pAceTypes*  
 L’entrée de contrôle d’accès ( **ACE**) types.  
  
 *pAceFlags*  
 Le **ACE** indicateurs.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode remplit des paramètres de tableau avec les détails de chaque **ACE** objet contenu dans le `CAcl` objet. Utilisez NULL lorsque les détails de ce tableau particulière ne sont pas requises.  
  
 Le contenu de chaque tableau correspondre à l’autre, autrement dit, le premier élément de la `CAccessMaskArray` tableau correspond au premier élément dans le `CSidArray` tableau et ainsi de suite.  
  
 Consultez la page [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) pour plus d’informations sur les types d’ACE et les indicateurs.  
  
##  <a name="getaclentry"></a>CAcl::GetAclEntry  
 Récupère toutes les informations sur une entrée dans une liste de contrôle d’accès (ACL).  
  
```
void GetAclEntry(
    UINT nIndex,
    CSid* pSid,
    ACCESS_MASK* pMask = NULL,
    BYTE* pType = NULL,
    BYTE* pFlags = NULL,
    GUID* pObjectType = NULL,
    GUID* pInheritedObjectType = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de l’entrée ACL à récupérer.  
  
 `pSid`  
 Le [CSid](../../atl/reference/csid-class.md) de l’objet auquel s’applique l’entrée ACL.  
  
 *pMask*  
 Le masque spécifiant les autorisations à accorder ou refuser l’accès.  
  
 `pType`  
 Le type d’ACE.  
  
 `pFlags`  
 Les indicateurs ACE.  
  
 `pObjectType`  
 Type d'objet. Cela est fixé à GUID_NULL si le type d’objet n’est pas spécifié dans l’ACE, ou si l’ACE n’est pas un ACE d’objet.  
  
 `pInheritedObjectType`  
 Le type d’objet hérité. Cela est fixé à GUID_NULL si le type d’objet hérité n’est pas spécifié dans l’ACE, ou si l’ACE n’est pas un ACE d’objet.  
  
### <a name="remarks"></a>Notes  
 Cette méthode récupère toutes les informations concernant un ACE individuel, en fournissant davantage d’informations que [CAcl::GetAclEntries](#getaclentries) seul rend disponibles.  
  
 Consultez la page [ACE_HEADER](http://msdn.microsoft.com/library/windows/desktop/aa374919) pour plus d’informations sur les types d’ACE et les indicateurs.  
  
##  <a name="getlength"></a>CAcl::GetLength  
 Retourne la longueur de la liste de contrôle d’accès (ACL).  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la longueur en octets nécessaires pour contenir la **ACL** structure.  
  
##  <a name="getpacl"></a>CAcl::GetPACL  
 Retourne un pointeur vers une liste de contrôle d’accès (ACL).  
  
```
const ACL* GetPACL() const throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le **ACL** structure.  
  
##  <a name="isempty"></a>CAcl::IsEmpty  
 Tests du `CAcl` objet pour les entrées.  
  
```
bool IsEmpty() const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Retourne **true** si le `CAcl` objet n’est pas NULL et ne contient aucune entrée. Retourne **false** si le `CAcl` objet est NULL ou contient au moins une entrée.  
  
##  <a name="isnull"></a>CAcl::IsNull  
 Retourne l’état de la `CAcl` objet.  
  
```
bool IsNull() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le `CAcl` objet est NULL, **false** dans le cas contraire.  
  
##  <a name="operator_const_acl__star"></a>ACL const CAcl::operator *  
 Les casts un `CAcl` de l’objet à un **ACL** structure (liste de contrôle d’accès).  
  
```  
operator const ACL *() const throw(...);
```  
  
### <a name="remarks"></a>Remarques  
 Retourne l’adresse de la **ACL** structure.  
  
##  <a name="operator_eq"></a>CAcl::operator =  
 Opérateur d'assignation.  
  
```
CAcl& operator= (const CAcl& rhs) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rhs`  
 Le `CAcl` à affecter à l’objet existant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence à la mise à jour `CAcl` objet.  
  
##  <a name="removeace"></a>CAcl::RemoveAce  
 Supprime un ACE spécifique (entrée de contrôle d’accès) de la **CAcl** objet.  
  
```
void RemoveAce(UINT nIndex) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `nIndex`  
 Index de l’entrée ACE à supprimer.  
  
### <a name="remarks"></a>Notes  
 Cette méthode est dérivée de [CAtlArray::RemoveAt](../../atl/reference/catlarray-class.md#removeat).  
  
##  <a name="removeaces"></a>CAcl::RemoveAces  
 Supprime interdits (entrées du contrôle d’accès) de la `CAcl` qui s’appliquent à la donnée `CSid`.  
  
```
bool RemoveAces(const CSid& rSid) throw(...)
```  
  
### <a name="parameters"></a>Paramètres  
 `rSid`  
 Référence à un objet `CSid`.  
  
##  <a name="setempty"></a>CAcl::SetEmpty  
 Marque le `CAcl` de l’objet comme étant vide.  
  
```
void SetEmpty() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Le `CAcl` peut être définie sur une valeur vide ou une valeur NULL : les deux États sont différents.  
  
##  <a name="setnull"></a>CAcl::SetNull  
 Marque le `CAcl` objet avec la valeur NULL.  
  
```
void SetNull() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Le `CAcl` peut être définie sur une valeur vide ou une valeur NULL : les deux États sont différents.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Fonctions globales de sécurité](../../atl/reference/security-global-functions.md)

