---
title: "Fonctions globales de signalement d’erreurs et de débogage | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
dev_langs:
- C++
helpviewer_keywords:
- functions [ATL], error reporting
ms.assetid: 11339c02-98cd-428d-b3b9-7deeb155a6a3
caps.latest.revision: 17
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
ms.openlocfilehash: 4a412910d13d10606080c14412d33d2b614fdcec
ms.lasthandoff: 02/24/2017

---
# <a name="debugging-and-error-reporting-global-functions"></a>Fonctions globales de signalement d’erreurs et de débogage
Ces fonctions fournissent des fonctionnalités de trace et de débogage utiles.  
  
|||  
|-|-|  
|[AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66)|Retourne un `GetLastError` code d’erreur sous la forme d’une valeur HRESULT.|  
|[AtlHresultFromWin32](http://msdn.microsoft.com/library/63add2dd-274c-4e72-a98c-040b93413a2f)|Convertit un code d'erreur Win32 en valeur HRESULT.|  
|[AtlReportError](http://msdn.microsoft.com/library/86b046a5-ea18-4ecf-9aab-40fc1eab847c)|Configure **IErrorInfo** pour fournir des détails de l’erreur à un client.|  
|[AtlThrow](http://msdn.microsoft.com/library/2bd111da-8170-488d-914a-c9bf6b6765f7)|Lève un `CAtlException`.|  
|[AtlThrowLastWin32](http://msdn.microsoft.com/library/8bce8e56-c7cd-4ebb-8c62-80ebc63a3d07)|Appelez cette fonction pour signaler une erreur en fonction du résultat de la fonction Windows `GetLastError`.|  
  
##  <a name="a-nameatlhresultfromlasterrora--atlhresultfromlasterror"></a><a name="atlhresultfromlasterror"></a>AtlHresultFromLastError  
 Retourne la dernière valeur du code d'erreur du thread appelant sous la forme d'une valeur HRESULT.  
  
```
HRESULT AtlHresultFromLastError();
```  
  
### <a name="remarks"></a>Notes  
 `AtlHresultFromLastError`appels `GetLastError` pour obtenir la dernière erreur et renvoie l’erreur après l’avoir converti un HRESULT à l’aide de la **HRESULT_FROM_WIN32** (macro).  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlcomcli.h  

##  <a name="a-nameatlhresultfromwin32a--atlhresultfromwin32"></a><a name="atlhresultfromwin32"></a>AtlHresultFromWin32  
 Convertit un code d'erreur Win32 en valeur HRESULT.  
  
```
AtlHresultFromWin32(DWORD error);
```  
  
### <a name="parameters"></a>Paramètres  
 *erreur*  
 La valeur d’erreur à convertir.  
  
### <a name="remarks"></a>Remarques  
 Convertit un code d’erreur Win32 HRESULT, à l’aide de la macro **HRESULT_FROM_WIN32**.  
  
> [!NOTE]
>  Au lieu d’utiliser **HRESULT_FROM_WIN32(GetLastError())**, utilisez la fonction [AtlHresultFromLastError](http://msdn.microsoft.com/library/74530d7d-3c91-484c-acf3-aff755715d66).  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlcomcli.h  

##  <a name="a-nameatlreporterrora--atlreporterror"></a><a name="atlreporterror"></a>AtlReportError  
 Configure le `IErrorInfo` interface pour fournir des informations d’erreur aux clients de l’objet.  
  
```
HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCOLESTR lpszDesc,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    LPCSTR lpszDesc,
    DWORD dwHelpID,
    LPCSTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0);

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());

HRESULT WINAPI AtlReportError(
    const CLSID& clsid,
    UINT nID,
    DWORD dwHelpID,
    LPCOLESTR lpszHelpFile,
    const IID& iid = GUID_NULL,
    HRESULT hRes = 0,
    HINSTANCE hInst = _AtlBaseModule.GetResourceInstance());
```  
  
### <a name="parameters"></a>Paramètres  
 `clsid`  
 [in] Le CLSID de l’objet de l’erreur.  
  
 `lpszDesc`  
 [in] Chaîne décrivant l’erreur. Spécifient les versions Unicode `lpszDesc` est de type **LPCOLESTR**; la version ANSI spécifie un type de `LPCSTR`.  
  
 `iid`  
 [in] L’IID de l’interface qui définit l’erreur ou `GUID_NULL` si l’erreur est définie par le système d’exploitation.  
  
 `hRes`  
 [in] Le `HRESULT` doit être renvoyée à l’appelant.  
  
 `nID`  
 [in] L’identificateur de ressource où se trouve la chaîne de description d’erreur. Cette valeur doit être comprise entre 0 x 0200 et 0xFFFF, inclus. Dans les versions debug, un **ASSERT** entraîne si `nID` n’indexe pas une chaîne valide. Dans les versions release, la chaîne de description d’erreur est définie à « Erreur inconnue ».  
  
 `dwHelpID`  
 [in] L’identificateur de contexte d’aide pour l’erreur.  
  
 `lpszHelpFile`  
 [in] Le chemin d’accès et le nom du fichier d’aide décrivant l’erreur.  
  
 `hInst`  
 [in] Le handle de la ressource. Par défaut, ce paramètre est **__AtlBaseModuleModule::GetResourceInstance**, où **__AtlBaseModuleModule** est l’instance globale de [CAtlBaseModule](../../atl/reference/catlbasemodule-class.md) ou d’une classe dérivée.  
  
### <a name="return-value"></a>Valeur de retour  
 Si le `hRes` paramètre est différent de zéro, retourne la valeur de `hRes`. Si `hRes` est zéro, les quatre premières versions de `AtlReportError` retourner `DISP_E_EXCEPTION`. Les deux dernières versions retournent le résultat de la macro **MAKE_HRESULT (1, FACILITY_ITF,** `nID` **)**.  
  
### <a name="remarks"></a>Remarques  
 La chaîne *lpszDesc* est utilisé en tant que description de l’erreur. Lorsque le client reçoit la `hRes` retour de `AtlReportError`, le client peut accéder à la **IErrorInfo** structure pour plus d’informations sur l’erreur.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_COM&#52;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_1.cpp)]  
  
> [!CAUTION]
>  N’utilisez pas `AtlReportError` dans C++ gestionnaires catch. Certaines substitutions de ces fonctions utilisent les macros de conversion de chaînes ATL en interne, qui à son tour utiliser la `_alloca` fonctionnent en interne. À l’aide de `AtlReportError` dans un bloc catch C++ gestionnaire peut provoquer des exceptions dans les gestionnaires catch de C++.  

### <a name="requirements"></a>Spécifications  
 **En-tête :** atlcom.h  
    
##  <a name="a-nameatlthrowa--atlthrow"></a><a name="atlthrow"></a>AtlThrow  
 Appelez cette fonction pour signaler une erreur en fonction d'un code d'état `HRESULT`.  
  
```
__declspec(noreturn) inline void AtlThrow(HRESULT hr);
```  
  
### <a name="parameters"></a>Paramètres  
 `hr`  
 Valeur HRESULT standard.  
  
### <a name="remarks"></a>Notes  
 Cette fonction est utilisée par le code ATL et MFC en cas d’une condition d’erreur. Il peut également être appelé à partir de votre propre code. L’implémentation par défaut de cette fonction dépend de la définition du symbole **_ATL_NO_EXCEPTIONS** et sur le type de projet, MFC ou ATL.  
  
 Dans tous les cas, cette fonction suit la valeur HRESULT au débogueur.  
  
 Dans Visual Studio 2015 Update 3 et versions ultérieures, cette fonction est attribué __declspec (noreturn) pour éviter les fausses avertissements SAL.  
  
 Si **_ATL_NO_EXCEPTIONS** n’est pas défini dans un projet MFC, cette fonction génère une [CMemoryException](../../mfc/reference/cmemoryexception-class.md) ou [COleException](../../mfc/reference/coleexception-class.md) selon la valeur de HRESULT.  
  
 Si **_ATL_NO_EXCEPTIONS** n’est pas défini dans un projet ATL, la fonction lève une [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Si **_ATL_NO_EXCEPTIONS** est défini, la fonction provoque un échec d’assertion au lieu de lever une exception.  
  
 Pour les projets ATL, il est possible de fournir votre propre implémentation de cette fonction à utiliser en cas d’échec par ATL. Pour ce faire, définissez votre propre fonction avec la même signature que `AtlThrow` et #define `AtlThrow` par le nom de votre fonction. Ceci doit être fait avant d’inclure atlexcept.h (ce qui signifie qu’il doit être exécuté avant d’inclure des en-têtes ATL atlbase.h incluant atlexcept.h). Attribut votre fonction `__declspec(noreturn)` pour éviter les fausses avertissements SAL.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#95;](../../atl/codesnippet/cpp/debugging-and-error-reporting-global-functions_2.h)]  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atldef.h  

##  <a name="a-nameatlthrowlastwin32a--atlthrowlastwin32"></a><a name="atlthrowlastwin32"></a>AtlThrowLastWin32  
 Appelez cette fonction pour signaler une erreur en fonction du résultat de la fonction Windows `GetLastError`.  
  
```
inline void AtlThrowLastWin32();
```  
  
### <a name="remarks"></a>Remarques  
 Cette fonction effectue le suivi du résultat de `GetLastError` au débogueur.  
  
 Si **_ATL_NO_EXCEPTIONS** n’est pas défini dans un projet MFC, cette fonction génère une [CMemoryException](../../mfc/reference/cmemoryexception-class.md) ou [COleException](../../mfc/reference/coleexception-class.md) selon la valeur retournée par `GetLastError`.  
  
 Si **_ATL_NO_EXCEPTIONS** n’est pas défini dans un projet ATL, la fonction lève une [CAtlException](../../atl/reference/catlexception-class.md).  
  
 Si **_ATL_NO_EXCEPTIONS** est défini, la fonction provoque un échec d’assertion au lieu de lever une exception.  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atldef.h  
   
     
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)   
 [Macros de débogage et rapport d’erreurs](../../atl/reference/debugging-and-error-reporting-macros.md)










