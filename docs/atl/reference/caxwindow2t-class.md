---
title: Classe de CAxWindow2T | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- ATL::CAxWindow2T<TBase>
- ATL::CAxWindow2T
- CAxWindow2T
- ATL.CAxWindow2T<TBase>
- ATL.CAxWindow2T
- CAxWindow2
dev_langs:
- C++
helpviewer_keywords:
- CAxWindow2 class
ms.assetid: b87bc943-7991-4537-b902-2138d7f4d837
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
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: deed13f7e44246eca1e9d3d138f73d0f540dc0b1
ms.lasthandoff: 02/24/2017

---
# <a name="caxwindow2t-class"></a>CAxWindow2T (classe)
Cette classe fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX et prend également en charge pour l’hébergement de contrôles ActiveX sous licence.  
  
> [!IMPORTANT]
>  Cette classe et ses membres ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
## <a name="syntax"></a>Syntaxe  
  
```
template <class TBase = CWindow>
    class CAxWindow2T :
    public CAxWindowT<TBase>
```  
  
#### <a name="parameters"></a>Paramètres  
 *TBase*  
 La classe à partir de laquelle `CAxWindowT` dérive.  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAxWindow2T::CAxWindow2T](#caxwindow2t)|Construit un objet `CAxWindow2T`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CAxWindow2T::Create](#create)|Crée une fenêtre hôte.|  
|[CAxWindow2T::CreateControlLic](#createcontrollic)|Crée un contrôle ActiveX sous licence, puis initialise et héberge ce dernier dans la fenêtre spécifiée.|  
|[CAxWindow2T::CreateControlLicEx](#createcontrollicex)|Crée un contrôle ActiveX sous licence, l’initialise, héberge ce dernier dans la fenêtre spécifiée et récupère un pointeur d’interface (ou pointeurs) du contrôle.|  
|[CAxWindow2T::GetWndClassName](#getwndclassname)|Méthode statique qui Récupère le nom de la classe de fenêtre.|  
  
### <a name="public-operators"></a>Op&#233;rateurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CAxWindow2T::operator =](#operator_eq)|Assigne une `HWND` à un fichier `CAxWindow2T` objet.|  
  
## <a name="remarks"></a>Remarques  
 `CAxWindow2T`Fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX. `CAxWindow2T`prend également en charge pour l’hébergement de contrôles ActiveX sous licence. L’hébergement est fournie par « **AtlAxWinLic80**», qui est encapsulé par `CAxWindow2T`.  
  
 Classe `CAxWindow2` est implémentée comme une spécialisation de la `CAxWindow2T` classe. Cette spécialisation est déclarée en tant que :  
  
 `typedef CAxWindow2T <CWindow> CAxWindow2;`  
  
> [!NOTE]
> `CAxWindowT`les membres sont décrits dans le [Caxwindow2](../../atl/reference/caxwindow-class.md).  
  
 Consultez la page [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple qui utilise les membres de cette classe.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `TBase`  
  
 `CAxWindowT`  
  
 `CAxWindow2T`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** atlwin.h  
  
##  <a name="a-namecaxwindow2ta--caxwindow2tcaxwindow2t"></a><a name="caxwindow2t"></a>CAxWindow2T::CAxWindow2T  
 Construit un objet `CAxWindow2T`.  
  
```
CAxWindow2T(HWND  hWnd = NULL) : CAxWindowT<TBase>(hWnd)
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 Handle d’une fenêtre existante.  
  
##  <a name="a-namecreatea--caxwindow2tcreate"></a><a name="create"></a>CAxWindow2T::Create  
 Crée une fenêtre hôte.  
  
```
HWND Create(
    HWND hWndParent,
    _U_RECT rect = NULL,
    LPCTSTR szWindowName = NULL,
    DWORD dwStyle = 0,
    DWORD dwExStyle = 0,
    _U_MENUorID MenuOrID = 0U,
    LPVOID lpCreateParam = NULL);
```  
  
### <a name="remarks"></a>Remarques  
 `CAxWindow2T::Create`appels [CWindow::Create](../../atl/reference/cwindow-class.md#create) avec la `LPCTSTR``lpstrWndClass` paramètre défini pour la classe de fenêtre qui assure l’hébergement du contrôle ( **AtlAxWinLic80**).  
  
 Consultez `CWindow::Create` pour obtenir une description des paramètres et valeur de retour.  
  
 **Remarque** si 0 est utilisée comme valeur pour le `MenuOrID` paramètre, il doit être spécifié en tant que 0 u (valeur par défaut) pour éviter une erreur du compilateur.  
  
### <a name="example"></a>Exemple  
 Consultez la page [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple qui utilise `CAxWindow2T::Create`.  
  
##  <a name="a-namecreatecontrollica--caxwindow2tcreatecontrollic"></a><a name="createcontrollic"></a>CAxWindow2T::CreateControlLic  
 Crée un contrôle ActiveX sous licence, puis initialise et héberge ce dernier dans la fenêtre spécifiée.  
  
```
HRESULT CreateControlLic(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);

HRESULT CreateControlLic(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    BSTR bstrLicKey = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `bstrLicKey`  
 La clé de licence pour le contrôle ; NULL si la création d’un contrôle sans licence.  
  
### <a name="remarks"></a>Notes  
 Consultez la page [CAxWindow::CreateControl](../../atl/reference/caxwindow-class.md#createcontrol) pour obtenir une description des autres paramètres et valeur de retour.  
  
### <a name="example"></a>Exemple  
 Consultez la page [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple qui utilise `CAxWindow2T::CreateControlLic`.  
  
##  <a name="a-namecreatecontrollicexa--caxwindow2tcreatecontrollicex"></a><a name="createcontrollicex"></a>CAxWindow2T::CreateControlLicEx  
 Crée un contrôle ActiveX sous licence, l’initialise, héberge ce dernier dans la fenêtre spécifiée et récupère un pointeur d’interface (ou pointeurs) du contrôle.  
  
```
HRESULT CreateControlLicEx(
    LPCOLESTR lpszName,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLicKey = NULL);

    HRESULT CreateControlLicEx(
    DWORD dwResID,
    IStream* pStream = NULL,
    IUnknown** ppUnkContainer = NULL,
    IUnknown** ppUnkControl = NULL,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLickey = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `bstrLicKey`  
 La clé de licence pour le contrôle ; NULL si la création d’un contrôle sans licence.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [CAxWindow::CreateControlEx](../../atl/reference/caxwindow-class.md#createcontrolex) pour obtenir une description des autres paramètres et valeur de retour.  
  
### <a name="example"></a>Exemple  
 Consultez la page [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple qui utilise `CAxWindow2T::CreateControlLicEx`.  
  
##  <a name="a-namegetwndclassnamea--caxwindow2tgetwndclassname"></a><a name="getwndclassname"></a>CAxWindow2T::GetWndClassName  
 Récupère le nom de la classe de fenêtre.  
  
```
static LPCTSTR GetWndClassName();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers une chaîne contenant le nom de la classe de fenêtre ( **AtlAxWinLic80**) qui peut héberger des contrôles ActiveX sous licence et sans licence.  
  
##  <a name="a-nameoperatoreqa--caxwindow2toperator-"></a><a name="operator_eq"></a>CAxWindow2T::operator =  
 Assigne une `HWND` à un fichier `CAxWindow2T` objet.  
  
```
CAxWindow2T<TBase>& operator= (HWND hWnd);
```  
  
### <a name="parameters"></a>Paramètres  
 `hWnd`  
 Handle d’une fenêtre existante.  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../../atl/atl-class-overview.md)   
 [Forum aux questions sur la contenance de contrôles](../../atl/atl-control-containment-faq.md)

