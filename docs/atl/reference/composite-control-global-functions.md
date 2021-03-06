---
title: Fonctions globales de contrôle composite | Documents Microsoft
ms.custom: ''
ms.date: 11/04/2016
ms.technology:
- cpp-atl
ms.topic: reference
f1_keywords:
- atlhost/ATL::AtlAxDialogBox
- atlhost/ATL::AtlAxCreateDialog
- atlhost/ATL::AtlAxCreateControl
- atlhost/ATL::AtlAxCreateControlEx
- atlhost/ATL::AtlAxCreateControlLic
- atlhost/ATL::AtlAxCreateControlLicEx
- atlhost/ATL::AtlAxAttachControl
- atlhost/ATL::AtlAxGetHost
- atlhost/ATL::AtlAxGetControl
- atlhost/ATL::AtlSetChildSite
- atlhost/ATL::AtlAxWinInit
- atlhost/ATL::AtlAxWinTerm
- atlhost/ATL::AtlGetObjectSourceInterface
dev_langs:
- C++
helpviewer_keywords:
- composite controls, global functions
ms.assetid: 536884cd-e863-4c7a-ab0a-604dc60a0bbe
author: mikeblome
ms.author: mblome
ms.workload:
- cplusplus
ms.openlocfilehash: 7c62d5056f28460644084296598ae865c6ff5f48
ms.sourcegitcommit: be2a7679c2bd80968204dee03d13ca961eaa31ff
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 05/03/2018
---
# <a name="composite-control-global-functions"></a>Fonctions globales de contrôle composite
Ces fonctions fournissent la prise en charge pour la création de boîtes de dialogue et de création, d’hébergement et de licences des contrôles ActiveX.  
  
> [!IMPORTANT]
>  Les fonctions répertoriées dans le tableau suivant ne peut pas être utilisées dans les applications qui s’exécutent dans le Windows Runtime.  
  
|||  
|-|-|  
|[AtlAxDialogBox](#atlaxdialogbox)|Crée une boîte de dialogue modale à partir d'un modèle de boîte de dialogue fourni par l'utilisateur. La boîte de dialogue peut contenir des contrôles ActiveX.|  
|[API AtlAxCreateDialog](#atlaxcreatedialog)|Crée une boîte de dialogue non modale à partir d'un modèle de boîte de dialogue fourni par l'utilisateur. La boîte de dialogue peut contenir des contrôles ActiveX.|  
|[AtlAxCreateControl](#atlaxcreatecontrol)|Crée un contrôle ActiveX, puis initialise et héberge ce dernier dans la fenêtre spécifiée.|  
|[AtlAxCreateControlEx](#atlaxcreatecontrolex)|Crée un contrôle ActiveX, lui, héberge ce dernier dans la fenêtre spécifiée et récupère un pointeur d’interface (ou pointeurs) à partir du contrôle.|  
|[AtlAxCreateControlLic](#atlaxcreatecontrollic)|Crée un contrôle ActiveX sous licence, puis initialise et héberge ce dernier dans la fenêtre spécifiée.|  
|[AtlAxCreateControlLicEx](#atlaxcreatecontrollicex)|Crée un contrôle ActiveX sous licence, il initialise, héberge ce dernier dans la fenêtre spécifiée et récupère un pointeur d’interface (ou pointeurs) à partir du contrôle.|  
|[AtlAxAttachControl](#atlaxattachcontrol)|Joint un contrôle précédemment créé à la fenêtre spécifiée.|  
|[AtlAxGetHost](#atlaxgethost)|Permet d’obtenir un pointeur d’interface direct vers le conteneur d’une fenêtre spécifique (le cas échéant), fonction de son handle.|  
|[AtlAxGetControl](#atlaxgetcontrol)|Permet d’obtenir un pointeur d’interface direct vers le contrôle contenu dans une fenêtre spécifique (le cas échéant), fonction de son handle.|  
|[AtlSetChildSite](#atlsetchildsite)|Initialise le **IUnknown** du site enfant.|  
|[AtlAxWinInit](#atlaxwininit)|Initialise le code d’hébergement pour les objets AxWin.|  
|[AtlAxWinTerm](#atlaxwinterm)|N’initialise pas le code d’hébergement pour les objets AxWin.|  
|[AtlGetObjectSourceInterface](#atlgetobjectsourceinterface)|Retourne des informations sur l’interface source par défaut d’un objet.|  

## <a name="requirements"></a>Spécifications  
 **En-tête :** atlhost.h  

##  <a name="atlaxdialogbox"></a>  AtlAxDialogBox  
 Crée une boîte de dialogue modale à partir d'un modèle de boîte de dialogue fourni par l'utilisateur.  
   
```
ATLAPI_(int) AtlAxDialogBox(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstance`  
 [in] Identifie une instance du module dont le fichier exécutable contient le modèle de boîte de dialogue.  
  
 `lpTemplateName`  
 [in] Identifie le modèle de boîte de dialogue. Ce paramètre est le pointeur vers une chaîne de caractères terminée par null qui spécifie le nom de la boîte de dialogue modèle ou une valeur entière qui spécifie l’identificateur de ressource de modèle de boîte de dialogue. Si le paramètre spécifie un identificateur de ressource, son mot de poids fort doit être égal à zéro et son mot de poids faible doit contenir l’identificateur. Vous pouvez utiliser la [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) macro pour créer cette valeur.  
  
 `hWndParent`  
 [in] Identifie la fenêtre propriétaire de la boîte de dialogue.  
  
 `lpDialogProc`  
 [in] Pointe vers la procédure de boîte de dialogue. Pour plus d’informations sur la procédure de boîte de dialogue, consultez [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Spécifie la valeur à passer à la boîte de dialogue dans le **lParam** paramètre de la **WM_INITDIALOG** message.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
### <a name="remarks"></a>Notes  
 Pour utiliser **AtlAxDialogBox** avec un modèle de boîte de dialogue qui contient un contrôle ActiveX, spécifiez une valide **CLSID**, **APPID** ou la chaîne d’URL en tant que la *texte* champ le **contrôle** section de la ressource de boîte de dialogue, ainsi que « AtlAxWin80 » en tant que le *nom de la classe* champ sous la même section. Ce qui suit montre les valide **contrôle** section peut ressembler à :  
  
```  
CONTROL    "{04FE35E9-ADBC-4f1d-83FE-8FA4D1F71C7F}", IDC_TEST,  
    "AtlAxWin80", WS_GROUP | WS_TABSTOP, 0, 0, 100, 100  
```  
  
 Pour plus d’informations sur la modification de scripts de ressources, consultez [Comment : ouvrir un fichier de Script de ressources au Format texte](../../windows/how-to-open-a-resource-script-file-in-text-format.md). Pour plus d’informations sur les instructions de définition de ressource de contrôle, consultez [les paramètres de contrôle communs](http://msdn.microsoft.com/library/windows/desktop/aa380902) sous Windows SDK *: outils du Kit de développement logiciel*.  
  
 Pour plus d’informations sur les boîtes de dialogue en général, reportez-vous à [DialogBox](http://msdn.microsoft.com/library/windows/desktop/ms645452) et [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) dans le Kit de développement logiciel Windows.  
  
##  <a name="atlaxcreatedialog"></a>  API AtlAxCreateDialog  
 Crée une boîte de dialogue non modale à partir d'un modèle de boîte de dialogue fourni par l'utilisateur.  
  
```
ATLAPI_(HWND) AtlAxCreateDialog(
    HINSTANCE hInstance,
    LPCWSTR lpTemplateName,
    HWND hWndParent,
    DLGPROC lpDialogProc,
    LPARAM dwInitParam);
```  
  
### <a name="parameters"></a>Paramètres  
 `hInstance`  
 [in] Identifie une instance du module dont le fichier exécutable contient le modèle de boîte de dialogue.  
  
 `lpTemplateName`  
 [in] Identifie le modèle de boîte de dialogue. Ce paramètre est le pointeur vers une chaîne de caractères terminée par null qui spécifie le nom de la boîte de dialogue modèle ou une valeur entière qui spécifie l’identificateur de ressource de modèle de boîte de dialogue. Si le paramètre spécifie un identificateur de ressource, son mot de poids fort doit être égal à zéro et son mot de poids faible doit contenir l’identificateur. Vous pouvez utiliser la [MAKEINTRESOURCE](http://msdn.microsoft.com/library/windows/desktop/ms648029) macro pour créer cette valeur.  
  
 `hWndParent`  
 [in] Identifie la fenêtre propriétaire de la boîte de dialogue.  
  
 `lpDialogProc`  
 [in] Pointe vers la procédure de boîte de dialogue. Pour plus d’informations sur la procédure de boîte de dialogue, consultez [DialogProc](http://msdn.microsoft.com/library/windows/desktop/ms645469).  
  
 `dwInitParam`  
 [in] Spécifie la valeur à passer à la boîte de dialogue dans le **lParam** paramètre de la **WM_INITDIALOG** message.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
### <a name="remarks"></a>Notes  
 La boîte de dialogue peut contenir des contrôles ActiveX.  
  
 Consultez [CreateDialog](http://msdn.microsoft.com/library/windows/desktop/ms645434) et [CreateDialogParam](http://msdn.microsoft.com/library/windows/desktop/ms645445) dans le Kit de développement logiciel Windows.  
  
##  <a name="atlaxcreatecontrol"></a>  AtlAxCreateControl  
 Crée un contrôle ActiveX, puis initialise et héberge ce dernier dans la fenêtre spécifiée.  
  

```
ATLAPI AtlAxCreateControl(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Un pointeur vers une chaîne à passer au contrôle. Doit être au format de l’une des manières suivantes :  
  
-   Un ProgID tels que « MSCAL. Calendar.7 »  
  
-   Un CLSID tels que « {8E27C92B-1264-101C-8A2F-040224009C02} »  
  
-   Une URL comme «http://www.microsoft.com»  
  
-   Une référence à un document actif comme « file://\\\Documents\MyDoc.doc »  
  
-   Un fragment de code HTML comme « MSHTML :\<HTML >\<corps > Il s’agit d’une ligne de texte\</corps >\</HTML > »  
  
    > [!NOTE]
    >  « MSHTML : » doit précéder le fragment HTML afin qu’il est désigné comme étant un flux MSHTML.  
  
 `hWnd`  
 [in] Handle vers la fenêtre qui sera liée au contrôle.  
  
 `pStream`  
 [in] Pointeur vers un flux qui est utilisé pour initialiser les propriétés du contrôle. Peut être **NULL**.  
  
 `ppUnkContainer`  
 [out] L’adresse d’un pointeur qui recevra le **IUnknown** du conteneur. Peut être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
### <a name="remarks"></a>Notes  
 Cette fonction globale vous donne le même résultat que l’appel [AtlAxCreateControlEx](#atlaxcreatecontrolex)( `lpszName` **,** `hWnd` **,** `pStream` **, NULL, NULL, NULL, NULL** ) ;.  
  
 Pour créer un contrôle ActiveX sous licence, consultez [AtlAxCreateControlLic](#atlaxcreatecontrollic).  
  
##  <a name="atlaxcreatecontrolex"></a>  AtlAxCreateControlEx  
 Crée un contrôle ActiveX, puis initialise et héberge ce dernier dans la fenêtre spécifiée. Un pointeur d'interface et un récepteur d'événements du nouveau contrôle peuvent également être créés.  
  
```
ATLAPI AtlAxCreateControlEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Un pointeur vers une chaîne à passer au contrôle. Doit être au format de l’une des manières suivantes :  
  
-   Un ProgID tels que « MSCAL. Calendar.7 »  
  
-   Un CLSID tels que « {8E27C92B-1264-101C-8A2F-040224009C02} »  
  
-   Une URL comme «http://www.microsoft.com»  
  
-   Une référence à un document actif comme « file://\\\Documents\MyDoc.doc »  
  
-   Un fragment de code HTML comme « MSHTML :\<HTML >\<corps > Il s’agit d’une ligne de texte\</corps >\</HTML > »  
  
    > [!NOTE]
    >  « MSHTML : » doit précéder le fragment HTML afin qu’il est désigné comme étant un flux MSHTML.  
  
 `hWnd`  
 [in] Handle vers la fenêtre qui sera liée au contrôle.  
  
 `pStream`  
 [in] Pointeur vers un flux qui est utilisé pour initialiser les propriétés du contrôle. Peut être **NULL**.  
  
 `ppUnkContainer`  
 [out] L’adresse d’un pointeur qui recevra le **IUnknown** du conteneur. Peut être **NULL**.  
  
 `ppUnkControl`  
 [out] L’adresse d’un pointeur qui recevra le **IUnknown** du contrôle créé. Peut être **NULL**.  
  
 `iidSink`  
 L’identificateur d’interface d’une interface sortante sur l’objet de relation contenant-contenu.  
  
 *punkSink*  
 Un pointeur vers le **IUnknown** interface de l’objet récepteur pour être connectés au point de connexion spécifié par `iidSink` sur l’objet de relation contenant-contenu une fois que l’objet de relation contenant-contenu a été créé avec succès.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
### <a name="remarks"></a>Notes  
 `AtlAxCreateControlEx` est semblable à [AtlAxCreateControl](#atlaxcreatecontrol) mais permet également de recevoir un pointeur d’interface pour le contrôle qui vient d’être créé et configuré un récepteur d’événements pour recevoir les événements déclenchés par le contrôle.  
  
 Pour créer un contrôle ActiveX sous licence, consultez [AtlAxCreateControlLicEx](#atlaxcreatecontrollicex).  
  
##  <a name="atlaxcreatecontrollic"></a>  AtlAxCreateControlLic  
 Crée un contrôle ActiveX sous licence, puis initialise et héberge ce dernier dans la fenêtre spécifiée.  

```
ATLAPI AtlAxCreateControlLic(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Un pointeur vers une chaîne à passer au contrôle. Doit être au format de l’une des manières suivantes :  
  
-   Un ProgID tels que « MSCAL. Calendar.7 »  
  
-   Un CLSID tels que « {8E27C92B-1264-101C-8A2F-040224009C02} »  
  
-   Une URL comme «http://www.microsoft.com»  
  
-   Une référence à un document actif comme « file://\\\Documents\MyDoc.doc »  
  
-   Un fragment de code HTML comme « MSHTML :\<HTML >\<corps > Il s’agit d’une ligne de texte\</corps >\</HTML > »  
  
    > [!NOTE]
    >  « MSHTML : » doit précéder le fragment HTML afin qu’il est désigné comme étant un flux MSHTML.  
  
 `hWnd`  
 Handle vers la fenêtre qui sera liée au contrôle.  
  
 `pStream`  
 Pointeur vers un flux qui est utilisé pour initialiser les propriétés du contrôle. Peut être **NULL**.  
  
 `ppUnkContainer`  
 L’adresse d’un pointeur qui recevra le **IUnknown** du conteneur. Peut être **NULL**.  
  
 `bstrLic`  
 Le BSTR contenant la licence pour le contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
### <a name="example"></a>Exemple  
 Consultez [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple montrant comment utiliser `AtlAxCreateControlLic`.  
  
##  <a name="atlaxcreatecontrollicex"></a>  AtlAxCreateControlLicEx  
 Crée un contrôle ActiveX sous licence, puis initialise et héberge ce dernier dans la fenêtre spécifiée. Un pointeur d'interface et un récepteur d'événements du nouveau contrôle peuvent également être créés.  
  
```
ATLAPI AtlAxCreateControlLicEx(
    LPCOLESTR lpszName,
    HWND hWnd,
    IStream* pStream,
    IUnknown** ppUnkContainer,
    IUnknown** ppUnkControl,
    REFIID iidSink = IID_NULL,
    IUnknown* punkSink = NULL,
    BSTR bstrLic = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszName`  
 Un pointeur vers une chaîne à passer au contrôle. Doit être au format de l’une des manières suivantes :  
  
-   Un ProgID tels que « MSCAL. Calendar.7 »  
  
-   Un CLSID tels que « {8E27C92B-1264-101C-8A2F-040224009C02} »  
  
-   Une URL comme «http://www.microsoft.com»  
  
-   Une référence à un document actif comme « file://\\\Documents\MyDoc.doc »  
  
-   Un fragment de code HTML comme « MSHTML :\<HTML >\<corps > Il s’agit d’une ligne de texte\</corps >\</HTML > »  
  
    > [!NOTE]
    >  « MSHTML : » doit précéder le fragment HTML afin qu’il est désigné comme étant un flux MSHTML.  
  
 `hWnd`  
 Handle vers la fenêtre qui sera liée au contrôle.  
  
 `pStream`  
 Pointeur vers un flux qui est utilisé pour initialiser les propriétés du contrôle. Peut être **NULL**.  
  
 `ppUnkContainer`  
 L’adresse d’un pointeur qui recevra le **IUnknown** du conteneur. Peut être **NULL**.  
  
 `ppUnkControl`  
 [out] L’adresse d’un pointeur qui recevra le **IUnknown** du contrôle créé. Peut être **NULL**.  
  
 `iidSink`  
 L’identificateur d’interface d’une interface sortante sur l’objet de relation contenant-contenu.  
  
 *punkSink*  
 Un pointeur vers le **IUnknown** interface de l’objet récepteur pour être connectés au point de connexion spécifié par `iidSink` sur l’objet de relation contenant-contenu une fois que l’objet de relation contenant-contenu a été créé avec succès.  
  
 `bstrLic`  
 Le BSTR contenant la licence pour le contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
### <a name="remarks"></a>Notes  
 `AtlAxCreateControlLicEx` est semblable à [AtlAxCreateControlLic](#atlaxcreatecontrollic) mais permet également de recevoir un pointeur d’interface pour le contrôle qui vient d’être créé et configuré un récepteur d’événements pour recevoir les événements déclenchés par le contrôle.  
  
### <a name="example"></a>Exemple  
 Consultez [hébergement ActiveX des contrôles à l’aide de ATL AXHost](../../atl/hosting-activex-controls-using-atl-axhost.md) pour obtenir un exemple montrant comment utiliser `AtlAxCreateControlLicEx`.  
  
##  <a name="atlaxattachcontrol"></a>  AtlAxAttachControl  
 Joint un contrôle précédemment créé à la fenêtre spécifiée.  
  
```
ATLAPI AtlAxAttachControl(
    IUnknown* pControl,
    HWND hWnd,
    IUnknown** ppUnkContainer);
```  
  
### <a name="parameters"></a>Paramètres  
 `pControl`  
 [in] Un pointeur vers le **IUnknown** du contrôle.  
  
 `hWnd`  
 [in] Handle vers la fenêtre qui va héberger le contrôle.  
  
 `ppUnkContainer`  
 [out] Un pointeur vers un pointeur vers le **IUnknown** de l’objet conteneur.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
### <a name="remarks"></a>Notes  
 Utilisez [AtlAxCreateControlEx](#atlaxcreatecontrolex) et [AtlAxCreateControl](#atlaxcreatecontrol) créer et attacher un contrôle simultanément.  
  
> [!NOTE]
>  L’objet de contrôle qui est attaché doit être correctement initialisée avant d’appeler `AtlAxAttachControl`.  
  
##  <a name="atlaxgethost"></a>  AtlAxGetHost  
 Obtient un pointeur d'interface direct vers le conteneur d'une fenêtre spécifique (le cas échéant), en fonction de son handle.  
  
```
ATLAPI AtlAxGetHost(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Paramètres  
 `h`  
 [in] Un handle de fenêtre qui héberge le contrôle.  
  
 `pp`  
 [out] Le **IUnknown** du conteneur du contrôle.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
##  <a name="atlaxgetcontrol"></a>  AtlAxGetControl  
 Obtient un pointeur d'interface direct vers le contrôle contenu dans une fenêtre spécifique en fonction de son handle.  
  
```
ATLAPI AtlAxGetControl(HWND h, IUnknown** pp);
```  
  
### <a name="parameters"></a>Paramètres  
 `h`  
 [in] Un handle de fenêtre qui héberge le contrôle.  
  
 `pp`  
 [out] Le **IUnknown** du contrôle hébergé.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs HRESULT standards.  
  
##  <a name="atlsetchildsite"></a>  AtlSetChildSite  
 Appelez cette fonction pour définir le site de l’objet enfant à la **IUnknown** de l’objet parent.  
  
```
HRESULT AtlSetChildSite(IUnknown* punkChild, IUnknown* punkParent);
```  
  
### <a name="parameters"></a>Paramètres  
 *punkChild*  
 [in] Un pointeur vers le **IUnknown** interface de l’enfant.  
  
 `punkParent`  
 [in] Un pointeur vers le **IUnknown** interface du parent.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
##  <a name="atlaxwininit"></a>  AtlAxWinInit  
 Cette fonction initialise le contrôle du ATL code d’hébergement en inscrivant le **« AtlAxWin80 »** et **« AtlAxWinLic80 »** classes de fenêtre ainsi que quelques messages de fenêtre personnalisés.  
  
```
ATLAPI_(BOOL) AtlAxWinInit();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si l’initialisation du contrôle de code d’hébergement a réussi ; dans le cas contraire **FALSE**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction doit être appelée avant d’utiliser le contrôle ATL API d’hébergement. Après un appel à cette fonction, le **« AtlAxWin »** classe de fenêtre peut être utilisée dans les appels à [CreateWindow](http://msdn.microsoft.com/library/windows/desktop/ms632679) ou [CreateWindowEx](http://msdn.microsoft.com/library/windows/desktop/ms632680), comme décrit dans le Kit de développement logiciel Windows.  

##  <a name="atlaxwinterm"></a>  AtlAxWinTerm  
 Cette fonction n’initialise pas le contrôle du ATL code d’hébergement en annulant l’enregistrement du **« AtlAxWin80 »** et **« AtlAxWinLic80 »** classes de fenêtre.  
  
```
inline BOOL AtlAxWinTerm();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne toujours **TRUE**.  
  
### <a name="remarks"></a>Notes  
 Cette fonction appelle simplement [UnregisterClass](http://msdn.microsoft.com/library/windows/desktop/ms644899) comme décrit dans le Kit de développement logiciel Windows.  
  
 Appelez cette fonction pour nettoyer une fois que toutes les fenêtres hôtes existantes ont été détruits si vous avez appelé [AtlAxWinInit](#atlaxwininit) et vous n’avez plus besoin de créer des fenêtres de l’hôte. Si vous n’appelez pas cette fonction, la classe de fenêtre sera annulée automatiquement lorsque le processus se termine.  
  
##  <a name="atlgetobjectsourceinterface"></a>  AtlGetObjectSourceInterface  
 Appelez cette fonction pour récupérer des informations sur l'interface source par défaut d'un objet.  
  
```
ATLAPI AtlGetObjectSourceInterface(
    IUnknown* punkObj,
    GUID* plibid,
    IID* piid,
    unsigned short* pdwMajor,
    unsigned short* pdwMinor);
```  
  
### <a name="parameters"></a>Paramètres  
 `punkObj`  
 [in] Pointeur vers l’objet pour lequel les informations sont à retourner.  
  
 `plibid`  
 [out] Pointeur vers le LIBID de la bibliothèque de types contenant la définition de l’interface source.  
  
 `piid`  
 [out] Pointeur vers l’ID de l’interface de source de l’objet par défaut.  
  
 *pdwMajor*  
 [out] Pointeur vers le numéro de version principale de la bibliothèque de types contenant la définition de l’interface source.  
  
 *pdwMinor*  
 [out] Pointeur vers le numéro de version mineure de la bibliothèque de types contenant la définition de l’interface source.  
  
### <a name="return-value"></a>Valeur de retour  
 Une valeur HRESULT standard.  
  
### <a name="remarks"></a>Notes  
 `AtlGetObjectSourceInterface` peut fournir vous avec l’ID de l’interface source par défaut, avec LIBID et majeures et les numéros de version mineure de la bibliothèque de types décrivant cette interface.  
  
> [!NOTE]
>  Pour cette fonction récupérer les informations demandées, l’objet représenté par `punkObj` doit implémenter `IDispatch` (et retournent des informations de type via **IDispatch::GetTypeInfo**) et il doit également implémenter le `IProvideClassInfo2` ou `IPersist`. Les informations de type pour l’interface source doivent être dans la même bibliothèque de types en tant que les informations de type `IDispatch`.  
  
### <a name="example"></a>Exemple  
 L’exemple ci-dessous montre comment vous pouvez définir une classe de récepteur d’événements, `CEasySink`, afin de réduire le nombre d’arguments de modèle que vous pouvez passer à `IDispEventImpl` pour les éléments essentiels. `EasyAdvise` et `EasyUnadvise` utiliser `AtlGetObjectSourceInterface` pour initialiser le [IDispEventImpl](../../atl/reference/idispeventimpl-class.md) membres avant d’appeler [DispEventAdvise](idispeventsimpleimpl-class.md#dispeventadvise) ou [DispEventUnadvise](idispeventsimpleimpl-class.md#dispeventunadvise).  
  
 [!code-cpp[NVC_ATL_Windowing#93](../../atl/codesnippet/cpp/composite-control-global-functions_1.h)]  
  
## <a name="see-also"></a>Voir aussi  
 [Fonctions](../../atl/reference/atl-functions.md)   
 [Macros de contrôle composite](../../atl/reference/composite-control-macros.md)
