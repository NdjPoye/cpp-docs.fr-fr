---
title: Classe de CPropExchange | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropExchange
- AFXCTL/CPropExchange
- AFXCTL/CPropExchange::ExchangeBlobProp
- AFXCTL/CPropExchange::ExchangeFontProp
- AFXCTL/CPropExchange::ExchangePersistentProp
- AFXCTL/CPropExchange::ExchangeProp
- AFXCTL/CPropExchange::ExchangeVersion
- AFXCTL/CPropExchange::GetVersion
- AFXCTL/CPropExchange::IsAsynchronous
- AFXCTL/CPropExchange::IsLoading
dev_langs:
- C++
helpviewer_keywords:
- CPropExchange class
- OLE controls, persistence
- controls [MFC], OLE
ms.assetid: ed872180-e770-4942-892a-92139d501fab
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
ms.sourcegitcommit: 040985df34f2613b4e4fae29498721aef15d50cb
ms.openlocfilehash: 655d8e2f074c3bd12b1b52ece74efb844c7a9904
ms.lasthandoff: 02/24/2017

---
# <a name="cpropexchange-class"></a>CPropExchange (classe)
Prend en charge l'implémentation de la persistance de vos contrôles OLE.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class AFX_NOVTABLE CPropExchange  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPropExchange::ExchangeBlobProp](#exchangeblobprop)|Échange d’une propriété d’objet binaire volumineux (BLOB).|  
|[CPropExchange::ExchangeFontProp](#exchangefontprop)|Échange d’une propriété de police.|  
|[CPropExchange::ExchangePersistentProp](#exchangepersistentprop)|Échange d’une propriété entre un contrôle et un fichier.|  
|[CPropExchange::ExchangeProp](#exchangeprop)|Échange les propriétés de tout type intégré.|  
|[CPropExchange::ExchangeVersion](#exchangeversion)|Échange le numéro de version d’un contrôle OLE.|  
|[CPropExchange::GetVersion](#getversion)|Récupère le numéro de version d’un contrôle OLE.|  
|[CPropExchange::IsAsynchronous](#isasynchronous)|Détermine si les échanges de propriété sont effectués de façon asynchrone.|  
|[CPropExchange::IsLoading](#isloading)|Indique si les propriétés soient chargées dans le contrôle ou enregistré à partir de celui-ci.|  
  
## <a name="remarks"></a>Remarques  
 `CPropExchange`n’a pas d’une classe de base.  
  
 Établit le contexte et la direction d’un échange de propriété.  
  
 La persistance est l’échange d’informations d’état du contrôle, généralement représentées par ses propriétés, entre le contrôle lui-même et un support.  
  
 Le framework construit un objet dérivé `CPropExchange` lorsqu’il est averti que les propriétés d’un contrôle OLE doivent être chargés à partir d’ou stockage stockée vers persistant.  
  
 L’infrastructure passe un pointeur vers ce `CPropExchange` objet de votre contrôle `DoPropExchange` (fonction). Si vous avez utilisé un Assistant pour créer les fichiers de démarrage pour votre contrôle, votre contrôle `DoPropExchange` les appels de fonction `COleControl::DoPropExchange`. La version de classe de base échange des propriétés stock du contrôle ; vous modifiez la version de votre classe dérivée pour les propriétés de Microsoft exchange que vous avez ajouté à votre contrôle.  
  
 `CPropExchange`peut être utilisé pour sérialiser les propriétés d’un contrôle ou initialiser les propriétés d’un contrôle lors de la charge ou la création d’un contrôle. Le `ExchangeProp` et `ExchangeFontProp` les fonctions membres de `CPropExchange` sont en mesure de stocker les propriétés et les charger à partir de supports différents.  
  
 Pour plus d’informations sur l’utilisation de `CPropExchange`, consultez l’article [contrôles ActiveX MFC : Pages de propriétés](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CPropExchange`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxctl.h  
  
##  <a name="exchangeblobprop"></a>CPropExchange::ExchangeBlobProp  
 Sérialise une propriété qui stocke les données d’objet binaire volumineux (BLOB).  
  
```  
virtual BOOL ExchangeBlobProp(
    LPCTSTR pszPropName,  
    HGLOBAL* phBlob,  
    HGLOBAL hBlobDefault = NULL) = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pszPropName`  
 Le nom de la propriété qui est échangé.  
  
 `phBlob`  
 Pointeur vers une variable qui pointe vers le stockage de la propriété (la variable est généralement un membre de votre classe).  
  
 `hBlobDefault`  
 Valeur par défaut de la propriété.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’échange a réussi ; 0 en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 La valeur de propriété est lu ou écrite vers, selon le cas, la variable référencée par `phBlob`. Si `hBlobDefault` est spécifié, il sera utilisé comme valeur par défaut de la propriété. Cette valeur est utilisée si, pour une raison quelconque, la sérialisation du contrôle échoue.  
  
 Les fonctions **CArchivePropExchange::ExchangeBlobProp**, **CResetPropExchange::ExchangeBlobProp**, et **CPropsetPropExchange::ExchangeBlobProp** remplacent cette fonction virtuelle pure.  
  
##  <a name="exchangefontprop"></a>CPropExchange::ExchangeFontProp  
 Échange d’une propriété de police entre un support de stockage et le contrôle.  
  
```  
virtual BOOL ExchangeFontProp(
    LPCTSTR pszPropName,  
    CFontHolder& font,  
    const FONTDESC* pFontDesc,  
    LPFONTDISP pFontDispAmbient) = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pszPropName`  
 Le nom de la propriété qui est échangé.  
  
 `font`  
 Une référence à un [CFontHolder](../../mfc/reference/cfontholder-class.md) objet qui contient la propriété de police.  
  
 `pFontDesc`  
 Un pointeur vers un [FONTDESC](http://msdn.microsoft.com/library/windows/desktop/ms692782) structure contenant les valeurs pour l’initialisation de l’état par défaut de la propriété de police lorsque `pFontDispAmbient` est **NULL**.  
  
 `pFontDispAmbient`  
 Un pointeur vers le **IFontDisp** interface d’une police à utiliser pour l’initialisation de l’état par défaut de la propriété de police.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’échange a réussi ; 0 en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Si la propriété de police est chargée à partir du support pour le contrôle, les caractéristiques de la police sont récupérés à partir du support et la `CFontHolder` objet référencé par `font` est initialisé avec eux. Si la propriété font est stockée, les caractéristiques de l’objet de police sont écrites sur le support.  
  
 Les fonctions **CArchivePropExchange::ExchangeFontProp**, **CResetPropExchange::ExchangeFontProp**, et **CPropsetPropExchange::ExchangeFontProp** remplacent cette fonction virtuelle pure.  
  
##  <a name="exchangepersistentprop"></a>CPropExchange::ExchangePersistentProp  
 Échange d’une propriété entre le contrôle et un fichier.  
  
```  
virtual BOOL ExchangePersistentProp(
    LPCTSTR pszPropName,  
    LPUNKNOWN* ppUnk,  
    REFIID iid,  
    LPUNKNOWN pUnkDefault) = 0;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pszPropName`  
 Le nom de la propriété qui est échangé.  
  
 `ppUnk`  
 Un pointeur vers une variable qui contient un pointeur vers la propriété **IUnknown** interface (cette variable est généralement un membre de votre classe).  
  
 `iid`  
 ID de l’interface sur la propriété qui utilise le contrôle.  
  
 `pUnkDefault`  
 Valeur par défaut de la propriété.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’échange a réussi ; 0 en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Si la propriété est chargée à partir du fichier pour le contrôle, la propriété est créée et initialisée à partir du fichier. Si la propriété est stockée, sa valeur est écrite dans le fichier.  
  
 Les fonctions **CArchivePropExchange::ExchangePersistentProp**, **CResetPropExchange::ExchangePersistentProp**, et **CPropsetPropExchange::ExchangePersistentProp** remplacent cette fonction virtuelle pure.  
  
##  <a name="exchangeprop"></a>CPropExchange::ExchangeProp  
 Échange d’une propriété entre un support de stockage et le contrôle.  
  
```  
virtual BOOL ExchangeProp(
    LPCTSTR pszPropName,  
    VARTYPE vtProp,  
    void* pvProp,  
    const void* pvDefault = NULL) = 0 ;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pszPropName`  
 Le nom de la propriété qui est échangé.  
  
 `vtProp`  
 Un symbole qui spécifie le type de la propriété qui est échangé. Les valeurs possibles sont :  
  
|Symbole|Type de propriété|  
|------------|-------------------|  
|`VT_I2`|**short**|  
|`VT_I4`|**long**|  
|`VT_BOOL`|**BOOL**|  
|`VT_BSTR`|`CString`|  
|`VT_CY`|**CY**|  
|`VT_R4`|**float**|  
|`VT_R8`|**double**|  
  
 `pvProp`  
 Pointeur vers la valeur de propriété.  
  
 *pvDefault*  
 Pointeur vers une valeur par défaut pour la propriété.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’échange a réussi ; 0 en cas d’échec.  
  
### <a name="remarks"></a>Remarques  
 Si la propriété est chargée à partir du support pour le contrôle, la valeur de propriété est récupérée à partir du support et stockée dans l’objet désigné par `pvProp`. Si la propriété est stockée sur le support, la valeur de l’objet pointé par `pvProp` sont écrites sur le support.  
  
 Les fonctions **CArchivePropExchange::ExchangeProp**, **CResetPropExchange::ExchangeProp**, et **CPropsetPropExchange::ExchangeProp** remplacent cette fonction virtuelle pure.  
  
##  <a name="exchangeversion"></a>CPropExchange::ExchangeVersion  
 Appelé par l’infrastructure pour gérer la persistance d’un numéro de version.  
  
```  
virtual BOOL ExchangeVersion(
    DWORD& dwVersionLoaded,  
    DWORD dwVersionDefault,  
    BOOL bConvert);
```  
  
### <a name="parameters"></a>Paramètres  
 *dwVersionLoaded*  
 Référence à une variable où sera stocké le numéro de version des données persistantes en cours de chargement.  
  
 `dwVersionDefault`  
 Le numéro de version actuel du contrôle.  
  
 `bConvert`  
 Indique s’il faut convertir les données persistantes dans la version actuelle ou de conserver la même version que celle qui a été chargée.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la fonction a réussi ; 0 dans le cas contraire.  
  
##  <a name="getversion"></a>CPropExchange::GetVersion  
 Appelez cette fonction pour récupérer le numéro de version du contrôle.  
  
```  
DWORD GetVersion();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le numéro de version du contrôle.  
  
##  <a name="isasynchronous"></a>CPropExchange::IsAsynchronous  
 Détermine si les échanges de propriété sont effectués de façon asynchrone.  
  
```  
BOOL IsAsynchronous();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne TRUE si les propriétés sont échangés de façon asynchrone, sinon FALSE.  
  
##  <a name="isloading"></a>CPropExchange::IsLoading  
 Appelez cette fonction pour déterminer si les propriétés soient chargées dans le contrôle ou enregistré à partir de celui-ci.  
  
```  
BOOL IsLoading();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si les propriétés sont chargées ; sinon 0.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [COleControl::DoPropExchange](../../mfc/reference/colecontrol-class.md#dopropexchange)




