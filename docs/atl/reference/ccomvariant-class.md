---
title: Classe de CComVariant | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CComVariant
- ATLCOMCLI/ATL::CComVariant
- ATLCOMCLI/ATL::CComVariant::CComVariant
- ATLCOMCLI/ATL::CComVariant::Attach
- ATLCOMCLI/ATL::CComVariant::ChangeType
- ATLCOMCLI/ATL::CComVariant::Clear
- ATLCOMCLI/ATL::CComVariant::Copy
- ATLCOMCLI/ATL::CComVariant::CopyTo
- ATLCOMCLI/ATL::CComVariant::Detach
- ATLCOMCLI/ATL::CComVariant::GetSize
- ATLCOMCLI/ATL::CComVariant::ReadFromStream
- ATLCOMCLI/ATL::CComVariant::SetByRef
- ATLCOMCLI/ATL::CComVariant::WriteToStream
dev_langs:
- C++
helpviewer_keywords:
- VARIANT macro
- CComVariant class
- VARIANT macro, ATL
ms.assetid: 4d31149c-d005-44b5-a509-10f84afa2b61
caps.latest.revision: 26
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
ms.openlocfilehash: 4b01ca9da3d216603ea7efad228735edd1becbd3
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="ccomvariant-class"></a>CComVariant (classe)
Cette classe encapsule la `VARIANT` type, en fournissant un membre qui indique le type de données stockées.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
cpp
class CComVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CComVariant::CComVariant](#ccomvariant)|Constructeur.|  
|[CComVariant :: ~ CComVariant](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CComVariant::Attach](#attach)|Attache un **variante** à le `CComVariant` objet.|  
|[CComVariant::ChangeType](#changetype)|Convertit le `CComVariant` objet vers un nouveau type.|  
|[CComVariant::Clear](#clear)|Efface le `CComVariant` objet.|  
|[CComVariant::Copy](#copy)|Copie un **variante** à le `CComVariant` objet.|  
|[CComVariant::CopyTo](#copyto)|Copie le contenu de la `CComVariant` objet.|  
|[CComVariant::Detach](#detach)|Détache sous-jacent **variante** à partir de la `CComVariant` objet.|  
|[CComVariant::GetSize](#getsize)|Retourne la taille en octets du contenu de la `CComVariant` objet.|  
|[CComVariant::ReadFromStream](#readfromstream)|Charge un **variante** à partir d’un flux de données.|  
|[CComVariant::SetByRef](#setbyref)|Initialise le `CComVariant` objet et définit les **vt** membre **VT_BYREF**.|  
|[CComVariant::WriteToStream](#writetostream)|Enregistre l’objet sous-jacent **variante** dans un flux.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|||  
|-|-|  
|[CComVariant::operator](#operator_lt)|Indique si le `CComVariant` objet est inférieur à spécifié **variante**.|  
|[CComVariant::operator >](#operator_gt)|Indique si le `CComVariant` objet est supérieur à spécifié **variante**.|  
|[opérateur ! =](#operator_neq)|Indique si le `CComVariant` objet n’est pas égale spécifié **variante**.|  
|[opérateur =](#operator_eq)|Assigne une valeur à la `CComVariant` objet.|  
|[opérateur ==](#operator_eq_eq)|Indique si le `CComVariant` objet est égal à spécifié **variante**.|  
  
## <a name="remarks"></a>Remarques  
 `CComVariant`encapsule la `VARIANT and VARIANTARG` type, qui se compose d’une union et d’un membre qui indique le type des données stockées dans l’union. **VARIANT**s sont généralement utilisés dans Automation.  
  
 `CComVariant`dérive de la **VARIANT** type afin d’être utilisé partout où une **variante** peut être utilisé. Vous pouvez, par exemple, utiliser le **V_VT** macro pour extraire le type d’un `CComVariant` ou vous pouvez accéder à la **vt** membre directement, comme vous pouvez le faire avec un **variante**.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `tagVARIANT`  
  
 `CComVariant`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlcomcli.h  
  
##  <a name="attach"></a>CComVariant::Attach  
 Efface en toute sécurité le contenu actuel de la `CComVariant` objet, copie le contenu de `pSrc` dans cet objet, puis définit le type variant de `pSrc` à `VT_EMPTY`.  
  
```
HRESULT Attach(VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSrc`  
 [in] Pointe vers le [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) à joindre à l’objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Propriétaire des données détenues par `pSrc` est transféré vers le `CComVariant` objet.  
  
##  <a name="ccomvariant"></a>CComVariant::CComVariant  
 Chaque constructeur traite l’initialisation sans échec de la `CComVariant` objet en appelant le `VariantInit` fonction Win32 ou en définissant la valeur de l’objet et le type en fonction des paramètres passés.  
  
```
CComVariant() throw();
CComVariant(const CComVariant& varSrc);
CComVariant(const VARIANT& varSrc);
CComVariant(LPCOLESTR lpszSrc);
CComVariant(LPCSTR lpszSrc);
CComVariant(bool bSrc);
CComVariant(BYTE nSrc) throw();
CComVariant(int nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned int  nSrc, VARTYPE vtSrc = VT_UI4) throw();
CComVariant(shor  nSrc) throw();
CComVariant(unsigned short nSrc) throw();
CComVariant(long  nSrc, VARTYPE vtSrc = VT_I4) throw();
CComVariant(unsigned long  nSrc) throw();
CComVariant(LONGLONG  nSrc) throw();
CComVariant(ULONGLONG  nSrc) throw();
CComVariant(float  fltSrc) throw();
CComVariant(double  dblSrc, VARTYPE vtSrc = VT_R8) throw();
CComVariant(CY  cySrc) throw();
CComVariant(IDispatch* pSrc) throw();
CComVariant(IUnknown* pSrc) throw();
CComVariant(const SAFEARRAY* pSrc);
CComVariant(char  cSrc) throw();
CComVariant(const CComBSTR& bstrSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 *varSrc*  
 [in] Le `CComVariant` ou `VARIANT` utilisée pour initialiser le `CComVariant` objet. Le contenu de la variante source est copié vers la destination sans conversion.  
  
 `lpszSrc`  
 [in] La chaîne de caractères utilisée pour initialiser le `CComVariant` objet. Vous pouvez passer une zéro caractère large (Unicode) chaîne de caractères à la **LPCOLESTR** version du constructeur ou d’une chaîne ANSI pour le `LPCSTR` version. Dans les deux cas, la chaîne est convertie en Unicode `BSTR` allouée à l’aide de **SysAllocString**. Le type de la `CComVariant` objet sera `VT_BSTR`.  
  
 `bSrc`  
 [in] Le `bool` utilisée pour initialiser le `CComVariant` objet. Le `bool` argument est converti en un **VARIANT_BOOL** avant d’être stocké. Le type de la `CComVariant` objet sera `VT_BOOL`.  
  
 `nSrc`  
 [in] Le `int`, **octets**, **court**, **long**, **LONGLONG**, **ULONGLONG**, **court non signé**, `unsigned long`, ou `unsigned int` utilisée pour initialiser le `CComVariant` objet. The type of the `CComVariant` object will be `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**, **VT_UI4**, or **VT_UI4**, respectively.  
  
 `vtSrc`  
 [in] Le type de la variante. Lorsque le premier paramètre est `int`, les types valides sont `VT_I4` et **VT_INT**. Lorsque le premier paramètre est **long**, les types valides sont `VT_I4` et `VT_ERROR`. Lorsque le premier paramètre est **double**, les types valides sont `VT_R8` et `VT_DATE`. Lorsque le premier paramètre est `unsigned int`, les types valides sont **VT_UI4** et **VT_UINT**.  
  
 `fltSrc`  
 [in] Le **float** utilisée pour initialiser le `CComVariant` objet. Le type de la `CComVariant` objet sera `VT_R4`.  
  
 `dblSrc`  
 [in] Le **double** utilisée pour initialiser le `CComVariant` objet. Le type de la `CComVariant` objet sera `VT_R8`.  
  
 `cySrc`  
 [in] Le **CY** utilisée pour initialiser le `CComVariant` objet. Le type de la `CComVariant` objet sera `VT_CY`.  
  
 `pSrc`  
 [in] Le `IDispatch` ou **IUnknown** pointeur utilisé pour initialiser le `CComVariant` objet. `AddRef`seront appelées sur le pointeur d’interface. Le type de la `CComVariant` objet sera **VT_DISPATCH** ou **VT_UNKNOWN**, respectivement.  
  
 Ou, le **SAFERRAY** pointeur utilisé pour initialiser le `CComVariant` objet. Une copie de la **SAFEARRAY** est stocké dans le `CComVariant` objet. Le type de la `CComVariant` objet sera une combinaison du type d’origine de la **SAFEARRAY** et **VT_ARRAY**.  
  
 `cSrc`  
 [in] Le `char` utilisée pour initialiser le `CComVariant` objet. Le type de la `CComVariant` objet sera **VT_I1**.  
  
 `bstrSrc`  
 [in] Le BSTR est utilisé pour initialiser le `CComVariant` objet. Le type de la `CComVariant` objet sera `VT_BSTR`.  
  
### <a name="remarks"></a>Remarques  
 Le destructeur gère le nettoyage en appelant [CComVariant::Clear](#clear).  
  
##  <a name="dtor"></a>CComVariant :: ~ CComVariant  
 Destructeur.  
  
```
~CComVariant() throw();
```  
  
### <a name="remarks"></a>Notes  
 Cette méthode gère le nettoyage en appelant [CComVariant::Clear](#clear).  
  
##  <a name="changetype"></a>CComVariant::ChangeType  
 Convertit le `CComVariant` objet vers un nouveau type.  
  
```
HRESULT ChangeType(VARTYPE vtNew, const VARIANT* pSrc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `vtNew`  
 [in] Le nouveau type de la `CComVariant` objet.  
  
 `pSrc`  
 [in] Un pointeur vers le `VARIANT` dont la valeur sera convertie dans le nouveau type. La valeur par défaut est **NULL**, ce qui signifie que le `CComVariant` objet sera converti en place.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Si vous passez une valeur `pSrc`, `ChangeType` utilisera ce **variante** comme source pour la conversion. Dans le cas contraire, le `CComVariant` objet sera la source.  
  
##  <a name="clear"></a>CComVariant::Clear  
 Efface les `CComVariant` objet en appelant le `VariantClear` fonction Win32.  
  
```
HRESULT Clear();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Le destructeur appelle automatiquement **désactivez**.  
  
##  <a name="copy"></a>CComVariant::Copy  
 Libère le `CComVariant` objet et lui attribue une copie de l’objet **variante**.  
  
```
HRESULT Copy(const VARIANT* pSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `pSrc`  
 [in] Un pointeur vers le [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) à copier.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
##  <a name="copyto"></a>CComVariant::CopyTo  
 Copie le contenu de la `CComVariant` objet.  
  
```
HRESULT CopyTo(BSTR* pstrDest);
```  
  
### <a name="parameters"></a>Paramètres  
 *pstrDest*  
 Pointe vers une `BSTR` qui recevront une copie du contenu de la `CComVariant` objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Le **CComVariant** objet doit être de type `VT_BSTR`.  
  
##  <a name="detach"></a>CComVariant::Detach  
 Détache sous-jacent **variante** à partir de la `CComVariant` de l’objet et définit le type d’objet `VT_EMPTY`.  
  
```
HRESULT Detach(VARIANT* pDest);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDest`  
 [out] Retourne l’objet sous-jacent `VARIANT` valeur de l’objet.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Remarques  
 Notez que le contenu de la `VARIANT` référencé par `pDest` sera automatiquement effacé avant d’être assigné à la valeur et le type de l’appel **CComVariant** objet.  
  
##  <a name="getsize"></a>CComVariant::GetSize  
 Pour une taille fixe simple `VARIANT`, cette méthode retourne le `sizeof` le type de données sous-jacent et `sizeof(VARTYPE)`.  
  
```
ULONG GetSize() const;
```  
  
### <a name="return-value"></a>Valeur de retour  
 La taille en octets du contenu actuel de la `CComVariant` objet.  
  
### <a name="remarks"></a>Remarques  
 Si le `VARIANT` contient un pointeur d’interface `GetSize` recherche `IPersistStream` ou `IPersistStreamInit`. Si réussie, la valeur de retour est les 32 bits de poids faible de la valeur retournée par `GetSizeMax` ainsi que les `sizeof` un `CLSID` et `sizeof(VARTYPE)`. Si le pointeur d’interface est `NULL`, `GetSize` retourne le `sizeof` un `CLSID` plus `sizeof(VARTYPE)`. Si la taille totale est supérieure à `ULONG_MAX`, `GetSize` retourne `sizeof(VARTYPE)` qui indique une erreur.  
  
 Dans tous les autres cas, un fichier temporaire `VARIANT` de type `VT_BSTR` est convertie à partir du `VARIANT`. La longueur de cette `BSTR` est calculée comme la taille de la longueur de la chaîne plus la longueur de la chaîne et la taille du caractère null plu `sizeof(VARTYPE)`. Si le `VARIANT` ne peut pas être converti en un `VARIANT` de type `VT_BSTR`, `GetSize` renvoie `sizeof(VARTYPE)`.  
  
 La taille retournée par cette méthode correspond au nombre d’octets utilisés par [CComVariant::WriteToStream](#writetostream) dans des conditions de réussite.  
  
##  <a name="operator_eq"></a>CComVariant::operator =  
 Affecte une valeur et le type correspondant à la `CComVariant` objet.  
  
```
CComVariant& operator=(const CComVariant& varSrc);
CComVariant& operator=(const VARIANT& varSrc);
CComVariant& operator=(const CComBSTR& bstrSrc);
CComVariant& operator=(LPCOLESTR lpszSrc);
CComVariant& operator=(LPCSTR lpszSrc);
CComVariant& operator=(bool bSrc);
CComVariant& operator=(BYTE nSrc) throw();
CComVariant& operator=int nSrc) throw();
CComVariant& operator=(unsigned int nSrc) throw();
CComVariant& operator=(short nSrc) throw();
CComVariant& operator=(unsigned short nSrc) throw();
CComVariant& operator=(long nSrc) throw();
CComVariant& operator=(unsigned long nSrc) throw();
CComVariant& operator=(LONGLONG nSrc) throw();
CComVariant& operator=(ULONGLONG nSrc) throw();
CComVariant& operator=(float fltSrc) throw();
CComVariant& operator=(double dblSrc) throw();
CComVariant& operator=(CY cySrc) throw();
CComVariant& operator=(IDispatch* pSrc) throw();
CComVariant& operator=(IUnknown* pSrc) throw();
CComVariant& operator=(const SAFEARRAY* pSrc);
CComVariant& operator=(char cSrc) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 *varSrc*  
 [in] Le `CComVariant` ou [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) à affecter à la `CComVariant` objet. Le contenu de la variante source est copié vers la destination sans conversion.  
  
 `bstrSrc`  
 [in] Le BSTR à assigner à la `CComVariant` objet. Le type de la `CComVariant` objet sera `VT_BSTR`.  
  
 `lpszSrc`  
 [in] La chaîne de caractères à affecter à la `CComVariant` objet. Vous pouvez passer une zéro caractère large (Unicode) chaîne de caractères à la **LPCOLESTR** version de l’opérateur ou une chaîne ANSI pour le `LPCSTR` version. Dans les deux cas, la chaîne est convertie en Unicode `BSTR` allouée à l’aide de **SysAllocString**. Le type de la `CComVariant` objet sera `VT_BSTR`.  
  
 `bSrc`  
 [in] Le `bool` à affecter à la `CComVariant` objet. Le `bool` argument est converti en un **VARIANT_BOOL** avant d’être stocké. Le type de la `CComVariant` objet sera `VT_BOOL`.  
  
 `nSrc`  
 [in] The `int`, **BYTE**, **short**, **long**, **LONGLONG**, **ULONGLONG**, **unsigned short**, `unsigned long`, or `unsigned int` to be assigned to the `CComVariant` object. The type of the `CComVariant` object will be `VT_I4`, `VT_UI1`, `VT_I2`, `VT_I4`, **VT_I8**, **VT_UI8**, **VT_UI2**, **VT_UI4**, or **VT_UI4**, respectively.  
  
 `fltSrc`  
 [in] Le **float** à affecter à la `CComVariant` objet. Le type de la `CComVariant` objet sera `VT_R4`.  
  
 `dblSrc`  
 [in] Le **double** à affecter à la `CComVariant` objet. Le type de la `CComVariant` objet sera `VT_R8`.  
  
 `cySrc`  
 [in] Le **CY** à affecter à la `CComVariant` objet. Le type de la `CComVariant` objet sera `VT_CY`.  
  
 `pSrc`  
 [in] Le `IDispatch` ou **IUnknown** pointeur à assigner à la `CComVariant` objet. `AddRef`seront appelées sur le pointeur d’interface. Le type de la `CComVariant` objet sera **VT_DISPATCH** ou **VT_UNKNOWN**, respectivement.  
  
 Une **SAFEARRAY** pointeur à assigner à la `CComVariant` objet. Une copie de la **SAFEARRAY** est stocké dans le `CComVariant` objet. Le type de la `CComVariant` objet sera une combinaison du type d’origine de la **SAFEARRAY** et **VT_ARRAY**.  
  
 `cSrc`  
 [in] Le caractère à assigner à la `CComVariant` objet. Le type de la `CComVariant` objet sera **VT_I1**.  
  
##  <a name="operator_eq_eq"></a>CComVariant::operator ==  
 Indique si le `CComVariant` objet est égal à spécifié **variante**.  
  
```
bool operator==(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Retourne **true** si la valeur et le type de *varSrc* sont égaux à la valeur et le type, respectivement, de la `CComVariant` objet. Dans le cas contraire, **false**. L’opérateur utilise les paramètres régionaux par défaut de l’utilisateur pour effectuer la comparaison.  
  
 L’opérateur compare uniquement la valeur des types variants. Il compare des chaînes, entiers et flottantes, mais pas les tableaux ou les enregistrements.  
  
##  <a name="operator_neq"></a>CComVariant::operator ! =  
 Indique si le `CComVariant` objet n’est pas égale spécifié **variante**.  
  
```
bool operator!=(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Notes  
 Retourne **true** si la valeur ou le type de *varSrc* n’est pas égale à la valeur ou tapez, respectivement, de la `CComVariant` objet. Dans le cas contraire, **false**. L’opérateur utilise les paramètres régionaux par défaut de l’utilisateur pour effectuer la comparaison.  
  
 L’opérateur compare uniquement la valeur des types variants. Il compare des chaînes, entiers et flottantes, mais pas les tableaux ou les enregistrements.  
  
##  <a name="operator_lt"></a>CComVariant::operator&lt;  
 Indique si le `CComVariant` objet est inférieur à spécifié **variante**.  
  
```
bool operator<(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Retourne **true** si la valeur de la `CComVariant` objet est inférieur à la valeur de *varSrc*. Dans le cas contraire, **false**. L’opérateur utilise les paramètres régionaux par défaut de l’utilisateur pour effectuer la comparaison.  
  
##  <a name="operator_gt"></a>CComVariant::operator&gt;  
 Indique si le `CComVariant` objet est supérieur à spécifié **variante**.  
  
```
bool operator>(const VARIANT& varSrc) const throw();
```  
  
### <a name="remarks"></a>Remarques  
 Retourne **true** si la valeur de la `CComVariant` objet est supérieur à la valeur de *varSrc*. Dans le cas contraire, **false**. L’opérateur utilise les paramètres régionaux par défaut de l’utilisateur pour effectuer la comparaison.  
  
##  <a name="readfromstream"></a>CComVariant::ReadFromStream  
 Définit sous-jacent **variante** à la **variante** contenues dans le flux spécifié.  
  
```
HRESULT ReadFromStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStream`  
 [in] Un pointeur vers le [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) interface sur le flux de données contenant les données.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
### <a name="remarks"></a>Notes  
 **ReadToStream** nécessite un appel précédent à [WriteToStream](#writetostream).  
  
##  <a name="setbyref"></a>CComVariant::SetByRef  
 Initialise le `CComVariant` objet et définit les **vt** membre **VT_BYREF**.  
  
```
template < typename T >
void SetByRef(T* pT) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `T`  
 Le type de **variante**, par exemple, `BSTR`, `int`, ou `char`.  
  
 *pT*  
 Le pointeur utilisé pour initialiser le `CComVariant` objet.  
  
### <a name="remarks"></a>Remarques  
 `SetByRef`est un modèle de fonction qui initialise le `CComVariant` objet avec le pointeur *pT* et définit les **vt** membre **VT_BYREF**. Exemple :  
  
 [!code-cpp[NVC_ATL_Utilities&#76;](../../atl/codesnippet/cpp/ccomvariant-class_1.cpp)]  
  
##  <a name="writetostream"></a>CComVariant::WriteToStream  
 Enregistre l’objet sous-jacent **variante** dans un flux.  
  
```
HRESULT WriteToStream(IStream* pStream);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStream`  
 [in] Un pointeur vers le [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) interface sur un flux de données.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur `HRESULT` standard.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)
