---
title: Classe de CSettingsStore | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::CSettingsStore
- AFXSETTINGSSTORE/CSettingsStore::Close
- AFXSETTINGSSTORE/CSettingsStore::CreateKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteKey
- AFXSETTINGSSTORE/CSettingsStore::DeleteValue
- AFXSETTINGSSTORE/CSettingsStore::Open
- AFXSETTINGSSTORE/CSettingsStore::Read
- AFXSETTINGSSTORE/CSettingsStore::Write
dev_langs:
- C++
helpviewer_keywords:
- CSettingsStore class
ms.assetid: 0ea181de-a13e-4b29-b560-7c43838223ff
caps.latest.revision: 29
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
ms.sourcegitcommit: 0b07f6b12e178d8e324313ea3b0f6de9ae7420c9
ms.openlocfilehash: 0918c8dd9b6284adecb61bc95ddfd41c22d16cb8
ms.lasthandoff: 02/24/2017

---
# <a name="csettingsstore-class"></a>CSettingsStore Class
Encapsule les fonctions API Windows, fournissant une interface orientée objet que vous utilisez pour accéder au Registre.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CSettingsStore : public CObject  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CSettingsStore::CSettingsStore](#csettingsstore)|Construit un objet `CSettingsStore`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CSettingsStore::Close](#close)|Ferme la clé de Registre ouverte.|  
|[CSettingsStore::CreateKey](#createkey)|Ouvre la clé spécifiée ou la crée si elle n’existe pas.|  
|[CSettingsStore::DeleteKey](#deletekey)|Supprime la clé spécifiée et tous ses enfants.|  
|[CSettingsStore::DeleteValue](#deletevalue)|Supprime la valeur spécifiée de la clé ouverte.|  
|[CSettingsStore::Open](#open)|Ouvre la clé spécifiée.|  
|[CSettingsStore::Read](#read)|Récupère les données pour une valeur de clé spécifiée.|  
|[CSettingsStore::Write](#write)|Écrit une valeur dans le Registre sous la clé ouverte.|  
  
## <a name="remarks"></a>Notes  
 Les fonctions membres `CreateKey` et `Open` sont très similaires. Si la clé de Registre existe déjà, `CreateKey` et `Open` fonctionnent de la même manière. Toutefois, si la clé de Registre n’existe pas, `CreateKey` créera alors que `Open` renvoie une valeur d’erreur.  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser les méthodes d’ouverture et la lecture de la `CSettingsStore` classe. Cet extrait de code fait partie de la [exemple de démonstration de conseil outil](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_ToolTipDemo n °&1;](../../mfc/reference/codesnippet/cpp/csettingsstore-class_1.cpp)]  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 `CSettingsStore`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxsettingsstore.h  
  
##  <a name="close"></a>CSettingsStore::Close  
 Ferme la clé de Registre ouverte.  
  
```  
virtual void Close();
```  
  
### <a name="remarks"></a>Notes  
 Par défaut, cette méthode est appelée à partir du destructeur de la [CSettingsStore classe](../../mfc/reference/csettingsstore-class.md).  
  
##  <a name="createkey"></a>CSettingsStore::CreateKey  
 Ouvre une clé de Registre ou le crée s’il n’existe pas.  
  
```  
virtual BOOL CreateKey(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pszPath`  
 Spécifie le nom d’une clé pour être créé ou ouvert.  
  
### <a name="return-value"></a>Valeur de retour  
 0 si l’opération a réussi ; Sinon, une valeur différente de zéro.  
  
### <a name="remarks"></a>Remarques  
 `CreateKey`utilise `m_hKey` comme racine de recherches de Registre. Il recherche `pszPath` en tant que sous-clé de `m_hKey`. Si la clé n’existe pas, `CreateKey` le crée. Sinon, il ouvre la clé. `CreateKey`définit ensuite `m_hKey` à la clé créée ou ouverte.  
  
##  <a name="csettingsstore"></a>CSettingsStore::CSettingsStore  
 Crée un objet `CSettngsStore`.  
  
```  
CSettingsStore(
    BOOL bAdmin,  
    BOOL bReadOnly);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bAdmin`  
 Paramètre booléen qui indique si le `CSettingsStore` objet agit en mode administrateur.  
  
 [in] `bReadOnly`  
 Paramètre booléen qui indique si le `CSettingsStore` objet est créé dans le mode lecture seule.  
  
### <a name="remarks"></a>Remarques  
 Si `bAdmin` a `false`, le `m_hKey` variable de membre est définie sur `HKEY_LOCAL_MACHINE`. If you set `bAdmin` to `true`, `m_hKey` is set to `HKEY_CURRENT_USER`.  
  
 L’accès de sécurité dépend du `bReadOnly` paramètre. Si `bReadonly` est `false`, l’accès de sécurité est défini sur `KEY_ALL_ACCESS`. Si `bReadyOnly` est `true`, l’accès de sécurité est défini sur une combinaison de `KEY_QUERY_VALUE, KEY_NOTIFY` et `KEY_ENUMERATE_SUB_KEYS`. Pour plus d’informations sur l’accès de sécurité ainsi que le Registre, consultez la page [sécurité de clé de Registre et les droits d’accès](http://msdn.microsoft.com/library/windows/desktop/ms724878).  
  
 Le destructeur de `CSettingsStore` versions `m_hKey` automatiquement.  
  
##  <a name="deletekey"></a>CSettingsStore::DeleteKey  
 Supprime une clé et tous ses enfants à partir du Registre.  
  
```  
virtual BOOL DeleteKey(
    LPCTSTR pszPath,  
    BOOL bAdmin = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pszPath`  
 Le nom de la clé à supprimer.  
  
 [in] `bAdmin`  
 Commutateur qui spécifie l’emplacement de la clé à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode échoue si le `CSettingsStore` objet est en mode lecture seule.  
  
 Si le paramètre `bAdmin` est égal à zéro, `DeleteKey` recherche la clé à supprimer sous `HKEY_CURRENT_USER`. Si `bAdmin` est différent de zéro, `DeleteKey` recherche la clé à supprimer sous `HKEY_LOCAL_MACHINE`.  
  
##  <a name="deletevalue"></a>CSettingsStore::DeleteValue  
 Supprime une valeur à partir de `m_hKey`.  
  
```  
virtual BOOL DeleteValue(LPCTSTR pszValue);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pszValue`  
 Spécifie le champ de valeur à supprimer.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
##  <a name="open"></a>CSettingsStore::Open  
 Ouvre une clé de Registre.  
  
```  
virtual BOOL Open(LPCTSTR pszPath);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pszPath`  
 Le nom d’une clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 Une fois cette méthode ouvre correctement la clé spécifiée, il définit `m_hKey` vers le handle de cette clé.  
  
##  <a name="read"></a>CSettingsStore::Read  
 Lit une valeur dans une clé de Registre.  
  
```  
virtual BOOL Read(
    LPCTSTR pszKey,  
    int& iVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    DWORD& dwVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CString& sVal);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CStringList& scStringList);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CStringArray& scArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CDWordArray& dwcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CWordArray& wcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CByteArray& bcArray);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    LPPOINT& lpPoint);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CRect& rect);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    BYTE** ppData,  
    UINT* pBytes);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObList& list);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObject& obj);

 
virtual BOOL Read(
    LPCTSTR pszKey,  
    CObject*& pObj);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pszKey`  
 Pointeur vers une chaîne terminée par le caractère null qui contient le nom de la valeur à lire dans le Registre.  
  
 [out] `iVal`  
 Référence à une variable de type entier qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `dwVal`  
 Référence à une variable double mot de 32 bits qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `sVal`  
 Référence à une variable de chaîne qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `scStringList`  
 Référence à une variable de liste de chaîne qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `scArray`  
 Référence à une variable de tableau de chaîne qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `dwcArray`  
 Référence à une variable tableau double mot de 32 bits qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `wcArray`  
 Référence à une variable de tableau word de 16 bits qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `bcArray`  
 Référence à une variable de tableau d’octets qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `lpPoint`  
 Référence à un pointeur vers un `POINT` structure qui reçoit la valeur de lire à partir de la clé de Registre.  
  
 [out] `rect`  
 Référence à un [CRect](../../atl-mfc-shared/reference/crect-class.md) variable qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `ppData`  
 Pointeur vers un pointeur vers les données qui reçoit la valeur lus à partir de la clé de Registre.  
  
 [out] `pBytes`  
 Pointeur vers une variable de type entier non signé. Cette variable reçoit la taille de la mémoire tampon qui `ppData` pointe vers.  
  
 [out] `list`  
 Référence à un [CObList](../../mfc/reference/coblist-class.md) variable qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `obj`  
 Référence à un [CObject](../../mfc/reference/cobject-class.md) variable qui reçoit la valeur lue à partir de la clé de Registre.  
  
 [out] `pObj`  
 Référence à un pointeur vers une `CObject` variable qui reçoit la valeur lue à partir de la clé de Registre.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro cas de réussite ; sinon, 0.  
  
### <a name="remarks"></a>Notes  
 `Read`vérifie le `pszKey` en tant que sous-clé de `m_hKey`.  
  
##  <a name="write"></a>CSettingsStore::Write  
 Écrit une valeur dans le Registre sous la clé ouverte.  
  
```  
virtual BOOL Write(
    LPCTSTR pszKey,  
    int iVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    DWORD dwVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPCTSTR pszVal);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CStringList& scStringList);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CByteArray& bcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CStringArray& scArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CDWordArray& dwcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CWordArray& wcArray);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    const CRect& rect);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPPOINT& lpPoint);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    LPBYTE pData,  
    UINT nBytes);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObList& list);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObject& obj);

 
virtual BOOL Write(
    LPCTSTR pszKey,  
    CObject* pObj);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `pszKey`  
 Pointeur vers une chaîne qui contient le nom de la valeur à définir.  
  
 [in] `iVal`  
 Référence à une variable de type entier qui contient les données à stocker.  
  
 [in] `dwVal`  
 Référence à une variable double mot de 32 bits qui contient les données à stocker.  
  
 [in] `pszVal`  
 Pointeur vers une variable de chaîne qui contient les données à stocker.  
  
 [in] `scStringList`  
 Référence à un [CStringList](../../mfc/reference/cstringlist-class.md) variable qui contient les données à stocker.  
  
 [in] `bcArray`  
 Référence à une variable de tableau d’octets qui contient les données à stocker.  
  
 [in] `scArray`  
 Référence à une variable de tableau de chaînes qui contient les données à stocker.  
  
 [in] `dwcArray`  
 Référence à une variable tableau double mot de 32 bits qui contient les données à stocker.  
  
 [in] `wcArray`  
 Référence à une variable de tableau word de 16 bits qui contient les données à stocker.  
  
 [in] `rect`  
 Référence à un [CRect](../../atl-mfc-shared/reference/crect-class.md) variable qui contient les données à stocker.  
  
 [in] `lpPoint`  
 Référence à un pointeur vers une `POINT` variable qui contient les données à stocker.  
  
 [in] `pData`  
 Pointeur vers une mémoire tampon qui contient les données à stocker.  
  
 [in] `nBytes`  
 Spécifie la taille, en octets, des données à laquelle le `pData` paramètre pointe.  
  
 [in] `list`  
 Référence à un [CObList](../../mfc/reference/coblist-class.md) variable qui contient les données à stocker.  
  
 [in] `obj`  
 Référence à un [CObject](../../mfc/reference/cobject-class.md) variable qui contient les données à stocker.  
  
 [in] `pObj`  
 Pointeur vers un pointeur vers une `CObject` variable qui contient les données à stocker.  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE` en cas de réussite ; sinon, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Afin d’écrire dans le Registre, vous devez définir `bReadOnly` une valeur différente de zéro lorsque vous créez un [CSettingsStore](../../mfc/reference/csettingsstore-class.md) objet. Pour plus d’informations, consultez [CSettingsStore::CSettingsStore](#csettingsstore).  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CWinAppEx (classe)](../../mfc/reference/cwinappex-class.md)

