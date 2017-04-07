---
title: COleVariant (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COleVariant
- AFXDISP/COleVariant
- AFXDISP/COleVariant::COleVariant
- AFXDISP/COleVariant::Attach
- AFXDISP/COleVariant::ChangeType
- AFXDISP/COleVariant::Clear
- AFXDISP/COleVariant::Detach
- AFXDISP/COleVariant::GetByteArrayFromVariantArray
- AFXDISP/COleVariant::SetString
dev_langs:
- C++
helpviewer_keywords:
- Automation, parameter types
- COleVariant class
- VARIANT data type
ms.assetid: e1b5cd4a-b066-4b9b-b48b-6215ed52d998
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
ms.openlocfilehash: 753566adc5fc8e48ad31da52c2bb3f04c9e21727
ms.lasthandoff: 02/24/2017

---
# <a name="colevariant-class"></a>COleVariant (classe)
Encapsule la [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) type de données.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class COleVariant : public tagVARIANT  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleVariant::COleVariant](#colevariant)|Construit un objet `COleVariant`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COleVariant::Attach](#attach)|Attache un **variante** à un `COleVariant`.|  
|[COleVariant::ChangeType](#changetype)|Change le type variant de ce `COleVariant` objet.|  
|[COleVariant::Clear](#clear)|Cela efface `COleVariant` objet.|  
|[COleVariant::Detach](#detach)|Détache un **VARIANT** d’un `COleVariant` et retourne le **VARIANT**.|  
|[COleVariant::GetByteArrayFromVariantArray](#getbytearrayfromvariantarray)|Récupère un tableau d’octets d’un tableau de variant existant.|  
|[COleVariant::SetString](#setstring)|Définit la chaîne à un type particulier, généralement ANSI.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COleVariant::operator LPCVARIANT](#operator_lpcvariant)|Convertit un `COleVariant` valeur dans un `LPCVARIANT`.|  
|[COleVariant::operator LPVARIANT](#operator_lpvariant)|Convertit un `COleVariant` de l’objet dans un `LPVARIANT`.|  
|[COleVariant::operator =](#operator_eq)|Copie un `COleVariant` valeur.|  
|[COleVariant::operator ==](#operator_eq_eq)|Compare deux `COleVariant` valeurs.|  
|[COleVariant::operator &lt; &lt;,&gt;&gt;](#operator_lt_lt__gt_gt)|Sorties un `COleVariant` valeur `CArchive` ou `CDumpContext` et les entrées une `COleVariant` à partir de l’objet `CArchive`.|  
  
## <a name="remarks"></a>Remarques  
 Ce type de données est utilisé dans OLE automation. Plus précisément, le [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b) structure contient un pointeur vers un tableau de **variante** structures. A **DISPPARAMS** structure est utilisée pour passer des paramètres [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d).  
  
> [!NOTE]
>  Cette classe est dérivée de la **variante** structure. Cela signifie que vous pouvez passer un `COleVariant` dans un paramètre qui appelle un **VARIANT** et que les membres de données de la **VARIANT** structure sont les membres de données accessibles de `COleVariant`.  
  
 Les deux classes MFC liées à [COleCurrency](../../mfc/reference/colecurrency-class.md) et [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) encapsulent les types de données variant **devise** ( `VT_CY`) et **DATE** ( `VT_DATE`). Le `COleVariant` classe est largement utilisée dans les classes DAO, consultez ces classes pour l’utilisation classique de cette classe, par exemple [CDaoQueryDef](../../mfc/reference/cdaoquerydef-class.md) et [CDaoRecordset](../../mfc/reference/cdaorecordset-class.md).  
  
 Pour plus d’informations, consultez la [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [devise](http://msdn.microsoft.com/en-us/5e81273c-7289-45c7-93c0-32c1553f708e), [DISPPARAMS](http://msdn.microsoft.com/en-us/a16e5a21-766e-4287-b039-13429aa78f8b), et [IDispatch::Invoke](http://msdn.microsoft.com/en-us/964ade8e-9d8a-4d32-bd47-aa678912a54d) entrées dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Pour plus d’informations sur la `COleVariant` classe et son utilisation dans OLE automation, consultez « En passant les paramètres dans OLE Automation » dans l’article [Automation](../../mfc/automation.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `tagVARIANT`  
  
 `COleVariant`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdisp.h  
  
##  <a name="attach"></a>COleVariant::Attach  
 Appelez cette fonction pour attacher la donnée [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) objet actuel `COleVariant` objet.  
  
```  
void Attach(VARIANT& varSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 *varSrc*  
 Existant **variante** objet à attacher à l’actuel `COleVariant` objet.  
  
### <a name="remarks"></a>Notes  
 Cette fonction affecte la [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) de *varSrc* à `VT_EMPTY`.  
  
 Pour plus d’informations, consultez la [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) et [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) entrées dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="colevariant"></a>COleVariant::COleVariant  
 Construit un objet `COleVariant`.  
  
```  
COleVariant(); 
COleVariant(const VARIANT& varSrc); 
COleVariant(const COleVariant& varSrc); 
COleVariant(LPCVARIANT pSrc); 
COleVariant(LPCTSTR lpszSrc); 
COleVariant(LPCTSTR lpszSrc, VARTYPE vtSrc); 
COleVariant(CString& strSrc); 
COleVariant(BYTE nSrc); 
COleVariant(short nSrc, VARTYPE vtSrc = VT_I2); 
COleVariant(long lSrc,VARTYPE vtSrc = VT_I4); 
COleVariant(const COleCurrency& curSrc); 
COleVariant(float fltSrc); 
COleVariant(double dblSrc); 
COleVariant(const COleDateTime& timeSrc); 
COleVariant(const CByteArray& arrSrc); 
COleVariant(const CLongBinary& lbSrc); 
COleVariant(LPCITEMIDLIST pidl);
```  
  
### <a name="parameters"></a>Paramètres  
 *varSrc*  
 Existant `COleVariant` ou **variante** doit être copié dans le nouvel objet `COleVariant` objet.  
  
 `pSrc`  
 Un pointeur vers un **variante** qui est copié dans le nouvel objet `COleVariant` objet.  
  
 `lpszSrc`  
 Une chaîne terminée par null à copier dans le nouveau `COleVariant` objet.  
  
 `vtSrc`  
 Le `VARTYPE` pour le nouveau `COleVariant` objet.  
  
 `strSrc`  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) doit être copié dans le nouvel objet `COleVariant` objet.  
  
 `nSrc`, `lSrc`  
 Valeur numérique à copier dans le nouvel objet `COleVariant`.  
  
 `vtSrc`  
 Le `VARTYPE` pour le nouveau `COleVariant` objet.  
  
 `curSrc`  
 A [COleCurrency](../../mfc/reference/colecurrency-class.md) doit être copié dans le nouvel objet `COleVariant` objet.  
  
 `fltSrc`, `dblSrc`  
 Valeur numérique à copier dans le nouvel objet `COleVariant`.  
  
 `timeSrc`  
 A [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) doit être copié dans le nouvel objet `COleVariant` objet.  
  
 `arrSrc`  
 A [CByteArray](../../mfc/reference/cbytearray-class.md) doit être copié dans le nouvel objet `COleVariant` objet.  
  
 `lbSrc`  
 A [CLongBinary](../../mfc/reference/clongbinary-class.md) doit être copié dans le nouvel objet `COleVariant` objet.  
  
 `pidl`  
 Un pointeur vers un [ITEMIDLIST](http://msdn.microsoft.com/library/windows/desktop/bb773321) à copier dans la nouvelle structure `COleVariant` objet.  
  
### <a name="remarks"></a>Notes  
 Créent de tous ces constructeurs `COleVariant` objets initialisés à la valeur spécifiée. Une brève description de chacun de ces constructeurs ci-dessous.  
  
- **() COleVariant** crée vide `COleVariant` objet, `VT_EMPTY`.  
  
- **COleVariant (** *varSrc* **)** copie existant **variante** ou `COleVariant` objet. Le type variant est conservé.  
  
- **COleVariant (** `pSrc` **)** copie existant **variante** ou `COleVariant` objet. Le type variant est conservé.  
  
- **COleVariant (** `lpszSrc` **)** copie d’une chaîne dans le nouvel objet, `VT_BSTR` (UNICODE).  
  
- **COleVariant (** `lpszSrc` **,** `vtSrc` **)** copie d’une chaîne dans le nouvel objet. Le paramètre `vtSrc` doit être `VT_BSTR` (UNICODE) ou `VT_BSTRT` (ANSI).  
  
- **COleVariant (** `strSrc` **)** copie d’une chaîne dans le nouvel objet, **VT_BSTR** (UNICODE).  
  
- **COleVariant (** `nSrc` **)** copie un entier 8 bits dans le nouvel objet, `VT_UI1`.  
  
- **COleVariant (** `nSrc` **,** `vtSrc` **)** copie un entier 16 bits (ou une valeur booléenne) dans le nouvel objet. Le paramètre `vtSrc` doit être `VT_I2` ou `VT_BOOL`.  
  
- **COleVariant (** `lSrc` **,** `vtSrc` **)** copie un entier 32 bits (ou `SCODE` valeur) dans le nouvel objet. Le paramètre `vtSrc` doit être `VT_I4`, `VT_ERROR`, ou `VT_BOOL`.  
  
- **COleVariant (** `curSrc` **)** Copies un **COleCurrency** valeur dans le nouvel objet `VT_CY`.  
  
- **COleVariant (** `fltSrc` **)** copie la valeur à virgule flottante 32 bits dans le nouvel objet `VT_R4`.  
  
- **COleVariant (** `dblSrc` **)** copie la valeur à virgule flottante 64 bits dans le nouvel objet `VT_R8`.  
  
- **COleVariant (** `timeSrc` **)** Copies un `COleDateTime` valeur dans le nouvel objet `VT_DATE`.  
  
- **COleVariant (** `arrSrc` **)** Copies un `CByteArray` objet dans le nouvel objet `VT_EMPTY`.  
  
- **COleVariant (** `lbSrc` **)** Copies un `CLongBinary` objet dans le nouvel objet `VT_EMPTY`.  
  
 Pour plus d’informations sur `SCODE`, consultez [Structure des Codes d’erreur COM](http://msdn.microsoft.com/library/windows/desktop/ms690088) dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="changetype"></a>COleVariant::ChangeType  
 Convertit le type de valeur de type variant dans ce `COleVariant` objet.  
  
```  
void ChangeType(VARTYPE vartype, LPVARIANT pSrc = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `vartype`  
 Le [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) pour ce `COleVariant` objet.  
  
 `pSrc`  
 Un pointeur vers le [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) objet à convertir. Si cette valeur est **NULL**, ce `COleVariant` objet est utilisé comme source pour la conversion.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez la [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), et [VariantChangeType](http://msdn.microsoft.com/en-us/48a51e32-95d7-4eeb-8106-f5043ffa2fd1) entrées dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="clear"></a>COleVariant::Clear  
 Efface les **variante**.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarques  
 Cela définit le **VARTYPE** pour cet objet pour `VT_EMPTY`. Le `COleVariant` destructeur appelle cette fonction.  
  
 Pour plus d’informations, consultez la `VARIANT`, `VARTYPE`, et `VariantClear` entrées dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="detach"></a>COleVariant::Detach  
 Détache sous-jacent [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) objet à partir de ce `COleVariant` objet.  
  
```  
VARIANT Detach();
```  
  
### <a name="remarks"></a>Remarques  
 Cette fonction affecte la [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) pour ce `COleVariant` objet `VT_EMPTY`.  
  
> [!NOTE]
>  Après avoir appelé **détachement**, il est responsable de l’appelant d’appeler **VariantClear** sur le **variante** structure.  
  
 Pour plus d’informations, consultez la [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118), [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4), et [VariantClear](http://msdn.microsoft.com/en-us/28741d81-8404-4f85-95d3-5c209ec13835) entrées dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="getbytearrayfromvariantarray"></a>COleVariant::GetByteArrayFromVariantArray  
 Récupère un tableau d’octets d’un tableau de variant existant  
  
```  
void GetByteArrayFromVariantArray(CByteArray& bytes);
```  
  
### <a name="parameters"></a>Paramètres  
 `bytes`  
 Une référence à un fichier [CByteArray](../../mfc/reference/cbytearray-class.md) objet.  
  
##  <a name="operator_lpcvariant"></a>COleVariant::operator LPCVARIANT  
 Cet opérateur de conversion retourne un `VARIANT` structure dont la valeur est copiée à partir de ce `COleVariant` objet.  
  
```  
operator LPCVARIANT() const; 
```  
  
### <a name="remarks"></a>Notes  
  
##  <a name="operator_lpvariant"></a>COleVariant::operator LPVARIANT  
 Appeler cet opérateur de conversion pour accéder à l’objet sous-jacent `VARIANT` structure pour ce `COleVariant` objet.  
  
```  
operator LPVARIANT();
```   
  
### <a name="remarks"></a>Remarques  
  
> [!CAUTION]
>  Modification de la valeur dans la **variante** structure accédé par le pointeur retourné par cette fonction modifie la valeur de cette `COleVariant` objet.  
  
##  <a name="operator_eq"></a>COleVariant::operator =  
 Ces opérateurs d’assignation surchargés copier la valeur source dans ce `COleVariant` objet.  
  
```  
const COleVariant& operator=(const VARIANT& varSrc); 
const COleVariant& operator=(LPCVARIANT pSrc); 
const COleVariant& operator=(const COleVariant& varSrc); 
const COleVariant& operator=(const LPCTSTR lpszSrc);
const COleVariant& operator=(const CString& strSrc); 
const COleVariant& operator=(BYTE nSrc); 
const COleVariant& operator=(short nSrc); 
const COleVariant& operator=(long lSrc); 
const COleVariant& operator=(const COleCurrency& curSrc); 
const COleVariant& operator=(float fltSrc); 
const COleVariant& operator=(double dblSrc); 
const COleVariant& operator=(const COleDateTime& dateSrc); 
const COleVariant& operator=(const CByteArray& arrSrc); 
const COleVariant& operator=(const CLongBinary& lbSrc);
```  
  
### <a name="remarks"></a>Remarques  
 Une brève description de chaque opérateur ci-dessous :  
  
- **opérateur = (** *varSrc***)** copie existant **variante** ou `COleVariant` objet dans cet objet.  
  
- **opérateur = (** `pSrc` **)** Copies le **variante** objet accédé par `pSrc` dans cet objet.  
  
- **opérateur = (** `lpszSrc` **)** copie d’une chaîne terminée par null dans cet objet et définit les **VARTYPE** à `VT_BSTR`.  
  
- **opérateur = (** `strSrc` **)** Copies un [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet dans cet objet, puis définit les **VARTYPE** à `VT_BSTR`.  
  
- **opérateur = (** `nSrc` **)** copie une valeur entière de 8 ou 16 bits dans cet objet. Si `nSrc` est une valeur de 8 bits, le **VARTYPE** de cela est défini sur `VT_UI1`. Si `nSrc` est une valeur de 16 bits et le **VARTYPE** cette est `VT_BOOL`, il est conservé ; sinon, elle est définie sur `VT_I2`.  
  
- **opérateur = (** `lSrc` **)** copie une valeur d’entier 32 bits vers cet objet. Si le **VARTYPE** cette est `VT_ERROR`, il est conservé ; sinon, elle est définie sur `VT_I4`.  
  
- **opérateur = (** `curSrc` **)** Copies un [COleCurrency](../../mfc/reference/colecurrency-class.md) objet dans cet objet, puis définit les **VARTYPE** à `VT_CY`.  
  
- **opérateur = (** `fltSrc` **)** copie une valeur à virgule flottante 32 bits dans cet objet et définit les **VARTYPE** à `VT_R4`.  
  
- **opérateur = (** `dblSrc` **)** copie la valeur à virgule flottante 64 bits dans cet objet et définit les **VARTYPE** à `VT_R8`.  
  
- **opérateur = (** `dateSrc` **)** Copies un [COleDateTime](../../atl-mfc-shared/reference/coledatetime-class.md) objet dans cet objet, puis définit les **VARTYPE** à `VT_DATE`.  
  
- **opérateur = (** `arrSrc` **)** Copies un [CByteArray](../../mfc/reference/cbytearray-class.md) objet dans ce `COleVariant` objet.  
  
- **opérateur = (** `lbSrc` **)** Copies un [CLongBinary](../../mfc/reference/clongbinary-class.md) objet dans ce `COleVariant` objet.  
  
 Pour plus d’informations, consultez la [variante](http://msdn.microsoft.com/en-us/e305240e-9e11-4006-98cc-26f4932d2118) et [VARTYPE](http://msdn.microsoft.com/en-us/317b911b-1805-402d-a9cb-159546bc88b4) entrées dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="operator_eq_eq"></a>COleVariant::operator ==  
 Cet opérateur compare deux valeurs de type variant et retourne zéro si elles sont égales ; sinon 0.  
  
```  
BOOL operator==(const VARIANT& varSrc) const; 
BOOL operator==(LPCVARIANT pSrc) const;
```  
  
##  <a name="operator_lt_lt__gt_gt"></a>COleVariant::operator &lt; &lt;,&gt;&gt;  
 Sorties un `COleVariant` valeur `CArchive` ou **CdumpContext** et les entrées une `COleVariant` à partir de l’objet `CArchive`.  
  
```  
friend CDumpContext& AFXAPI operator<<(
    CDumpContext& dc,  
    OleVariant varSrc);
 
friend CArchive& AFXAPI operator<<(
    CArchive& ar,  
    COleVariant varSrc);
 
friend CArchive& AFXAPI operator>>(
    CArchive& ar,  
    COleVariant& varSrc);
```  
  
### <a name="remarks"></a>Remarques  
 Le `COleVariant` insertion ( ** < \< **) (opérateur) prend en charge le diagnostic vidage et le stockage dans une archive. L’extraction ( ** >> **) (opérateur) prend en charge le chargement à partir d’une archive.  
  
##  <a name="setstring"></a>COleVariant::SetString  
 Définit la chaîne d’un type particulier.  
  
```  
void SetString(LPCTSTR lpszSrc, VARTYPE vtSrc);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszSrc`  
 Une chaîne terminée par null à copier dans le nouveau `COleVariant` objet.  
  
 *VtSrc*  
 Le **VARTYPE** pour le nouveau `COleVariant` objet.  
  
### <a name="remarks"></a>Remarques  
 Le paramètre `vtSrc` doit être `VT_BSTR` (UNICODE) ou `VT_BSTRT` (ANSI). `SetString`est généralement utilisé pour définir des chaînes au format ANSI, depuis la valeur par défaut pour le [COleVariant::COleVariant](#colevariant) constructeur avec une chaîne ou paramètre de pointeur de chaîne et non **VARTYPE** est au format UNICODE.  
  
 Un jeu d’enregistrements DAO dans une version non-UNICODE attend des chaînes comme ANSI. Par conséquent, pour DAO des fonctions qui utilisent `COleVariant` objets, si vous ne créez pas un jeu d’enregistrements UNICODE, vous devez utiliser le **COleVariant::COleVariant (** `lpszSrc` **,** `vtSrc` **)** forme de constructeur avec `vtSrc` la valeur `VT_BSTRT` (ANSI) ou utilisez `SetString` avec `vtSrc` la valeur `VT_BSTRT` pour rendre les chaînes ANSI. Par exemple, le `CDaoRecordset` fonctions [CDaoRecordset::Seek](../../mfc/reference/cdaorecordset-class.md#seek) et [CDaoRecordset::SetFieldValue](../../mfc/reference/cdaorecordset-class.md#setfieldvalue) utiliser `COleVariant` comme paramètres des objets. Ces objets doivent être ANSI si le jeu d’enregistrements DAO n’est pas UNICODE.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




