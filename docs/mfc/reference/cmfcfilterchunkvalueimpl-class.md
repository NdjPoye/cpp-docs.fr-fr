---
title: Classe de CMFCFilterChunkValueImpl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCFilterChunkValueImpl
- afxwin/CMFCFilterChunkValueImpl
dev_langs:
- C++
helpviewer_keywords:
- CMFCFilterChunkValueImpl class
ms.assetid: 3c833f23-5b88-4d08-9e09-ca6a8aec88bf
caps.latest.revision: 25
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
ms.openlocfilehash: 8de3cba19a60b8022df96a9edafd13677fa3fecb
ms.lasthandoff: 02/24/2017

---
# <a name="cmfcfilterchunkvalueimpl-class"></a>CMFCFilterChunkValueImpl, classe
Il s’agit d’une classe qui simplifie la logique de paires de valeur à la fois des segments et des propriétés.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCFilterChunkValueImpl : public ATL::IFilterChunkValue;  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl :: ~ CMFCFilterChunkValueImpl](#_dtorcmfcfilterchunkvalueimpl)|Destruction de l’objet.|  
|[CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl](#cmfcfilterchunkvalueimpl)|Construit l’objet.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::Clear](#clear)|Efface le ChunkValue.|  
|[CMFCFilterChunkValueImpl::CopyChunk](#copychunk)|Copie ce segment vers une structure qui décrit les caractéristiques d’un segment.|  
|[CMFCFilterChunkValueImpl::CopyFrom](#copyfrom)|Initialise cette valeur de segment à partir de l’autre valeur.|  
|[CMFCFilterChunkValueImpl::GetChunkGUID](#getchunkguid)|Récupère le GUID du segment.|  
|[CMFCFilterChunkValueImpl::GetChunkPID](#getchunkpid)|Récupère le segment PID (ID de propriété).|  
|[CMFCFilterChunkValueImpl::GetChunkType](#getchunktype)|Obtient segment type.|  
|[CMFCFilterChunkValueImpl::GetString](#getstring)|Récupère la valeur de chaîne.|  
|[CMFCFilterChunkValueImpl::GetValue](#getvalue)|Récupère la valeur en un propvariant alloué.|  
|[CMFCFilterChunkValueImpl::GetValueNoAlloc](#getvaluenoalloc)|Valeur renvoie non allouée (valeur interne).|  
|[CMFCFilterChunkValueImpl::IsValid](#isvalid)|Vérifie si la valeur de cette propriété est valide ou non.|  
|[CMFCFilterChunkValueImpl::SetBoolValue](#setboolvalue)|Surchargé. Définit la propriété par clé à une valeur booléenne.|  
|[CMFCFilterChunkValueImpl::SetDwordValue](#setdwordvalue)|Définit la propriété par clé à une valeur DWORD.|  
|[CMFCFilterChunkValueImpl::SetFileTimeValue](#setfiletimevalue)|Définit la propriété par clé en filetime.|  
|[CMFCFilterChunkValueImpl::SetInt64Value](#setint64value)|Définit la propriété par clé pour un int64.|  
|[CMFCFilterChunkValueImpl::SetIntValue](#setintvalue)|Définit la propriété à une clé à un entier.|  
|[CMFCFilterChunkValueImpl::SetLongValue](#setlongvalue)|Définit la propriété par clé pour une longue durée.|  
|[CMFCFilterChunkValueImpl::SetSystemTimeValue](#setsystemtimevalue)|Définit la propriété par clé un SYSTEMTIME.|  
|[CMFCFilterChunkValueImpl::SetTextValue](#settextvalue)|Définit la propriété par clé en une chaîne Unicode.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCFilterChunkValueImpl::SetChunk](#setchunk)|Une fonction d’assistance qui définit les propriétés communes du segment.|  
  
## <a name="remarks"></a>Notes  
 Pour utiliser, vous créez simplement une classe CMFCFilterChunkValueImpl du type approprié  
  
 Exemple :  
  
 Segment CMFCFilterChunkValueImpl ;  
  
 HR = segment. SetBoolValue(PKEY_IsAttachment, true) ;  
  
 ou  
  
 HR = segment. SetFileTimeValue (PKEY_ItemDate, ftLastModified) ;  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `ATL::IFilterChunkValue`  
  
 [CMFCFilterChunkValueImpl](../../mfc/reference/cmfcfilterchunkvalueimpl-class.md)  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxwin.h  
  
##  <a name="a-namecleara--cmfcfilterchunkvalueimplclear"></a><a name="clear"></a>CMFCFilterChunkValueImpl::Clear  
 Efface le ChunkValue.  
  
```  
void Clear();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecmfcfilterchunkvalueimpla--cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="cmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl::CMFCFilterChunkValueImpl  
 Construit l’objet.  
  
```  
CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namedtorcmfcfilterchunkvalueimpla--cmfcfilterchunkvalueimplcmfcfilterchunkvalueimpl"></a><a name="_dtorcmfcfilterchunkvalueimpl"></a>CMFCFilterChunkValueImpl :: ~ CMFCFilterChunkValueImpl  
 Destruction de l’objet.  
  
```  
virtual ~CMFCFilterChunkValueImpl();
```  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecopychunka--cmfcfilterchunkvalueimplcopychunk"></a><a name="copychunk"></a>CMFCFilterChunkValueImpl::CopyChunk  
 Copie ce segment vers une structure qui décrit les caractéristiques d’un segment.  
  
```  
HRESULT CopyChunk(STAT_CHUNK* pStatChunk);
```  
  
### <a name="parameters"></a>Paramètres  
 `pStatChunk`  
 Un pointeur vers la valeur de destination qui décrivent les caractéristiques du segment.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namecopyfroma--cmfcfilterchunkvalueimplcopyfrom"></a><a name="copyfrom"></a>CMFCFilterChunkValueImpl::CopyFrom  
 Initialise cette valeur de segment à partir de l’autre valeur.  
  
```  
void CopyFrom (IFilterChunkValue* pValue);
```  
  
### <a name="parameters"></a>Paramètres  
 `pValue`  
 Spécifie la valeur de la source d’origine.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetchunkguida--cmfcfilterchunkvalueimplgetchunkguid"></a><a name="getchunkguid"></a>CMFCFilterChunkValueImpl::GetChunkGUID  
 Récupère le GUID du segment.  
  
```  
REFGUID GetChunkGUID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une référence à un GUID qui identifie le segment.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetchunkpida--cmfcfilterchunkvalueimplgetchunkpid"></a><a name="getchunkpid"></a>CMFCFilterChunkValueImpl::GetChunkPID  
 Récupère le segment PID (ID de propriété).  
  
```  
DWORD GetChunkPID() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur DWORD qui contient l’ID de propriété.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetchunktypea--cmfcfilterchunkvalueimplgetchunktype"></a><a name="getchunktype"></a>CMFCFilterChunkValueImpl::GetChunkType  
 Récupère le type de segment.  
  
```  
CHUNKSTATE GetChunkType() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur énumérée de CHUNKSTATE, qui spécifie si le segment actuel est une propriété de type texte ou un type valeur.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetstringa--cmfcfilterchunkvalueimplgetstring"></a><a name="getstring"></a>CMFCFilterChunkValueImpl::GetString  
 Récupère la valeur de chaîne.  
  
```  
CString &GetString();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chaîne contenant la valeur du segment.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetvaluea--cmfcfilterchunkvalueimplgetvalue"></a><a name="getvalue"></a>CMFCFilterChunkValueImpl::GetValue  
 Récupère la valeur en un propvariant alloué.  
  
```  
HRESULT GetValue(PROPVARIANT** ppPropVariant);
```  
  
### <a name="parameters"></a>Paramètres  
 `ppPropVariant`  
 Lorsque la fonction retourne une valeur, ce paramètre contient la valeur du segment.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si PROPVARIANT a été allouée avec succès et que la valeur du segment a été copiée avec succès à `ppPropVariant`; sinon un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetvaluenoalloca--cmfcfilterchunkvalueimplgetvaluenoalloc"></a><a name="getvaluenoalloc"></a>CMFCFilterChunkValueImpl::GetValueNoAlloc  
 Retourne la valeur non allouée (valeur interne).  
  
```  
PROPVARIANT GetValueNoAlloc ();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur actuelle de segment.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameisvalida--cmfcfilterchunkvalueimplisvalid"></a><a name="isvalid"></a>CMFCFilterChunkValueImpl::IsValid  
 Vérifie si la valeur de cette propriété est valide ou non.  
  
```  
BOOL IsValid() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la valeur de segment actuel est valide ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetboolvaluea--cmfcfilterchunkvalueimplsetboolvalue"></a><a name="setboolvalue"></a>CMFCFilterChunkValueImpl::SetBoolValue  
 Surchargé. Définit la propriété par clé à une valeur booléenne.  
  
```  
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,  
    BOOL bVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);

 
HRESULT SetBoolValue(
    REFPROPERTYKEY pkey,  
    VARIANT_BOOL bVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `bVal`  
 Spécifie la valeur du segment à définir.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetchunka--cmfcfilterchunkvalueimplsetchunk"></a><a name="setchunk"></a>CMFCFilterChunkValueImpl::SetChunk  
 Une fonction d’assistance qui définit les propriétés communes du segment.  
  
```  
HRESULT SetChunk(
    REFPROPERTYKEY pkey,  
    CHUNKSTATE chunkType=CHUNK_VALUE,  
    LCID locale=0,  
    DWORD cwcLenSource=0,  
    DWORD cwcStartSource=0,  
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; code d’erreur dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetdwordvaluea--cmfcfilterchunkvalueimplsetdwordvalue"></a><a name="setdwordvalue"></a>CMFCFilterChunkValueImpl::SetDwordValue  
 Définissez la propriété par clé à une valeur DWORD.  
  
```  
HRESULT SetDwordValue(
    REFPROPERTYKEY pkey,  
    DWORD dwVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `dwVal`  
 Spécifie la valeur du segment à définir.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetfiletimevaluea--cmfcfilterchunkvalueimplsetfiletimevalue"></a><a name="setfiletimevalue"></a>CMFCFilterChunkValueImpl::SetFileTimeValue  
 Définissez la propriété par clé en filetime.  
  
```  
HRESULT SetFileTimeValue(
    REFPROPERTYKEY pkey,  
    FILETIME dtVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `dtVal`  
 Spécifie la valeur du segment à définir.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetint64valuea--cmfcfilterchunkvalueimplsetint64value"></a><a name="setint64value"></a>CMFCFilterChunkValueImpl::SetInt64Value  
 Définissez la propriété par clé pour un int64.  
  
```  
HRESULT SetInt64Value(
    REFPROPERTYKEY pkey,  
    __int64 nVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `nVal`  
 Spécifie la valeur du segment à définir.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetintvaluea--cmfcfilterchunkvalueimplsetintvalue"></a><a name="setintvalue"></a>CMFCFilterChunkValueImpl::SetIntValue  
 Définir la propriété à une clé à un entier.  
  
```  
HRESULT SetIntValue(
    REFPROPERTYKEY pkey,  
    int nVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `nVal`  
 Spécifie la valeur du segment à définir.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetlongvaluea--cmfcfilterchunkvalueimplsetlongvalue"></a><a name="setlongvalue"></a>CMFCFilterChunkValueImpl::SetLongValue  
 Définissez la propriété par clé pour une longue durée.  
  
```  
HRESULT SetLongValue(
    REFPROPERTYKEY pkey,  
    long lVal,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `lVal`  
 Spécifie la valeur du segment à définir.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetsystemtimevaluea--cmfcfilterchunkvalueimplsetsystemtimevalue"></a><a name="setsystemtimevalue"></a>CMFCFilterChunkValueImpl::SetSystemTimeValue  
 Définit la propriété par clé un SYSTEMTIME.  
  
```  
HRESULT SetSystemTimeValue(
    REFPROPERTYKEY pkey,  
    const SYSTEMTIME& systemTime,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale=0,  
    DWORD cwcLenSource=0,  
    DWORD cwcStartSource=0,  
    CHUNK_BREAKTYPE chunkBreakType=CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `systemTime`  
 Spécifie la valeur du segment à définir.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesettextvaluea--cmfcfilterchunkvalueimplsettextvalue"></a><a name="settextvalue"></a>CMFCFilterChunkValueImpl::SetTextValue  
 Définit la propriété par clé en une chaîne Unicode.  
  
```  
HRESULT SetTextValue(
    REFPROPERTYKEY pkey,  
    LPCTSTR pszValue,  
    CHUNKSTATE chunkType = CHUNK_VALUE,  
    LCID locale = 0,  
    DWORD cwcLenSource = 0,  
    DWORD cwcStartSource = 0,  
    CHUNK_BREAKTYPE chunkBreakType = CHUNK_NO_BREAK);
```  
  
### <a name="parameters"></a>Paramètres  
 `pkey`  
 Spécifie une clé de propriété.  
  
 `pszValue`  
 Spécifie la valeur du segment à définir.  
  
 `chunkType`  
 Indicateurs indiquent si ce segment contient un type de texte ou une propriété de type valeur. Les valeurs qui proviennent de l’énumération CHUNKSTATE.  
  
 `locale`  
 La langue et sous-langue associé à un bloc de texte. Paramètres régionaux de segment sont utilisé par les indexeurs de document pour effectuer la césure correcte du texte. Si le segment est un type valeur avec le type de données VT_BSTR, VT_LPSTR ou VT_LPWSTR ni type texte, ce champ est ignoré.  
  
 `cwcLenSource`  
 La longueur en caractères du texte source à partir duquel le segment actuel a été dérivé. Une valeur zéro signifie que la correspondance entre le texte source et le texte dérivé caractère par caractère. Une valeur différente de zéro signifie qu’aucune cette correspondance directe n’existe.  
  
 `cwcStartSource`  
 Le décalage à partir de laquelle le texte de la source pour un segment dérivé commence dans le segment de code source.  
  
 `chunkBreakType`  
 Le type de saut qui sépare le segment précédent le segment actuel. Valeurs proviennent de l’énumération CHUNK_BREAKTYPE.  
  
### <a name="return-value"></a>Valeur de retour  
 S_OK si l’opération a réussi ; Sinon, un code d’erreur.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)

