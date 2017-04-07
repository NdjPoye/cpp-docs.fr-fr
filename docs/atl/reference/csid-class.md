---
title: Classe de CSid | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSid
- ATLSECURITY/ATL::CSid
- ATLSECURITY/ATL::CSid::CSidArray
- ATLSECURITY/ATL::CSid::CSid
- ATLSECURITY/ATL::CSid::AccountName
- ATLSECURITY/ATL::CSid::Domain
- ATLSECURITY/ATL::CSid::EqualPrefix
- ATLSECURITY/ATL::CSid::GetLength
- ATLSECURITY/ATL::CSid::GetPSID
- ATLSECURITY/ATL::CSid::GetPSID_IDENTIFIER_AUTHORITY
- ATLSECURITY/ATL::CSid::GetSubAuthority
- ATLSECURITY/ATL::CSid::GetSubAuthorityCount
- ATLSECURITY/ATL::CSid::IsValid
- ATLSECURITY/ATL::CSid::LoadAccount
- ATLSECURITY/ATL::CSid::Sid
- ATLSECURITY/ATL::CSid::SidNameUse
dev_langs:
- C++
helpviewer_keywords:
- CSid class
ms.assetid: be58b7ca-5958-49c3-a833-ca341aaaf753
caps.latest.revision: 24
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
ms.openlocfilehash: ceb0ab95d18e1336584eab45bc00ce769efd7384
ms.lasthandoff: 02/24/2017

---
# <a name="csid-class"></a>CSid (classe)
Cette classe est un wrapper pour un `SID` structure de (l’identificateur de sécurité).  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CSid
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-typedefs"></a>Typedefs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSid::CSidArray](#csidarray)|Tableau d'objets `CSid`.|  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSid::CSid](#csid)|Constructeur.|  
|[CSid :: ~ CSid](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSid::AccountName](#accountname)|Retourne le nom du compte associé avec le `CSid` objet.|  
|[CSid::Domain](#domain)|Retourne le nom de domaine associé à le `CSid` objet.|  
|[CSid::EqualPrefix](#equalprefix)|Tests `SID` préfixes (identificateur de sécurité) pour l’égalité.|  
|[CSid::GetLength](#getlength)|Retourne la longueur de la `CSid` objet.|  
|[CSid::GetPSID](#getpsid)|Retourne un pointeur vers un `SID` structure.|  
|[CSid::GetPSID_IDENTIFIER_AUTHORITY](#getpsid_identifier_authority)|Retourne un pointeur vers le **SID_IDENTIFIER_AUTHORITY** structure.|  
|[CSid::GetSubAuthority](#getsubauthority)|Retourne une sous-autorité spécifiée dans un **SID** structure.|  
|[CSid::GetSubAuthorityCount](#getsubauthoritycount)|Retourne le nombre de sous-autorité.|  
|[CSid::IsValid](#isvalid)|Tests du `CSid` objet de validité.|  
|[CSid::LoadAccount](#loadaccount)|Mises à jour la `CSid` objet étant donné le nom de compte, de domaine ou un existant `SID` structure.|  
|[CSid::Sid](#sid)|Retourne la chaîne d’identification.|  
|[CSid::SidNameUse](#sidnameuse)|Retourne une description de l’état de la `CSid` objet.|  
  
### <a name="operators"></a>Opérateurs  
  
|||  
|-|-|  
|[opérateur =](#operator_eq)|Opérateur d'assignation.|  
|[SID const opérateur *](#operator_const_sid__star)|Les casts un `CSid` objet vers un pointeur vers un `SID` structure.|  
  
### <a name="global-operators"></a>Opérateurs globaux  
  
|||  
|-|-|  
|[opérateur ==](#operator_eq_eq)|Teste si deux objets de descripteur de sécurité pour l’égalité|  
|[opérateur ! =](#operator_neq)|Teste si deux objets de descripteur de sécurité d’inégalité|  
|[(opérateur)\<](#operator_lt_)|Compare la valeur relative de deux objets de descripteurs de sécurité.|  
|[opérateur >](#operator_gt_)|Compare la valeur relative de deux objets de descripteurs de sécurité.|  
|[(opérateur)\<=](#operator_lt__eq)|Compare la valeur relative de deux objets de descripteurs de sécurité.|  
|[opérateur > =](#operator_gt__eq)|Compare la valeur relative de deux objets de descripteurs de sécurité.|  
  
## <a name="remarks"></a>Remarques  
 Le `SID` structure est une structure de longueur variable utilisée pour identifier les utilisateurs ou groupes.  
  
 Les applications ne doivent pas modifier le `SID` structure directement, mais plutôt utiliser les méthodes fournies dans cette classe wrapper. Voir aussi [AtlGetOwnerSid](http://msdn.microsoft.com/library/0e3a2606-74b8-4412-9803-bb437e22da85), [AtlSetGroupSid](http://msdn.microsoft.com/library/83531d32-11ab-4a68-a3c6-1bfa54ab8dfa), [AtlGetGroupSid](http://msdn.microsoft.com/library/8e7ec6b9-15c8-4a8a-977e-1e4c853d0be7), et [AtlSetOwnerSid](http://msdn.microsoft.com/library/3a8abb76-1d2c-465d-a5e8-62a12a3c37f3).  
  
 Pour une présentation du modèle de contrôle d’accès dans Windows, consultez la page [le contrôle d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsecurity.h  
  
##  <a name="accountname"></a>CSid::AccountName  
 Retourne le nom du compte associé avec le `CSid` objet.  
  
```
LPCTSTR AccountName() const throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le `LPCTSTR` pointant sur le nom du compte.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode tente de trouver un nom pour l’objet `SID` (identificateur de sécurité). Pour plus d’informations, consultez [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Si aucun nom de compte pour le `SID` peut être trouvé, `AccountName` renvoie une chaîne vide. Cela peut se produire si un délai d’expiration réseau empêche cette méthode de recherche du nom. Elle se produit également pour les identificateurs de sécurité sans nom de compte correspondant, par exemple une ouverture de session `SID` qui identifie une ouverture de session.  
  
##  <a name="csid"></a>CSid::CSid  
 Constructeur.  
  
```
CSid() throw();
CSid(const SID& rhs) throw(...);
CSid(const CSid& rhs) throw(...);

CSid(
    const SID_IDENTIFIER_AUTHORITY& IdentifierAuthority,
    BYTE nSubAuthorityCount,
    ...) throw(...);

explicit CSid(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

explicit CSid(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rhs`  
 Existant `CSid` objet ou `SID` structure de (l’identificateur de sécurité).  
  
 *IdentifierAuthority*  
 L’autorité.  
  
 *nSubAuthorityCount*  
 Le nombre de sous-autorité.  
  
 `pszAccountName`  
 Le nom du compte.  
  
 `pszSystem`  
 Le nom du système. Cette chaîne peut être le nom d’un ordinateur distant. Si cette chaîne est NULL, le système local est utilisé à la place.  
  
 `pSid`  
 Un pointeur vers un `SID` structure.  
  
### <a name="remarks"></a>Remarques  
 Le constructeur initialise la `CSid` objet en affectant un membre de données interne *SidTypeInvalid*, ou en copiant les paramètres d’un existant `CSid`, `SID`, ou le compte existant.  
  
 Si l’initialisation échoue, le constructeur lève une [CAtlException classe](../../atl/reference/catlexception-class.md).  
  
##  <a name="dtor"></a>CSid :: ~ CSid  
 Destructeur.  
  
```
virtual ~CSid() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Le destructeur libère les ressources acquises par l’objet.  
  
##  <a name="csidarray"></a>CSid::CSidArray  
 Un tableau de [CSid](../../atl/reference/csid-class.md) objets.  
  
```
typedef CAtlArray<CSid> CSidArray;
```  
  
### <a name="remarks"></a>Notes  
 Ce typedef Spécifie le type de tableau qui peut être utilisé pour récupérer les identificateurs de sécurité d’une ACL (liste de contrôle d’accès). Consultez la page [CAcl::GetAclEntries](../../atl/reference/cacl-class.md#getaclentries).  
  
##  <a name="domain"></a>CSid::Domain  
 Retourne le nom de domaine associé à le `CSid` objet.  
  
```
LPCTSTR Domain() const throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le `LPCTSTR` pointant sur le domaine.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode tente de trouver un nom pour l’objet `SID` (identificateur de sécurité). Pour plus d’informations, consultez [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166).  
  
 Si aucun nom de compte pour le `SID` peut être trouvé, **domaine** retourne le domaine comme une chaîne vide. Cela peut se produire si un délai d’expiration réseau empêche cette méthode de recherche du nom. Elle se produit également pour les identificateurs de sécurité sans nom de compte correspondant, par exemple une ouverture de session `SID` qui identifie une ouverture de session.  
  
##  <a name="equalprefix"></a>CSid::EqualPrefix  
 Tests `SID` préfixes (identificateur de sécurité) pour l’égalité.  
  
```
bool EqualPrefix(const SID& rhs) const throw();
bool EqualPrefix(const CSid& rhs) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `rhs`  
 Le `SID` structure de (l’identificateur de sécurité) ou `CSid` objet à comparer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** en cas de réussite, **false** en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [EqualPrefixSid](http://msdn.microsoft.com/library/windows/desktop/aa446621) dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)] pour plus de détails.  
  
##  <a name="getlength"></a>CSid::GetLength  
 Retourne la longueur de la `CSid` objet.  
  
```
UINT GetLength() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la longueur en octets de la `CSid` objet.  
  
### <a name="remarks"></a>Notes  
 Si le `CSid` structure n’est pas valide, la valeur de retour n’est pas définie. Avant d’appeler `GetLength`, utilisez la [CSid::IsValid](#isvalid) fonction membre pour vérifier que `CSid` est valide.  
  
> [!NOTE]
>  Dans les versions debug la fonction provoque une assertion si le `CSid` objet n’est pas valide.  
  
##  <a name="getpsid"></a>CSid::GetPSID  
 Retourne un pointeur vers un `SID` structure de (l’identificateur de sécurité).  
  
```
const SID* GetPSID() const throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne l’adresse de la `CSid` sous-jacent de l’objet `SID` structure.  
  
##  <a name="getpsid_identifier_authority"></a>CSid::GetPSID_IDENTIFIER_AUTHORITY  
 Retourne un pointeur vers le **SID_IDENTIFIER_AUTHORITY** structure.  
  
```
const SID_IDENTIFIER_AUTHORITY* GetPSID_IDENTIFIER_AUTHORITY() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, elle retourne l’adresse de la **SID_IDENTIFIER_AUTHORITY** structure. Si elle échoue, la valeur de retour est non définie. Échec peut se produire si le `CSid` objet n’est pas valide, auquel cas la [CSid::IsValid](#isvalid) méthode renvoie **false**. La fonction `GetLastError` peut être appelée pour les informations d’erreur étendues.  
  
> [!NOTE]
>  Dans les versions debug la fonction provoque une assertion si le `CSid` objet n’est pas valide.  
  
##  <a name="getsubauthority"></a>CSid::GetSubAuthority  
 Retourne une sous-autorité spécifiée dans un `SID` structure de (l’identificateur de sécurité).  
  
```
DWORD GetSubAuthority(DWORD nSubAuthority) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *nSubAuthority*  
 La sous-autorité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la sous-autorité référencée par *nSubAuthority.* La valeur de sous-autorité est un identificateur relatif (RID).  
  
### <a name="remarks"></a>Remarques  
 Le *nSubAuthority* paramètre spécifie l’identifiant de l’élément de tableau sous-autorité la méthode renvoie la valeur d’index. La méthode n’effectue aucun test de validation sur cette valeur. Une application peut appeler [CSid::GetSubAuthorityCount](#getsubauthoritycount) pour découvrir la plage de valeurs acceptables.  
  
> [!NOTE]
>  Dans les versions debug la fonction provoque une assertion si le `CSid` objet n’est pas valide.  
  
##  <a name="getsubauthoritycount"></a>CSid::GetSubAuthorityCount  
 Retourne le nombre de sous-autorité.  
  
```
UCHAR GetSubAuthorityCount() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Si la méthode réussit, la valeur de retour est le nombre de sous-autorité.  
  
 Si la méthode échoue, la valeur de retour est non définie. La méthode échoue si le `CSid` objet n’est pas valide. Pour obtenir des informations plus complètes sur les erreurs, appelez `GetLastError`.  
  
> [!NOTE]
>  Dans les versions debug la fonction provoque une assertion si le `CSid` objet n’est pas valide.  
  
##  <a name="isvalid"></a>CSid::IsValid  
 Tests du `CSid` objet de validité.  
  
```
bool IsValid() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** si le `CSid` objet est valide, **false** dans le cas contraire. Aucune information d’erreur étendue pour cette méthode ; n’appelez pas `GetLastError`.  
  
### <a name="remarks"></a>Remarques  
 Le `IsValid` méthode valide les `CSid` objet en vérifiant que le numéro de révision est comprise dans une plage connue et que le nombre de sous-autorités est inférieur au nombre maximal.  
  
##  <a name="loadaccount"></a>CSid::LoadAccount  
 Mises à jour le `CSid` objet étant donné le nom de compte, de domaine ou une structure SID (identificateur de sécurité) existante.  
  
```
bool LoadAccount(
    LPCTSTR pszAccountName,
    LPCTSTR pszSystem = NULL) throw(...);

bool LoadAccount(
    const SID* pSid,
    LPCTSTR pszSystem = NULL) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pszAccountName`  
 Le nom du compte.  
  
 `pszSystem`  
 Le nom du système. Cette chaîne peut être le nom d’un ordinateur distant. Si cette chaîne est NULL, le système local est utilisé à la place.  
  
 `pSid`  
 Un pointeur vers un [SID](http://msdn.microsoft.com/library/windows/desktop/aa379594\(v=vs.85\).aspx) structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **true** en cas de réussite, **false** en cas d’échec. Pour obtenir des informations plus complètes sur les erreurs, appelez `GetLastError`.  
  
### <a name="remarks"></a>Remarques  
 `LoadAccount`tente de trouver un identificateur de sécurité pour le nom spécifié. Consultez la page [LookupAccountSid](http://msdn.microsoft.com/library/windows/desktop/aa379166\(v=vs.85\).aspx) pour plus de détails.  
  
##  <a name="operator_eq"></a>CSid::operator =  
 Opérateur d'assignation.  
  
```
CSid& operator= (const CSid& rhs) throw(...);  
CSid& operator= (const SID& rhs) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` à affecter à la `CSid` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne une référence à la mise à jour `CSid` objet.  
  
##  <a name="operator_eq_eq"></a>CSid::operator ==  
 Teste si deux objets de descripteur de sécurité d’égalité.  
  
```
bool operator==(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté gauche de l’opérateur ==.  
  
 `rhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté droit de l’opérateur ==.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les descripteurs de sécurité sont égaux, sinon **false**.  
  
##  <a name="operator_neq"></a>CSid::operator ! =  
 Teste si deux objets de descripteur de sécurité d’inégalité.  
  
```
bool operator!=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté gauche de la ! =, opérateur.  
  
 `rhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté droit de la ! =, opérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si les descripteurs de sécurité ne sont pas égaux, sinon **false**.  
  
##  <a name="operator_lt"></a>CSid::operator&lt;  
 Compare la valeur relative de deux objets de descripteurs de sécurité.  
  
```
bool operator<(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté gauche de la ! =, opérateur.  
  
 `rhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté droit de la ! =, opérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si `lhs` est inférieure à `rhs`, sinon **false**.  
  
##  <a name="operator_lt__eq"></a>CSid::operator&lt;=  
 Compare la valeur relative de deux objets de descripteurs de sécurité.  
  
```
bool operator<=(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté gauche de la ! =, opérateur.  
  
 `rhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté droit de la ! =, opérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si `lhs` est inférieure ou égale à `rhs`, sinon **false**.  
  
##  <a name="operator_gt"></a>CSid::operator&gt;  
 Compare la valeur relative de deux objets de descripteurs de sécurité.  
  
```
bool operator>(
    const CSid& lhs,
    const CSid& rhs) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté gauche de la ! =, opérateur.  
  
 `rhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté droit de la ! =, opérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si `lhs` est supérieur à `rhs`, sinon **false**.  
  
##  <a name="operator_gt__eq"></a>CSid::operator&gt;=  
 Compare la valeur relative de deux objets de descripteurs de sécurité.  
  
```
bool operator>=(
    const CSid& lhs,
    const CSid& rhs) throw());
```  
  
### <a name="parameters"></a>Paramètres  
 `lhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté gauche de la ! =, opérateur.  
  
 `rhs`  
 Le `SID` (identificateur de sécurité) ou `CSid` qui apparaît sur le côté droit de la ! =, opérateur.  
  
### <a name="return-value"></a>Valeur de retour  
 **true** si `lhs` est supérieure ou égale à `rhs`, sinon **false**.  
  
##  <a name="operator_const_sid__star"></a>SID const CSid::operator *  
 Les casts un `CSid` objet vers un pointeur vers un `SID` structure de (l’identificateur de sécurité).  
  
```  
operator const SID *() const throw(...);
```  
  
### <a name="remarks"></a>Remarques  
 Retourne l’adresse de le `SID` structure.  
  
##  <a name="sid"></a>CSid::Sid  
 Retourne le `SID` structure (identificateur de sécurité) en tant que chaîne.  
  
```
LPCTSTR Sid() const throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne le `SID` structure sous forme de chaîne dans un format adapté à l’affichage, de stockage ou de transmission. Équivalent à [ConvertSidToStringSid](http://msdn.microsoft.com/library/windows/desktop/aa376399), bien que cette fonction est uniquement disponible sur Windows 2000 ou version ultérieure et donc est émulé pour les systèmes d’exploitation.  
  
##  <a name="sidnameuse"></a>CSid::SidNameUse  
 Retourne une description de l’état de la `CSid` objet.  
  
```
SID_NAME_USE SidNameUse() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur du membre de données qui stocke une valeur qui décrit l’état de la `CSid` objet.  
  
|Valeur|Description|  
|-----------|-----------------|  
|SidTypeUser|Indique un utilisateur `SID` (identificateur de sécurité).|  
|SidTypeGroup|Indique un groupe `SID`.|  
|SidTypeDomain|Indique un domaine `SID`.|  
|SidTypeAlias|Indique un alias `SID`.|  
|SidTypeWellKnownGroup|Indique un `SID` pour un groupe bien connu.|  
|SidTypeDeletedAccount|Indique un `SID` pour un compte supprimé.|  
|SidTypeInvalid|Indique un non valide `SID`.|  
|SidTypeUnknown|Indique un inconnu `SID` type.|  
|SidTypeComputer|Indique un `SID` d’un ordinateur.|  
  
### <a name="remarks"></a>Remarques  
 Appelez [CSid::LoadAccount](#loadaccount) pour mettre à jour la `CSid` objet avant d’appeler `SidNameUse` pour renvoyer son état. `SidNameUse`ne modifie pas l’état de l’objet (en appelant **LookupAccountName** ou **LookupAccountSid**), mais renvoie uniquement l’état actuel.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de la sécurité](../../visual-cpp-samples.md)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Fonctions globales de sécurité](../../atl/reference/security-global-functions.md)   
 [Opérateurs](../../atl/reference/atl-operators.md)

