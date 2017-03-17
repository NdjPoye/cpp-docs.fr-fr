---
title: Classe CBindStatusCallback | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::CBindStatusCallback
- ATLCTL/ATL::CBindStatusCallback::Download
- ATLCTL/ATL::CBindStatusCallback::GetBindInfo
- ATLCTL/ATL::CBindStatusCallback::GetPriority
- ATLCTL/ATL::CBindStatusCallback::OnDataAvailable
- ATLCTL/ATL::CBindStatusCallback::OnLowResource
- ATLCTL/ATL::CBindStatusCallback::OnObjectAvailable
- ATLCTL/ATL::CBindStatusCallback::OnProgress
- ATLCTL/ATL::CBindStatusCallback::OnStartBinding
- ATLCTL/ATL::CBindStatusCallback::OnStopBinding
- ATLCTL/ATL::CBindStatusCallback::StartAsyncDownload
- ATLCTL/ATL::CBindStatusCallback::m_dwAvailableToRead
- ATLCTL/ATL::CBindStatusCallback::m_dwTotalRead
- ATLCTL/ATL::CBindStatusCallback::m_pFunc
- ATLCTL/ATL::CBindStatusCallback::m_pT
- ATLCTL/ATL::CBindStatusCallback::m_spBindCtx
- ATLCTL/ATL::CBindStatusCallback::m_spBinding
- ATLCTL/ATL::CBindStatusCallback::m_spMoniker
- ATLCTL/ATL::CBindStatusCallback::m_spStream
dev_langs:
- C++
helpviewer_keywords:
- asynchronous data transfer [C++]
- data transfer [C++]
- data transfer [C++], asynchronous
- CBindStatusCallback class
ms.assetid: 0f5da276-6031-4418-b2a9-a4750ef29e77
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
ms.sourcegitcommit: 604a4bf49490ad2599c857eb3afd527d67e1e25b
ms.openlocfilehash: 50a0a27528f402cda5906658cd2c9cf57a5908e8
ms.lasthandoff: 02/24/2017

---
# <a name="cbindstatuscallback-class"></a>Classe CBindStatusCallback
Cette classe implémente l'interface `IBindStatusCallback`.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class T,
    int nBindFlags = BINDF_ASYNCHRONOUS |   BINDF_ASYNCSTORAGE | BINDF_GETNEWESTVERSION | BINDF_NOWRITECACHE>  
class ATL_NO_VTABLE CBindStatusCallback : public CComObjectRootEx
 <T ::_ThreadModel::ThreadModelNoCS>,
    public IBindStatusCallbackImpl<T>
```  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Votre classe contenant la fonction est appelée lorsque les données sont reçues.  
  
 *nBindFlags*  
 Spécifie les indicateurs de liaison qui sont retournés par [GetBindInfo](#getbindinfo). L’implémentation par défaut définit la liaison doit être asynchrone, récupère la dernière version de l’objet de données / et ne stocke pas les données récupérées dans le cache disque.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CBindStatusCallback::CBindStatusCallback](#cbindstatuscallback)|Constructeur.|  
|[CBindStatusCallback :: ~ CBindStatusCallback](#dtor)|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CBindStatusCallback::Download](#download)|Méthode statique qui démarre le processus de téléchargement, crée un `CBindStatusCallback` objet et appelle `StartAsyncDownload`.|  
|[CBindStatusCallback::GetBindInfo](#getbindinfo)|Appelé par les monikers asynchrones pour demander des informations sur le type de liaison à créer.|  
|[CBindStatusCallback::GetPriority](#getpriority)|Appelée par le moniker asynchrone pour obtenir la priorité de l’opération de liaison. Retourne l’implémentation ATL `E_NOTIMPL`.|  
|[CBindStatusCallback::OnDataAvailable](#ondataavailable)|Appelé pour fournir des données à votre application dès que possible. Lit les données, puis appelle la fonction transmise à utiliser les données.|  
|[CBindStatusCallback::OnLowResource](#onlowresource)|Appelé lorsque les ressources sont insuffisantes. Retourne l’implémentation ATL `S_OK`.|  
|[CBindStatusCallback::OnObjectAvailable](#onobjectavailable)|Appelée par le moniker asynchrone à passer un pointeur d’interface objet à votre application. Retourne l’implémentation ATL `S_OK`.|  
|[CBindStatusCallback::OnProgress](#onprogress)|Appelé pour indiquer la progression d’un processus de téléchargement de données. Retourne l’implémentation ATL `S_OK`.|  
|[CBindStatusCallback::OnStartBinding](#onstartbinding)|Appelé lorsque la liaison est démarrée.|  
|[CBindStatusCallback::OnStopBinding](#onstopbinding)|Appelée lorsque le transfert de données asynchrone est arrêté.|  
|[CBindStatusCallback::StartAsyncDownload à laquelle sont](#startasyncdownload)|Initialise les octets disponibles et octets lus à zéro, crée un objet de flux de données de type push à partir d’une URL et les appels `OnDataAvailable` chaque fois que les données sont disponibles.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CBindStatusCallback::m_dwAvailableToRead](#m_dwavailabletoread)|Nombre d’octets à lire.|  
|[CBindStatusCallback::m_dwTotalRead](#m_dwtotalread)|Nombre total d’octets lus.|  
|[CBindStatusCallback::m_pFunc](#m_pfunc)|Pointeur vers la fonction appelée lorsque les données sont disponibles.|  
|[CBindStatusCallback::m_pT](#m_pt)|Pointeur vers l’objet demandant le transfert de données asynchrone.|  
|[CBindStatusCallback::m_spBindCtx](#m_spbindctx)|Pointeur vers le [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) interface pour l’opération de liaison actuel.|  
|[CBindStatusCallback::m_spBinding](#m_spbinding)|Pointeur vers le `IBinding` interface pour l’opération de liaison actuel.|  
|[CBindStatusCallback::m_spMoniker](#m_spmoniker)|Pointeur vers le [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) interface pour l’URL à utiliser.|  
|[CBindStatusCallback::m_spStream](#m_spstream)|Pointeur vers le [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) interface pour le transfert de données.|  
  
## <a name="remarks"></a>Notes  
 La classe `CBindStatusCallback` implémente l'interface `IBindStatusCallback`. `IBindStatusCallback`doit être implémentée par votre application afin qu’il peut recevoir des notifications d’un transfert de données asynchrone. Les monikers asynchrones fournies par le système utilise `IBindStatusCallback` transfèrent des méthodes pour envoyer et recevoir des informations sur les données asynchrones vers et à partir de votre objet.  
  
 En règle générale, le `CBindStatusCallback` objet est associé à une opération de liaison spécifique. Par exemple, dans le [ASYNC](../../visual-cpp-samples.md) exemple, lorsque vous définissez la propriété URL, il crée un `CBindStatusCallback` objet dans l’appel à `Download`:  
  
 [!code-cpp[NVC_ATL_Windowing&#86;](../../atl/codesnippet/cpp/cbindstatuscallback-class_1.h)]  
  
 Les monikers asynchrones utilise la fonction de rappel `OnData` pour appeler votre application lorsqu’elle contient des données. Le moniker asynchrone est fourni par le système.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CComObjectRootBase`  
  
 `IBindStatusCallback`  
  
 [CComObjectRootEx](../../atl/reference/ccomobjectrootex-class.md)  
  
 `CBindStatusCallback`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlctl.h  
  
##  <a name="cbindstatuscallback"></a>CBindStatusCallback::CBindStatusCallback  
 Constructeur.  
  
```
CBindStatusCallback();
```  
  
### <a name="remarks"></a>Remarques  
 Crée un objet pour recevoir des notifications concernant le transfert de données asynchrone. En règle générale, un objet est créé pour chaque opération de liaison.  
  
 Le constructeur initialise également [m_pT](#m_pt) et [m_pFunc](#m_pfunc) à **NULL**.  
  
##  <a name="dtor"></a>CBindStatusCallback :: ~ CBindStatusCallback  
 Destructeur.  
  
```
~CBindStatusCallback();
```  
  
### <a name="remarks"></a>Notes  
 Libère toutes les ressources attribuées.  
  
##  <a name="download"></a>CBindStatusCallback::Download  
 Crée un `CBindStatusCallback` objet et appelle `StartAsyncDownload` pour démarrer le téléchargement asynchrone des données à partir de l’URL spécifiée.  
  
```
static HRESULT Download(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 *pT*  
 [in] Pointeur vers l’objet demandant le transfert de données asynchrone. Le `CBindStatusCallback` objet est mise en modèle de classe de cet objet.  
  
 *pFunc*  
 [in] Pointeur vers la fonction qui reçoit les données lues. La fonction est un membre de classe de l’objet de type `T`. Consultez la page [StartAsyncDownload](#startasyncdownload) pour la syntaxe et un exemple.  
  
 `bstrURL`  
 [in] L’URL pour obtenir des données à partir de. Peut être n’importe quel nom de fichier ou URL valide. Ne peut pas être **NULL**. Exemple :  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] Le **IUnknown** du conteneur. **NULL** par défaut.  
  
 `bRelative`  
 [in] Indicateur qui indique si l’URL est relative ou absolue. **FALSE** par défaut, ce qui signifie que l’URL est absolu.  
  
### <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
### <a name="remarks"></a>Remarques  
 Chaque fois que les données sont disponibles, il est envoyé à l’objet via `OnDataAvailable`. `OnDataAvailable`lit les données et appelle la fonction vers laquelle pointée *pFunc* (par exemple, pour stocker les données ou l’imprimer à l’écran).  
  
##  <a name="getbindinfo"></a>CBindStatusCallback::GetBindInfo  
 Appelé pour indiquer le moniker de la liaison.  
  
```
STDMETHOD(GetBindInfo)(
    DWORD* pgrfBSCF,
    BINDINFO* pbindinfo);
```  
  
### <a name="parameters"></a>Paramètres  
 *pgrfBSCF*  
 [out] Pointeur vers **BINDF** des valeurs d’énumération qui indique comment l’opération de liaison doit se produire. Par défaut, définie avec les valeurs d’énumération suivantes :  
  
 **BINDF_ASYNCHRONOUS** téléchargement asynchrone.  
  
 **BINDF_ASYNCSTORAGE** `OnDataAvailable` retourne **E_PENDING** lorsque les données ne sont pas encore disponibles plutôt qu’un blocage jusqu'à ce que les données sont disponibles.  
  
 **BINDF_GETNEWESTVERSION** l’opération de liaison doit récupérer la version la plus récente des données.  
  
 **BINDF_NOWRITECACHE** l’opération de liaison ne doit pas stocker les données récupérées dans le cache disque.  
  
 *pbindinfo*  
 [dans, out] Un pointeur vers le **BINDINFO** structure donner plus d’informations sur la façon dont l’objet souhaite liaison se produise.  
  
### <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut définit la liaison asynchrone et à utiliser le modèle d’émission de données. Dans le modèle push de données, le moniker de l’opération de liaison asynchrone des lecteurs et en permanence le signale au client lorsque les nouvelles données sont disponibles.  
  
##  <a name="getpriority"></a>CBindStatusCallback::GetPriority  
 Appelée par le moniker asynchrone pour obtenir la priorité de l’opération de liaison.  
  
```
STDMETHOD(GetPriority)(LONG* pnPriority);
```  
  
### <a name="parameters"></a>Paramètres  
 *pnPriority*  
 [out] Adresse de la **LONG** variable qui, en cas de réussite, reçoit la priorité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne **E_NOTIMPL**.  
  
##  <a name="m_dwavailabletoread"></a>CBindStatusCallback::m_dwAvailableToRead  
 Peut être utilisé pour stocker le nombre d’octets disponibles pour la lecture.  
  
```
DWORD m_dwAvailableToRead;
```  
  
### <a name="remarks"></a>Notes  
 Initialisé à zéro dans `StartAsyncDownload`.  
  
##  <a name="m_dwtotalread"></a>CBindStatusCallback::m_dwTotalRead  
 Le total cumulé d’octets lu dans le transfert de données asynchrone.  
  
```
DWORD m_dwTotalRead;
```  
  
### <a name="remarks"></a>Notes  
 Incrémenté à chaque modification `OnDataAvailable` est appelée par le nombre d’octets lus réellement. Initialisé à zéro dans `StartAsyncDownload`.  
  
##  <a name="m_pfunc"></a>CBindStatusCallback::m_pFunc  
 La fonction vers laquelle pointe `m_pFunc` est appelée par `OnDataAvailable` une fois qu’il lit les données disponibles (par exemple, pour stocker les données ou l’imprimer à l’écran).  
  
```
ATL_PDATAAVAILABLE m_pFunc;
```  
  
### <a name="remarks"></a>Remarques  
 La fonction vers laquelle pointe `m_pFunc` est un membre de classe de l’objet et la syntaxe est la suivante :  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>* pbsc,`  
  
 `BYTE* pBytes,`  
  
 `DWORD dwSize`  
  
 `);`  
  
##  <a name="m_pt"></a>CBindStatusCallback::m_pT  
 Pointeur vers l’objet demandant le transfert de données asynchrone.  
  
```
T* m_pT;
```  
  
### <a name="remarks"></a>Remarques  
 Le `CBindStatusCallback` objet est mise en modèle de classe de cet objet.  
  
##  <a name="m_spbindctx"></a>CBindStatusCallback::m_spBindCtx  
 Un pointeur vers un [IBindCtx](http://msdn.microsoft.com/library/windows/desktop/ms693755) interface qui fournit l’accès au contexte de liaison (un objet qui stocke des informations sur une opération de liaison de moniker particulier).  
  
```
CComPtr<IBindCtx> m_spBindCtx;
```  
  
### <a name="remarks"></a>Remarques  
 Initialisé dans `StartAsyncDownload`.  
  
##  <a name="m_spbinding"></a>CBindStatusCallback::m_spBinding  
 Un pointeur vers le `IBinding` interface de l’opération de liaison actuel.  
  
```
CComPtr<IBinding> m_spBinding;
```  
  
### <a name="remarks"></a>Remarques  
 Initialisé dans `OnStartBinding` et publiée dans `OnStopBinding`.  
  
##  <a name="m_spmoniker"></a>CBindStatusCallback::m_spMoniker  
 Un pointeur vers le [IMoniker](http://msdn.microsoft.com/library/windows/desktop/ms679705) interface pour l’URL à utiliser.  
  
```
CComPtr<IMoniker> m_spMoniker;
```  
  
### <a name="remarks"></a>Remarques  
 Initialisé dans `StartAsyncDownload`.  
  
##  <a name="m_spstream"></a>CBindStatusCallback::m_spStream  
 Un pointeur vers le [IStream](http://msdn.microsoft.com/library/windows/desktop/aa380034) interface de l’opération de liaison actuel.  
  
```
CComPtr<IStream> m_spStream;
```  
  
### <a name="remarks"></a>Remarques  
 Initialisé dans `OnDataAvailable` à partir de la **STGMEDIUM** structure lorsque la **BCSF** indicateur est **BCSF_FIRSTDATANOTIFICATION** et libérée lorsque la **BCSF** indicateur est **BCSF_LASTDATANOTIFICATION**.  
  
##  <a name="ondataavailable"></a>CBindStatusCallback::OnDataAvailable  
 Les appels de monikers asynchrones fournies par le système `OnDataAvailable` pour fournir des données à l’objet dès que possible.  
  
```
STDMETHOD(  
    OnDataAvailable)(DWORD grfBSCF,
    DWORD dwSize,
    FORMATETC* /* pformatetc */,
    STGMEDIUM* pstgmed);
```  
  
### <a name="parameters"></a>Paramètres  
 *grfBSCF*  
 [in] A **BSCF** valeur d’énumération. Un ou plusieurs des opérations suivantes : **BSCF_FIRSTDATANOTIFICATION**, **BSCF_INTERMEDIARYDATANOTIFICATION**, ou **BSCF_LASTDATANOTIFICATION**.  
  
 `dwSize`  
 [in] La quantité cumulée (en octets) de données disponibles depuis le début de la liaison. Peut être égal à zéro, indiquant que la quantité de données ne s’applique pas ou qu’aucune quantité spécifique est devenue disponible.  
  
 *pFormatetc*  
 [in] Pointeur vers le [FORMATETC](http://msdn.microsoft.com/library/windows/desktop/ms682242) structure qui contient le format des données disponibles. S’il n’existe aucun format, peuvent être **CF_NULL**.  
  
 *pstgmed*  
 [in] Pointeur vers le [STGMEDIUM](http://msdn.microsoft.com/library/windows/desktop/ms695269) structure qui contient les données réelles disponibles.  
  
### <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
### <a name="remarks"></a>Remarques  
 `OnDataAvailable`lit les données, puis appelle une méthode de classe de l’objet (par exemple, pour stocker les données ou l’imprimer à l’écran). Consultez la page [CBindStatusCallback::StartAsyncDownload à laquelle sont](#startasyncdownload) pour plus d’informations.  
  
##  <a name="onlowresource"></a>CBindStatusCallback::OnLowResource  
 Appelé lorsque les ressources sont insuffisantes.  
  
```
STDMETHOD(OnLowResource)(DWORD /* dwReserved */);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwReserved`  
 Réservé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
##  <a name="onobjectavailable"></a>CBindStatusCallback::OnObjectAvailable  
 Appelée par le moniker asynchrone à passer un pointeur d’interface objet à votre application.  
  
```
STDMETHOD(OnObjectAvailable)(REFID /* riid */, IUnknown* /* punk */);
```  
  
### <a name="parameters"></a>Paramètres  
 `riid`  
 Identificateur d’interface de l’interface demandée. Non utilisé.  
  
 `punk`  
 Adresse de l’interface IUnknown. Non utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
##  <a name="onprogress"></a>CBindStatusCallback::OnProgress  
 Appelé pour indiquer la progression d’un processus de téléchargement de données.  
  
```
STDMETHOD(OnProgress)(
    ULONG /* ulProgress */,
    ULONG /* ulProgressMax */,
    ULONG /* ulStatusCode */,
    LPCWSTRONG /* szStatusText */);
```  
  
### <a name="parameters"></a>Paramètres  
 `ulProgress`  
 Entier long non signé. Non utilisé.  
  
 `ulProgressMax`  
 Entier long non signé n’est pas utilisé.  
  
 `ulStatusCode`  
 Entier long non signé. Non utilisé.  
  
 `szStatusText`  
 Adresse d’une valeur de chaîne. Non utilisé.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne `S_OK`.  
  
##  <a name="onstartbinding"></a>CBindStatusCallback::OnStartBinding  
 Définit le membre de données [m_spBinding](#m_spbinding) à la `IBinding` pointeur dans `pBinding`.  
  
```
STDMETHOD(OnStartBinding)(DWORD /* dwReserved */, IBinding* pBinding);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwReserved`  
 Réservé à un usage ultérieur.  
  
 `pBinding`  
 [in] Adresse de l’interface IBinding de l’utilisateur actuel l’opération de liaison. Il ne peut pas être NULL. Le client doit appeler AddRef sur ce pointeur pour conserver une référence à l’objet de liaison.  
  
##  <a name="onstopbinding"></a>CBindStatusCallback::OnStopBinding  
 Versions du `IBinding` le pointeur dans le membre de données [m_spBinding](#m_spbinding).  
  
```
STDMETHOD(OnStopBinding)(HRESULT hresult, LPCWSTR /* szError */);
```  
  
### <a name="parameters"></a>Paramètres  
 `hresult`  
 Code d’état retourné par l’opération de liaison.  
  
 szStatusText  
 Adresse d’une valeur de chaîne n’est pas utilisé.  
  
### <a name="remarks"></a>Remarques  
 Appelée par le moniker asynchrone fourni par le système pour indiquer la fin de l’opération de liaison.  
  
##  <a name="startasyncdownload"></a>CBindStatusCallback::StartAsyncDownload à laquelle sont  
 Démarre le téléchargement asynchrone des données à partir de l’URL spécifiée.  
  
```
HRESULT StartAsyncDownload(  
    T* pT,
    ATL_PDATAAVAILABLE pFunc,
    BSTR bstrURL,
    IUnknown* pUnkContainer = NULL,
    BOOL bRelative = FALSE);
```  
  
### <a name="parameters"></a>Paramètres  
 *pT*  
 [in] Pointeur vers l’objet demandant le transfert de données asynchrone. Le `CBindStatusCallback` objet est mise en modèle de classe de cet objet.  
  
 *pFunc*  
 [in] Pointeur vers la fonction qui reçoit les données en cours de lecture. La fonction est un membre de classe de l’objet de type `T`. Consultez la page **remarques** pour la syntaxe et un exemple.  
  
 `bstrURL`  
 [in] L’URL pour obtenir des données à partir de. Peut être n’importe quel nom de fichier ou URL valide. Ne peut pas être **NULL**. Exemple :  
  
 `CComBSTR mybstr =_T("http://somesite/data.htm")`  
  
 `pUnkContainer`  
 [in] Le **IUnknown** du conteneur. **NULL** par défaut.  
  
 `bRelative`  
 [in] Indicateur qui indique si l’URL est relative ou absolue. **FALSE** par défaut, ce qui signifie que l’URL est absolu.  
  
### <a name="return-value"></a>Valeur de retour  
 Un de la norme `HRESULT` valeurs.  
  
### <a name="remarks"></a>Remarques  
 Chaque fois que les données sont disponibles, il est envoyé à l’objet via `OnDataAvailable`. `OnDataAvailable`lit les données et appelle la fonction vers laquelle pointée *pFunc* (par exemple, pour stocker les données ou l’imprimer à l’écran).  
  
 La fonction vers laquelle pointe *pFunc* est un membre de classe de l’objet et la syntaxe est la suivante :  
  
 `void Function_Name(`  
  
 `CBindStatusCallback<T>*` `pbsc` `,`  
  
 `BYTE*` `pBytes` `,`  
  
 `DWORD` `dwSize`  
  
 `);`  
  
 Dans l’exemple suivant (extrait de la [ASYNC](../../visual-cpp-samples.md) exemple), la fonction `OnData` écrit les données reçues dans une zone de texte.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_ATL_Windowing&#87;](../../atl/codesnippet/cpp/cbindstatuscallback-class_2.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)

