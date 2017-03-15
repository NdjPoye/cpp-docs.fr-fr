---
title: Classe de CSecurityDesc | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CSecurityDesc
- ATL.CSecurityDesc
- CSecurityDesc
dev_langs:
- C++
helpviewer_keywords:
- CSecurityDesc class
ms.assetid: 3767a327-378f-4690-ba40-4d9f6a1f5ee4
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
ms.openlocfilehash: 6dbd586ee3ee07d3c567fa0aae46446397dfb62b
ms.lasthandoff: 02/24/2017

---
# <a name="csecuritydesc-class"></a>CSecurityDesc (classe)
Cette classe est un wrapper pour le **SECURITY_DESCRIPTOR** structure.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
class CSecurityDesc
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSecurityDesc::CSecurityDesc](#csecuritydesc)|Constructeur.|  
|[CSecurityDesc :: ~ CSecurityDesc](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSecurityDesc::FromString](#fromstring)|Convertit un descripteur de sécurité au format chaîne en un descripteur de sécurité valide et fonctionnel.|  
|[CSecurityDesc::GetControl](#getcontrol)|Récupère contrôle les informations du descripteur de sécurité.|  
|[CSecurityDesc::GetDacl](#getdacl)|Récupère des informations de liste de contrôle d’accès discrétionnaire du descripteur de sécurité.|  
|[CSecurityDesc::GetGroup](#getgroup)|Récupère les informations de groupe principal du descripteur de sécurité.|  
|[CSecurityDesc::GetOwner](#getowner)|Récupère les informations sur le propriétaire du descripteur de sécurité.|  
|[CSecurityDesc::GetPSECURITY_DESCRIPTOR](#getpsecurity_descriptor)|Retourne un pointeur vers le **SECURITY_DESCRIPTOR** structure.|  
|[CSecurityDesc::GetSacl](#getsacl)|Récupère les informations de liste (SACL) de contrôle d’accès système du descripteur de sécurité.|  
|[CSecurityDesc::IsDaclAutoInherited](#isdaclautoinherited)|Détermine si la liste DACL est configurée pour prendre en charge la propagation automatique.|  
|[CSecurityDesc::IsDaclDefaulted](#isdacldefaulted)|Détermine si le descripteur de sécurité est configuré avec une liste DACL par défaut.|  
|[CSecurityDesc::IsDaclPresent](#isdaclpresent)|Détermine si le descripteur de sécurité contient une liste DACL.|  
|[CSecurityDesc::IsDaclProtected](#isdaclprotected)|Détermine si la liste DACL est configurée pour empêcher toute modification.|  
|[CSecurityDesc::IsGroupDefaulted](#isgroupdefaulted)|Détermine si l’identificateur de sécurité de groupe du descripteur de sécurité (SID) a été défini par défaut.|  
|[CSecurityDesc::IsOwnerDefaulted](#isownerdefaulted)|Détermine si le SID du propriétaire du descripteur de sécurité a été défini par défaut.|  
|[CSecurityDesc::IsSaclAutoInherited](#issaclautoinherited)|Détermine si la liste SACL est configurée pour prendre en charge la propagation automatique.|  
|[CSecurityDesc::IsSaclDefaulted](#issacldefaulted)|Détermine si le descripteur de sécurité est configuré avec une liste SACL par défaut.|  
|[CSecurityDesc::IsSaclPresent](#issaclpresent)|Détermine si le descripteur de sécurité contient une liste SACL.|  
|[CSecurityDesc::IsSaclProtected](#issaclprotected)|Détermine si la liste SACL est configurée pour empêcher les modifications.|  
|[CSecurityDesc::IsSelfRelative](#isselfrelative)|Détermine si le descripteur de sécurité est au format auto-relatif.|  
|[CSecurityDesc::MakeAbsolute](#makeabsolute)|Appelez cette méthode pour convertir le descripteur de sécurité au format absolu.|  
|[CSecurityDesc::MakeSelfRelative](#makeselfrelative)|Appelez cette méthode pour convertir le descripteur de sécurité au format auto-relatif.|  
|[CSecurityDesc::SetControl](#setcontrol)|Définit les bits de contrôle d'un descripteur de sécurité.|  
|[CSecurityDesc::SetDacl](#setdacl)|Définit les informations dans une liste DACL. Si une liste DACL est déjà présente dans le descripteur de sécurité, il est remplacé.|  
|[CSecurityDesc::SetGroup](#setgroup)|Définit les informations de groupe principal d’un descripteur de sécurité format absolu, en remplaçant toutes les informations de groupe principal déjà présentes.|  
|[CSecurityDesc::SetOwner](#setowner)|Définit les informations de propriétaire d’un descripteur de sécurité format absolu, en remplaçant toutes les informations de propriétaire déjà présentes.|  
|[CSecurityDesc::SetSacl](#setsacl)|Définit les informations de la liste SACL. Si une liste SACL est déjà présente dans le descripteur de sécurité, il est remplacé.|  
|[CSecurityDesc::ToString](#tostring)|Convertit un descripteur de sécurité à un format de chaîne.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[SECURITY_DESCRIPTOR const CSecurityDesc::operator *](#operator_const_security_descriptor__star)|Retourne un pointeur vers le **SECURITY_DESCRIPTOR** structure.|  
|[CSecurityDesc::operator =](#operator_eq)|Opérateur d'assignation.|  
  
## <a name="remarks"></a>Notes  
 Le **SECURITY_DESCRIPTOR** structure contient les informations de sécurité associées à un objet. Applications utilisent cette structure pour définir et d’interroger l’état de la sécurité d’un objet. Voir aussi [AtlGetSecurityDescriptor](http://msdn.microsoft.com/library/233578b8-dcc5-4f51-8e62-7cdcc2ff6b11).  
  
 Les applications ne doivent pas modifier le **SECURITY_DESCRIPTOR** structure directement et à la place doit utiliser les méthodes de classe fournies.  
  
 Pour une présentation du modèle de contrôle d’accès dans Windows, consultez la page [le contrôle d’accès](http://msdn.microsoft.com/library/windows/desktop/aa374860) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlsecurity.h  
  
##  <a name="a-namecsecuritydesca--csecuritydesccsecuritydesc"></a><a name="csecuritydesc"></a>CSecurityDesc::CSecurityDesc  
 Constructeur.  
  
```
CSecurityDesc() throw();
CSecurityDesc(const CSecurityDesc& rhs) throw(... );  
CSecurityDesc(const SECURITY_DESCRIPTOR& rhs) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rhs`  
 Le `CSecurityDesc` objet ou **SECURITY_DESCRIPTOR** à affecter à la nouvelle structure `CSecurityDesc` objet.  
  
### <a name="remarks"></a>Remarques  
 Le `CSecurityDesc` objet peut éventuellement être créé à l’aide un **SECURITY_DESCRIPTOR** structure ou défini précédemment `CSecurityDesc` objet.  
  
##  <a name="a-namedtora--csecuritydesccsecuritydesc"></a><a name="dtor"></a>CSecurityDesc :: ~ CSecurityDesc  
 Destructeur.  
  
```
virtual ~CSecurityDesc() throw();
```  
  
### <a name="remarks"></a>Remarques  
 Le destructeur libère toutes les ressources attribuées.  
  
##  <a name="a-namefromstringa--csecuritydescfromstring"></a><a name="fromstring"></a>CSecurityDesc::FromString  
 Convertit un descripteur de sécurité au format chaîne en un descripteur de sécurité valide et fonctionnel.  
  
```
bool FromString(LPCTSTR pstr) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstr`  
 Pointeur vers une chaîne terminée par le caractère null qui contient le [descripteur de sécurité au format chaîne](http://msdn.microsoft.com/library/windows/desktop/aa379570) à convertir.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite. Lève une exception en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 La chaîne peut être créée à l’aide de [CSecurityDesc::ToString](#tostring). Convertir le descripteur de sécurité dans une chaîne facilite stocker et transmettre.  
  
 Cette méthode est uniquement disponible avec Windows 2000 et versions ultérieures, car il appelle [convertstringsecuritydescriptortosecuritydescriptor a](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
##  <a name="a-namegetcontrola--csecuritydescgetcontrol"></a><a name="getcontrol"></a>CSecurityDesc::GetControl  
 Récupère contrôle les informations du descripteur de sécurité.  
  
```
bool GetControl(SECURITY_DESCRIPTOR_CONTROL* psdc) const throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *psdc*  
 Pointeur vers un **SECURITY_DESCRIPTOR_CONTROL** structure qui reçoit les informations de contrôle du descripteur de sécurité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la méthode réussit, false en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est uniquement explicite lorsque vous utilisez Windows 2000 ou version ultérieure, car elle appelle [GetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa446647).  
  
##  <a name="a-namegetdacla--csecuritydescgetdacl"></a><a name="getdacl"></a>CSecurityDesc::GetDacl  
 Récupère des informations de liste de contrôle d’accès discrétionnaire du descripteur de sécurité.  
  
```
bool GetDacl(
    CDacl* pDacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDacl`  
 Pointeur vers un `CDacl` structure dans laquelle stocker une copie de la liste DACL du descripteur de sécurité. Si un discrétionnaire **ACL** existe, la méthode affecte `pDacl` pour l’adresse de la sécurité du descripteur de discrétionnaire **ACL**. Si un discrétionnaire **ACL** n’existe pas, aucune valeur n’est stockée.  
  
 `pbPresent`  
 Pointeur vers une valeur qui indique la présence d’une manière discrétionnaire **ACL** dans le descripteur de sécurité spécifié. Si le descripteur de sécurité contient un discrétionnaire **ACL**, ce paramètre est défini sur true. Si le descripteur de sécurité ne contient-elle pas un discrétionnaire **ACL**, ce paramètre est défini sur false.  
  
 `pbDefaulted`  
 Pointeur vers un indicateur est défini sur la valeur de l’indicateur SE_DACL_DEFAULTED dans le **SECURITY_DESCRIPTOR_CONTROL** structure si discrétionnaire **ACL** existe pour le descripteur de sécurité. Si cet indicateur est true, le discrétionnaire **ACL** a été récupéré par un mécanisme par défaut ; si false le discrétionnaire **ACL** a été spécifié par un utilisateur.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la méthode réussit, false en cas d’échec.  
  
##  <a name="a-namegetgroupa--csecuritydescgetgroup"></a><a name="getgroup"></a>CSecurityDesc::GetGroup  
 Récupère les informations de groupe principal du descripteur de sécurité.  
  
```
bool GetGroup(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSid`  
 Pointeur vers un [CSid](../../atl/reference/csid-class.md) (identificateur de sécurité) qui reçoit une copie du groupe stockée dans le CDacl.  
  
 `pbDefaulted`  
 Pointeur vers un indicateur est défini sur la valeur de l’indicateur SE_GROUP_DEFAULTED dans le **SECURITY_DESCRIPTOR_CONTROL** lorsque la méthode retourne la structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la méthode réussit, false en cas d’échec.  
  
##  <a name="a-namegetownera--csecuritydescgetowner"></a><a name="getowner"></a>CSecurityDesc::GetOwner  
 Récupère les informations sur le propriétaire du descripteur de sécurité.  
  
```
bool GetOwner(
    CSid* pSid,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSid`  
 Pointeur vers un [CSid](../../atl/reference/csid-class.md) (identificateur de sécurité) qui reçoit une copie du groupe stockée dans le CDacl.  
  
 `pbDefaulted`  
 Pointeur vers un indicateur est défini sur la valeur de l’indicateur SE_OWNER_DEFAULTED dans le **SECURITY_DESCRIPTOR_CONTROL** lorsque la méthode retourne la structure.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la méthode réussit, false en cas d’échec.  
  
##  <a name="a-namegetpsecuritydescriptora--csecuritydescgetpsecuritydescriptor"></a><a name="getpsecurity_descriptor"></a>CSecurityDesc::GetPSECURITY_DESCRIPTOR  
 Retourne un pointeur vers le **SECURITY_DESCRIPTOR** structure.  
  
```
const SECURITY_DESCRIPTOR* GetPSECURITY_DESCRIPTOR() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un pointeur vers le [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561) structure.  
  
##  <a name="a-namegetsacla--csecuritydescgetsacl"></a><a name="getsacl"></a>CSecurityDesc::GetSacl  
 Récupère les informations de liste (SACL) de contrôle d’accès système du descripteur de sécurité.  
  
```
bool GetSacl(
    CSacl* pSacl,
    bool* pbPresent = NULL,
    bool* pbDefaulted = NULL) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSacl`  
 Pointeur vers un `CSacl` structure dans laquelle stocker une copie de la liste SACL de descripteur de sécurité. Si un système **ACL** existe, la méthode affecte `pSacl` à l’adresse du système du descripteur de sécurité du **ACL**. Si un système **ACL** n’existe pas, aucune valeur n’est stockée.  
  
 `pbPresent`  
 Pointeur vers un indicateur, la méthode définit pour indiquer la présence d’un système **ACL** dans le descripteur de sécurité spécifié. Si le descripteur de sécurité contient un système **ACL**, ce paramètre est défini sur true. Si le descripteur de sécurité ne contient pas un système **ACL**, ce paramètre est défini sur false.  
  
 `pbDefaulted`  
 Pointeur vers un indicateur est défini sur la valeur de l’indicateur SE_SACL_DEFAULTED dans le **SECURITY_DESCRIPTOR_CONTROL** si un système de structure **ACL** existe pour le descripteur de sécurité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la méthode réussit, false en cas d’échec.  
  
##  <a name="a-nameisdaclautoinheriteda--csecuritydescisdaclautoinherited"></a><a name="isdaclautoinherited"></a>CSecurityDesc::IsDaclAutoInherited  
 Détermine si la liste de contrôle d’accès discrétionnaire (DACL) est configurée pour prendre en charge la propagation automatique.  
  
```
bool IsDaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si le descripteur de sécurité contient une liste DACL qui est configurée pour prendre en charge la propagation automatique des entrées de contrôle d’accès héritable (ACE) aux objets enfants existants. Sinon, retourne False.  
  
### <a name="remarks"></a>Notes  
 Le système définit ce bit lorsqu’il exécute l’algorithme de l’héritage automatique pour l’objet et ses objets enfants existants.  
  
##  <a name="a-nameisdacldefaulteda--csecuritydescisdacldefaulted"></a><a name="isdacldefaulted"></a>CSecurityDesc::IsDaclDefaulted  
 Détermine si le descripteur de sécurité est configuré avec une liste de contrôle d’accès discrétionnaire (DACL) par défaut.  
  
```
bool IsDaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne true si le descripteur de sécurité contient une liste DACL, par défaut.  
  
### <a name="remarks"></a>Remarques  
 Cet indicateur peut affecter comment le système traite la liste DACL, en ce qui concerne l’héritage d’entrée de contrôle d’accès. Par exemple, si le créateur d’un objet ne spécifie pas une liste DACL, l’objet reçoit le DACL par défaut à partir du jeton d’accès de l’auteur. Le système ignore cet indicateur si l’indicateur SE_DACL_PRESENT n’est pas définie.  
  
 Cet indicateur est utilisé pour déterminer comment le DACL sur l’objet final doit être calculée et n’est pas stocké physiquement dans le contrôle du descripteur de sécurité de l’objet sécurisable.  
  
 Pour définir cet indicateur, utilisez la [CSecurityDesc::SetDacl](#setdacl) (méthode).  
  
##  <a name="a-nameisdaclpresenta--csecuritydescisdaclpresent"></a><a name="isdaclpresent"></a>CSecurityDesc::IsDaclPresent  
 Détermine si le descripteur de sécurité contient une liste de contrôle d’accès discrétionnaire (DACL).  
  
```
bool IsDaclPresent() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si le descripteur de sécurité contient une liste DACL.  
  
### <a name="remarks"></a>Remarques  
 Si cet indicateur n’est pas défini, ou si cet indicateur est défini et que le DACL est NULL, le descripteur de sécurité autorise l’accès complet à tout le monde.  
  
 Cet indicateur est utilisé pour stocker les informations de sécurité spécifiées par l’appelant jusqu'à ce que le descripteur de sécurité est associé à un objet sécurisable. Une fois le descripteur de sécurité est associé à un objet sécurisable, l’indicateur SE_DACL_PRESENT est toujours défini dans le contrôle de descripteur de sécurité.  
  
 Pour définir cet indicateur, utilisez la [CSecurityDesc::SetDacl](#setdacl) (méthode).  
  
##  <a name="a-nameisdaclprotecteda--csecuritydescisdaclprotected"></a><a name="isdaclprotected"></a>CSecurityDesc::IsDaclProtected  
 Détermine si la liste de contrôle d’accès discrétionnaire (DACL) est configurée pour empêcher les modifications.  
  
```
bool IsDaclProtected() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la liste DACL est configurée pour empêcher la modification par des entrées de contrôle d’accès héritable (ACE) le descripteur de sécurité. Sinon, retourne False.  
  
### <a name="remarks"></a>Notes  
 Pour définir cet indicateur, utilisez la [CSecurityDesc::SetDacl](#setdacl) (méthode).  
  
 Cette méthode est uniquement explicite pour Windows 2000 ou version ultérieure, que Windows 2000 prend en charge la propagation automatique des ACE pouvant être héritées.  
  
##  <a name="a-nameisgroupdefaulteda--csecuritydescisgroupdefaulted"></a><a name="isgroupdefaulted"></a>CSecurityDesc::IsGroupDefaulted  
 Détermine si l’identificateur de sécurité de groupe du descripteur de sécurité (SID) a été défini par défaut.  
  
```
bool IsGroupDefaulted() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si un mécanisme par défaut, plutôt que le fournisseur d’origine du descripteur de sécurité, fourni le descripteur de sécurité SID de groupe. Sinon, retourne False.  
  
### <a name="remarks"></a>Remarques  
 Pour définir cet indicateur, utilisez la [CSecurityDesc::SetGroup](#setgroup) (méthode).  
  
##  <a name="a-nameisownerdefaulteda--csecuritydescisownerdefaulted"></a><a name="isownerdefaulted"></a>CSecurityDesc::IsOwnerDefaulted  
 Détermine si l’identificateur de sécurité du propriétaire du descripteur de sécurité (SID) a été défini par défaut.  
  
```
bool IsOwnerDefaulted() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne true si un mécanisme par défaut, plutôt que le fournisseur d’origine du descripteur de sécurité, fourni le SID du propriétaire du descripteur de sécurité. Sinon, retourne False.  
  
### <a name="remarks"></a>Remarques  
 Pour définir cet indicateur, utilisez la [CSecurityDesc::SetOwner](#setowner) (méthode).  
  
##  <a name="a-nameissaclautoinheriteda--csecuritydescissaclautoinherited"></a><a name="issaclautoinherited"></a>CSecurityDesc::IsSaclAutoInherited  
 Détermine si la liste de contrôle d’accès système (SACL) est configurée pour prendre en charge la propagation automatique.  
  
```
bool IsSaclAutoInherited() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si le descripteur de sécurité contient une liste SACL qui est configurée pour prendre en charge la propagation automatique des entrées de contrôle d’accès héritable (ACE) aux objets enfants existants. Sinon, retourne False.  
  
### <a name="remarks"></a>Remarques  
 Le système définit ce bit lorsqu’il exécute l’algorithme de l’héritage automatique pour l’objet et ses objets enfants existants.  
  
##  <a name="a-nameissacldefaulteda--csecuritydescissacldefaulted"></a><a name="issacldefaulted"></a>CSecurityDesc::IsSaclDefaulted  
 Détermine si le descripteur de sécurité est configuré avec une liste de contrôle d’accès de système (SACL) par défaut.  
  
```
bool IsSaclDefaulted() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne true si le descripteur de sécurité contient une liste SACL, par défaut.  
  
### <a name="remarks"></a>Notes  
 Cet indicateur peut affecter comment le système traite la liste SACL, en ce qui concerne l’héritage d’entrée de contrôle d’accès. Le système ignore cet indicateur si l’indicateur SE_SACL_PRESENT n’est pas définie.  
  
 Pour définir cet indicateur, utilisez la [CSecurityDesc::SetSacl](#setsacl) (méthode).  
  
##  <a name="a-nameissaclpresenta--csecuritydescissaclpresent"></a><a name="issaclpresent"></a>CSecurityDesc::IsSaclPresent  
 Détermine si le descripteur de sécurité contient une liste de contrôle d’accès système (SACL).  
  
```
bool IsSaclPresent() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si le descripteur de sécurité contient une liste SACL.  
  
### <a name="remarks"></a>Notes  
 Pour définir cet indicateur, utilisez la [CSecurityDesc::SetSacl](#setsacl) (méthode).  
  
##  <a name="a-nameissaclprotecteda--csecuritydescissaclprotected"></a><a name="issaclprotected"></a>CSecurityDesc::IsSaclProtected  
 Détermine si la liste de contrôle d’accès système (SACL) est configurée pour empêcher les modifications.  
  
```
bool IsSaclProtected() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la liste SACL est configurée pour empêcher le descripteur de sécurité d’être modifié par des entrées de contrôle d’accès héritable (ACE). Sinon, retourne False.  
  
### <a name="remarks"></a>Remarques  
 Pour définir cet indicateur, utilisez la [CSecurityDesc::SetSacl](#setsacl) (méthode).  
  
 Cette méthode est uniquement explicite pour Windows 2000 ou version ultérieure, que Windows 2000 prend en charge la propagation automatique des ACE pouvant être héritées.  
  
##  <a name="a-nameisselfrelativea--csecuritydescisselfrelative"></a><a name="isselfrelative"></a>CSecurityDesc::IsSelfRelative  
 Détermine si le descripteur de sécurité est au format auto-relatif.  
  
```
bool IsSelfRelative() const throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si le descripteur de sécurité est au format auto-relatif avec toutes les informations de sécurité dans un bloc contigu de mémoire. Retourne la valeur false si le descripteur de sécurité est au format absolu. Pour plus d’informations, consultez [absolues et des descripteurs de sécurité Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="a-namemakeabsolutea--csecuritydescmakeabsolute"></a><a name="makeabsolute"></a>CSecurityDesc::MakeAbsolute  
 Appelez cette méthode pour convertir le descripteur de sécurité au format absolu.  
  
```
bool MakeAbsolute() throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la méthode réussit, false dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
 Un descripteur de sécurité au format absolu contient des pointeurs vers les informations qu’il contient, plutôt que les informations de lui-même. Un descripteur de sécurité au format auto-relatif contient les informations contenues dans un bloc contigu de mémoire. Dans un descripteur de sécurité auto-relatif un **SECURITY_DESCRIPTOR** structure démarre toujours les informations, mais le descripteur de sécurité d’autres composants peuvent respecter la structure dans n’importe quel ordre. Au lieu d’utiliser des adresses mémoire, les composants du descripteur de sécurité auto-relatif sont identifiés par à partir du début du descripteur de sécurité. Ce format est utile lorsqu’un descripteur de sécurité doit être stocké sur un disque ou transmis au moyen d’un protocole de communication. Pour plus d’informations, consultez [absolues et des descripteurs de sécurité Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="a-namemakeselfrelativea--csecuritydescmakeselfrelative"></a><a name="makeselfrelative"></a>CSecurityDesc::MakeSelfRelative  
 Appelez cette méthode pour convertir le descripteur de sécurité au format auto-relatif.  
  
```
bool MakeSelfRelative() throw(...);
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true si la méthode réussit, false dans le cas contraire.  
  
### <a name="remarks"></a>Remarques  
 Un descripteur de sécurité au format absolu contient des pointeurs vers les informations qu’il contient, au lieu de contenant les informations de lui-même. Un descripteur de sécurité au format auto-relatif contient les informations contenues dans un bloc contigu de mémoire. Dans un descripteur de sécurité auto-relatif un **SECURITY_DESCRIPTOR** structure démarre toujours les informations, mais le descripteur de sécurité d’autres composants peuvent respecter la structure dans n’importe quel ordre. Au lieu d’utiliser des adresses mémoire, les composants du descripteur de sécurité sont identifiées par à partir du début du descripteur de sécurité. Ce format est utile lorsqu’un descripteur de sécurité doit être stocké sur un disque ou transmis au moyen d’un protocole de communication. Pour plus d’informations, consultez [absolues et des descripteurs de sécurité Self-Relative](http://msdn.microsoft.com/library/windows/desktop/aa374807).  
  
##  <a name="a-nameoperatoreqa--csecuritydescoperator-"></a><a name="operator_eq"></a>CSecurityDesc::operator =  
 Opérateur d'assignation.  
  
```
CSecurityDesc& operator= (const SECURITY_DESCRIPTOR& rhs) throw(...);  
CSecurityDesc& operator= (const CSecurityDesc& rhs) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `rhs`  
 Le **SECURITY_DESCRIPTOR** structure ou `CSecurityDesc` objet à attribuer à la `CSecurityDesc` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la mise à jour `CSecurityDesc` objet.  
  
##  <a name="a-nameoperatorconstsecuritydescriptorstara--csecuritydescoperator-const-securitydescriptor-"></a><a name="operator_const_security_descriptor__star"></a>SECURITY_DESCRIPTOR const CSecurityDesc::operator *  
 Convertit une valeur en un pointeur vers le **SECURITY_DESCRIPTOR** structure.  
  
```  
operator const SECURITY_DESCRIPTOR *() const throw();
```  
  
##  <a name="a-namesetcontrola--csecuritydescsetcontrol"></a><a name="setcontrol"></a>CSecurityDesc::SetControl  
 Définit les bits de contrôle d'un descripteur de sécurité.  
  
```
bool SetControl(
    SECURITY_DESCRIPTOR_CONTROL ControlBitsOfInterest, 
    SECURITY_DESCRIPTOR_CONTROL ControlBitsToSet) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `ControlBitsOfInterest`  
 A **SECURITY_DESCRIPTOR_CONTROL** masque qui indique les bits de contrôle à définir. Pour obtenir la liste des indicateurs qui peuvent être définies, consultez [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
 `ControlBitsToSe`t  
 Masque `SECURITY_DESCRIPTOR_CONTROL` qui indique les nouvelles valeurs des bits de contrôle spécifiés par le masque `ControlBitsOfInterest`. Ce paramètre peut être une combinaison des indicateurs répertoriés pour le paramètre `ControlBitsOfInterest`.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode est disponible uniquement sur Windows 2000 et versions ultérieures, puisqu’il invoque [SetSecurityDescriptorControl](http://msdn.microsoft.com/library/windows/desktop/aa379582\(v=vs.85\).aspx).  
  
##  <a name="a-namesetdacla--csecuritydescsetdacl"></a><a name="setdacl"></a>CSecurityDesc::SetDacl  
 Définit les informations dans une liste de contrôle d’accès discrétionnaire (DACL). Si une liste DACL est déjà présente dans le descripteur de sécurité, il est remplacé.  
  
```
inline void SetDacl(  
    bool bPresent = true,
    bool bDefaulted = false) throw(...);

inline void SetDacl(  
    const CDacl& Dacl,
    bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *DACL*  
 Référence à un `CDacl` objet spécifiant la DACL du descripteur de sécurité. Ce paramètre ne doit pas être NULL. Pour définir une liste DACL nulle dans le descripteur de sécurité, la première forme de la méthode doit être utilisée avec `bPresent` défini sur false.  
  
 `bPresent`  
 Spécifie un indicateur qui signale la présence d’une liste DACL dans le descripteur de sécurité. Si ce paramètre est true, la méthode définit l’indicateur SE_DACL_PRESENT dans le **SECURITY_DESCRIPTOR_CONTROL** de la structure et utilise les valeurs dans le *Dacl* et `bDefaulted` paramètres. Si elle est false, la méthode efface l’indicateur SE_DACL_PRESENT, et `bDefaulted` est ignoré.  
  
 `bDefaulted`  
 Spécifie un indicateur indiquant la source de la liste DACL. Si cet indicateur est true, la liste DACL a été récupérée par un mécanisme par défaut. Si la valeur est false, la liste DACL a été explicitement spécifiée par un utilisateur. La méthode stocke cette valeur dans l’indicateur SE_DACL_DEFAULTED de la **SECURITY_DESCRIPTOR_CONTROL** structure. Si ce paramètre n’est pas spécifié, l’indicateur SE_DACL_DEFAULTED est désactivée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Remarques  
 Il existe une différence importante entre vide et une liste DACL qui n’existe pas. Lorsqu’une liste DACL est vide, il ne contient aucune entrée de contrôle d’accès et aucun droit d’accès n’a été explicitement accordée. Par conséquent, l’accès à l’objet est refusé implicitement. Lorsqu’un objet n’a aucune liste DACL, en revanche, aucune protection n’est assignée à l’objet, et toute demande d’accès est accordé.  
  
##  <a name="a-namesetgroupa--csecuritydescsetgroup"></a><a name="setgroup"></a>CSecurityDesc::SetGroup  
 Définit les informations de groupe principal d’un descripteur de sécurité format absolu, en remplaçant toutes les informations de groupe principal déjà présentes.  
  
```
bool SetGroup(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `Sid`  
 Référence à un [CSid](../../atl/reference/csid-class.md) objet de groupe principal nouvelle du descripteur de sécurité. Ce paramètre ne doit pas être NULL. Un descripteur de sécurité peut être marqué comme n’ayant ne pas une liste DACL ou une liste SACL, mais il doit avoir un groupe et un propriétaire, même ces sont le SID NULL (qui est un identificateur de sécurité intégré avec une signification spéciale).  
  
 `bDefaulted`  
 Indique si les informations de groupe principal a été dérivées d’un mécanisme par défaut. Si cette valeur est true, il s’agit des informations par défaut et la méthode stocke cette valeur en tant que l’indicateur SE_GROUP_DEFAULTED dans le **SECURITY_DESCRIPTOR_CONTROL** structure. Si ce paramètre est zéro, l’indicateur SE_GROUP_DEFAULTED est désactivée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="a-namesetownera--csecuritydescsetowner"></a><a name="setowner"></a>CSecurityDesc::SetOwner  
 Définit les informations de propriétaire d’un descripteur de sécurité format absolu. Il remplace toutes les informations de propriétaire déjà présentes.  
  
```
bool SetOwner(const CSid& Sid, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `Sid`  
 Le [CSid](../../atl/reference/csid-class.md) objet pour nouveau propriétaire du principal du descripteur de sécurité. Ce paramètre ne doit pas être NULL.  
  
 `bDefaulted`  
 Indique si les informations de propriétaire sont dérivées d’un mécanisme par défaut. Si cette valeur est true, il est des informations par défaut. La méthode stocke cette valeur en tant que l’indicateur SE_OWNER_DEFAULTED dans le **SECURITY_DESCRIPTOR_CONTROL** structure. Si ce paramètre est zéro, l’indicateur SE_OWNER_DEFAULTED est désactivée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="a-namesetsacla--csecuritydescsetsacl"></a><a name="setsacl"></a>CSecurityDesc::SetSacl  
 Définit les informations dans une liste de contrôle d’accès système (SACL). Si une liste SACL est déjà présente dans le descripteur de sécurité, il est remplacé.  
  
```
bool SetSacl(const CSacl& Sacl, bool bDefaulted = false) throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 *Liste SACL*  
 Pointeur vers un `CSacl` objet spécifiant la liste SACL pour le descripteur de sécurité. Ce paramètre ne doit pas être NULL et doit être un objet CSacl. Contrairement aux DACL, il n’existe aucune différence entre NULL et une liste SACL vide, comme les objets de liste SACL ne spécifient pas de droits d’accès, uniquement les informations d’audit.  
  
 `bDefaulted`  
 Spécifie un indicateur indiquant la source de la liste SACL. Si cet indicateur est true, la liste SACL a été récupérée par un mécanisme par défaut. Si la valeur est false, la liste SACL a été explicitement spécifiée par un utilisateur. La méthode stocke cette valeur dans l’indicateur SE_SACL_DEFAULTED de la **SECURITY_DESCRIPTOR_CONTROL** structure. Si ce paramètre n’est pas spécifié, l’indicateur SE_SACL_DEFAULTED est désactivée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
##  <a name="a-nametostringa--csecuritydesctostring"></a><a name="tostring"></a>CSecurityDesc::ToString  
 Convertit un descripteur de sécurité à un format de chaîne.  
  
```
bool ToString(
    CString* pstr, SECURITY_INFORMATION si = OWNER_SECURITY_INFORMATION |
    GROUP_SECURITY_INFORMATION | DACL_SECURITY_INFORMATION |
    SACL_SECURITY_INFORMATION) const throw(...);
```  
  
### <a name="parameters"></a>Paramètres  
 `pstr`  
 Pointeur vers une chaîne terminée par le caractère null qui recevront le [descripteur de sécurité au format chaîne](http://msdn.microsoft.com/library/windows/desktop/aa379570).  
  
 `si`  
 Spécifie une combinaison d’indicateurs de bits SECURITY_INFORMATION pour indiquer les composants du descripteur de sécurité à inclure dans la chaîne de sortie.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur true en cas de réussite, false en cas d'échec.  
  
### <a name="remarks"></a>Notes  
 Une fois le descripteur de sécurité sous forme de chaîne, il peut plus facilement être stockée ou transmise. Utilisez la `CSecurityDesc::FromString` méthode pour convertir la chaîne en un descripteur de sécurité.  
  
 Le `si` paramètre peut contenir les indicateurs SECURITY_INFORMATION suivants :  
  
|Valeur|Signification|  
|-----------|-------------|  
|OWNER_SECURITY_INFORMATION|Inclure le propriétaire.|  
|GROUP_SECURITY_INFORMATION|Inclut le groupe principal.|  
|DACL_SECURITY_INFORMATION|Inclure la liste DACL.|  
|SACL_SECURITY_INFORMATION|Inclure la liste SACL.|  
  
 Si la liste DACL est NULL et que le bit de contrôle SE_DACL_PRESENT est défini dans le descripteur de sécurité d’entrée, la méthode échoue.  
  
 Si la liste DACL est NULL et que le bit de contrôle SE_DACL_PRESENT n’est pas défini dans le descripteur de sécurité d’entrée, la chaîne de descripteur de sécurité qui en résulte n’a pas un composant D:. Consultez la page [Format de chaîne de descripteur de sécurité](http://msdn.microsoft.com/library/windows/desktop/aa379570) pour plus de détails.  
  
 Cette méthode est uniquement disponible avec Windows 2000 et versions ultérieures, car il appelle [convertstringsecuritydescriptortosecuritydescriptor a](http://msdn.microsoft.com/library/windows/desktop/aa376401).  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple de la sécurité](../../visual-cpp-samples.md)   
 [SECURITY_DESCRIPTOR](http://msdn.microsoft.com/library/windows/desktop/aa379561)   
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Fonctions globales de sécurité](../../atl/reference/security-global-functions.md)

