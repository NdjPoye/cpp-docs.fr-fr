---
title: Classe de CPageSetupDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPageSetupDialog
dev_langs:
- C++
helpviewer_keywords:
- page setup
- Print Setup dialog box
- Page Setup dialog box
- OLE Page Setup dialog box
- CPageSetupDialog class
ms.assetid: 049c0ac8-f254-4854-9414-7a8271d1447a
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
ms.openlocfilehash: 81d36b3a005a291aca4c77dc9771a4fe92c304ee
ms.lasthandoff: 02/24/2017

---
# <a name="cpagesetupdialog-class"></a>CPageSetupDialog (classe)
Encapsule les services fournis par la boîte de dialogue Mise en page OLE courante Windows avec une prise en charge supplémentaire pour définir et modifier les marges d'impression.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPageSetupDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog)|Construit un objet `CPageSetupDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPageSetupDialog::CreatePrinterDC](#createprinterdc)|Crée un contexte de périphérique d’impression.|  
|[CPageSetupDialog::DoModal](#domodal)|Affiche la boîte de dialogue et permet la création de l’utilisateur une sélection.|  
|[CPageSetupDialog::GetDeviceName](#getdevicename)|Retourne le nom du périphérique de l’imprimante.|  
|[CPageSetupDialog::GetDevMode](#getdevmode)|Retourne l’actuel `DEVMODE` de l’imprimante.|  
|[CPageSetupDialog::GetDriverName](#getdrivername)|Retourne le pilote utilisé par l’imprimante.|  
|[CPageSetupDialog::GetMargins](#getmargins)|Retourne les paramètres actuels de la marge de l’imprimante.|  
|[CPageSetupDialog::GetPaperSize](#getpapersize)|Retourne la taille du papier de l’imprimante.|  
|[CPageSetupDialog::GetPortName](#getportname)|Retourne le nom de port de sortie.|  
|[CPageSetupDialog::OnDrawPage](#ondrawpage)|Appelée par l’infrastructure pour afficher l’image d’une page imprimée.|  
|[CPageSetupDialog::PreDrawPage](#predrawpage)|Appelé par l’infrastructure avant le rendu de l’image d’une page imprimée.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPageSetupDialog::m_psd](#m_psd)|Une structure utilisée pour personnaliser un `CPageSetupDialog` objet.|  
  
## <a name="remarks"></a>Remarques  
 Cette classe est conçue pour prendre la place de la boîte de dialogue Configuration de l’impression.  
  
 Pour utiliser un `CPageSetupDialog` d’objet, commencez par créer l’objet en utilisant la `CPageSetupDialog` constructeur. Une fois que la boîte de dialogue a été construite, vous pouvez définir ou modifier des valeurs dans le `m_psd` membre de données pour initialiser les valeurs des contrôles de la boîte de dialogue. Le [m_psd](#m_psd) structure est de type **PAGESETUPDLG**.  
  
 Après avoir initialisé les contrôles de boîte de dialogue, appelez le `DoModal` fonction membre pour afficher la boîte de dialogue et permettent aux utilisateurs de sélectionner des options d’impression. `DoModal`Retourne si l’utilisateur a sélectionné le OK ( **IDOK**) ou Annuler ( **IDCANCEL**) bouton.  
  
 Si `DoModal` retourne **IDOK**, vous pouvez utiliser plusieurs `CPageSetupDialog`de fonctions membres, ou accès le `m_psd` membre de données, pour récupérer les informations saisies par l’utilisateur.  
  
> [!NOTE]
>  Une fois la boîte de dialogue Mise en Page OLE est rejetée, toutes les modifications apportées par l’utilisateur ne seront pas enregistrées par l’infrastructure. C’est à l’application pour enregistrer des valeurs de cette boîte de dialogue à un emplacement permanent, telles que les membres de classe d’application ou de document de l’application.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CPageSetupDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdlgs.h  
  
##  <a name="a-namecpagesetupdialoga--cpagesetupdialogcpagesetupdialog"></a><a name="cpagesetupdialog"></a>CPageSetupDialog::CPageSetupDialog  
 Appelez cette fonction pour construire un `CPageSetupDialog` objet.  
  
```  
CPageSetupDialog(
    DWORD dwFlags = PSD_MARGINS | PSD_INWININIINTLMEASURE,  
    CWnd* pParentWnd = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Un ou plusieurs indicateurs que vous pouvez utiliser pour personnaliser les paramètres de la boîte de dialogue. Les valeurs peuvent être combinées à l’aide de l’opérateur de bits OR. Ces valeurs ont les significations suivantes :  
  
- **PSD_DEFAULTMINMARGINS** définit la largeur minimale autorisée pour les marges de page la même que les valeurs minimales de l’imprimante. Cet indicateur est ignoré si la **PSD_MARGINS** et **PSD_MINMARGINS** indicateurs sont également spécifiés.  
  
- **PSD_INWININIINTLMEASURE** non implémenté.  
  
- **PSD_MINMARGINS** , le système utilise les valeurs spécifiées dans le **rtMinMargin** membre en tant que la largeur minimale autorisée pour la gauche, haut, droite et les marges du bas. Le système empêche l’utilisateur d’entrer une largeur inférieure à la valeur minimale spécifiée. Si **PSD_MINMARGINS** n’est pas spécifié, le système définit la largeur minimale autorisée à celles autorisées par l’imprimante.  
  
- **PSD_MARGINS** Active la zone de contrôle de marge.  
  
- **PSD_INTHOUSANDTHSOFINCHES** les unités de la boîte de dialogue à mesurer 1/1000 de pouce.  
  
- **PSD_INHUNDREDTHSOFMILLIMETERS** les unités de la boîte de dialogue à mesurer 1/100 de millimètre.  
  
- **PSD_DISABLEMARGINS** désactive les contrôles de boîte de dialogue de marge.  
  
- **PSD_DISABLEPRINTER** désactive le bouton de l’imprimante.  
  
- **PSD_NOWARNING** évite que le message d’avertissement s’affiche lorsqu’il n’y a aucune imprimante par défaut.  
  
- **PSD_DISABLEORIENTATION** désactive le contrôle de boîte de dialogue de l’orientation de page.  
  
- **PSD_RETURNDEFAULT** entraîne `CPageSetupDialog` pour retourner [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) et [DEVNAMES](../../mfc/reference/devnames-structure.md) des structures qui sont initialisés pour l’imprimante par défaut sans afficher une boîte de dialogue. Il est supposé que les deux **hDevNames** et **hDevMode** sont **NULL**; sinon, la fonction renvoie une erreur. Si l’imprimante par défaut est pris en charge par un ancien pilote d’imprimante (antérieure à la version 3.0 pour Windows), uniquement **hDevNames** est retourné ; **hDevMode** is **NULL**.  
  
- **PSD_DISABLEPAPER** désactive le contrôle de sélection de document.  
  
- **PSD_SHOWHELP** , la boîte de dialogue Afficher le bouton aide. Le **hwndOwner** membre ne doit pas être **NULL** si cet indicateur est spécifié.  
  
- **PSD_ENABLEPAGESETUPHOOK** permet à la fonction de raccordement spécifiée dans **lpfnSetupHook**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATE** , le système d’exploitation créer la boîte de dialogue à l’aide de la boîte de dialogue modèle identifiée par **hInstance** et **lpSetupTemplateName**.  
  
- **PSD_ENABLEPAGESETUPTEMPLATEHANDLE** indique que **hInstance** identifie un bloc de données qui contient un modèle de boîte de dialogue préchargé. Le système ignore **lpSetupTemplateName** si cet indicateur est spécifié.  
  
- **PSD_ENABLEPAGEPAINTHOOK** permet à la fonction de raccordement spécifiée dans **lpfnPagePaintHook**.  
  
- **PSD_DISABLEPAGEPAINTING** désactive la zone de dessin de la boîte de dialogue.  
  
 `pParentWnd`  
 Pointeur vers la boîte de dialogue parente ou propriétaire.  
  
### <a name="remarks"></a>Remarques  
 Utilisez le [DoModal](../../mfc/reference/cdialog-class.md#domodal) fonction pour afficher la boîte de dialogue.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#94;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_1.cpp)]  
  
##  <a name="a-namecreateprinterdca--cpagesetupdialogcreateprinterdc"></a><a name="createprinterdc"></a>CPageSetupDialog::CreatePrinterDC  
 Crée un contexte de périphérique à partir de la [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) et [DEVNAMES](../../mfc/reference/devnames-structure.md) structures.  
  
```  
HDC CreatePrinterDC();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Handle vers le contexte de périphérique (DC) imprimante nouvellement créée.  
  
##  <a name="a-namedomodala--cpagesetupdialogdomodal"></a><a name="domodal"></a>CPageSetupDialog::DoModal  
 Appelez cette fonction pour afficher la boîte de dialogue Mise en Page OLE Windows courantes et permettent aux utilisateurs de sélectionner différentes options d’impression telles que les marges d’impression, la taille et l’orientation du papier et imprimante de destination.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 **IDOK** ou **IDCANCEL**. Si **IDCANCEL** est retourné, appelez Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) fonction pour déterminer si une erreur s’est produite.  
  
 **IDOK** et **IDCANCEL** sont des constantes qui indiquent si l’utilisateur a sélectionné le bouton OK ou annuler.  
  
### <a name="remarks"></a>Remarques  
 En outre, l’utilisateur peut accéder les options de configuration d’imprimante tels que l’emplacement réseau et des propriétés spécifiques à l’imprimante sélectionnée.  
  
 Si vous souhaitez initialiser les diverses options de la boîte de dialogue Mise en Page en définissant des membres de la `m_psd` structure, vous devez le faire avant d’appeler `DoModal`, et après la construction de l’objet de la boîte de dialogue. Après avoir appelé `DoModal`, appeler des fonctions à récupérer les paramètres ou les informations saisies par l’utilisateur dans la boîte de dialogue autres membres.  
  
 Si vous souhaitez propager les paramètres actuels entrés par l’utilisateur, effectuez un appel à [CWinApp::SelectPrinter](../../mfc/reference/cwinapp-class.md#selectprinter). Cette fonction utilise les informations de la `CPageSetupDialog` de l’objet et initialise et sélectionne une imprimante nouveau contrôleur de domaine avec les attributs corrects.  
  
 [!code-cpp[NVC_MFCDocView&#95;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_2.cpp)]  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="a-namegetdevicenamea--cpagesetupdialoggetdevicename"></a><a name="getdevicename"></a>CPageSetupDialog::GetDeviceName  
 Appelez cette fonction après `DoModal` pour récupérer le nom de l’imprimante sélectionnée.  
  
```  
CString GetDeviceName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom de périphérique utilisé par le **CPageSetupDialog** objet.  
  
##  <a name="a-namegetdevmodea--cpagesetupdialoggetdevmode"></a><a name="getdevmode"></a>CPageSetupDialog::GetDevMode  
 Appelez cette fonction après avoir appelé `DoModal` pour extraire des informations sur le contexte de périphérique de la `CPageSetupDialog` objet.  
  
```  
LPDEVMODE GetDevMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) structure de données qui contient des informations sur l’environnement d’un pilote d’impression et de l’initialisation du périphérique. Vous devez déverrouiller la mémoire consommée par cette structure avec Windows [GlobalUnlock](http://msdn.microsoft.com/library/windows/desktop/aa366595) (fonction), qui est décrite dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namegetdrivernamea--cpagesetupdialoggetdrivername"></a><a name="getdrivername"></a>CPageSetupDialog::GetDriverName  
 Appelez cette fonction après avoir appelé [DoModal](../../mfc/reference/cprintdialog-class.md#domodal) pour récupérer le nom du pilote de périphérique d’imprimante définis par le système.  
  
```  
CString GetDriverName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un `CString` en spécifiant le nom du pilote définies par le système.  
  
### <a name="remarks"></a>Notes  
 Utilisez un pointeur vers le `CString` objet retourné par `GetDriverName` comme valeur de `lpszDriverName` dans un appel à [CDC::CreateDC](../../mfc/reference/cdc-class.md#createdc).  
  
##  <a name="a-namegetmarginsa--cpagesetupdialoggetmargins"></a><a name="getmargins"></a>CPageSetupDialog::GetMargins  
 Appelez cette fonction après un appel à `DoModal` pour récupérer les marges du pilote de périphérique d’imprimante.  
  
```  
void GetMargins(
    LPRECT lpRectMargins,  
    LPRECT lpRectMinMargins) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *lpRectMargins*  
 Pointeur vers un [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) structure ou [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui décrit les marges d’impression pour l’imprimante sélectionnée (en pouces de 1/1000 ou 1/100 mm). Transmettez **NULL** pour ce paramètre, si vous n’êtes pas intéressé par ce rectangle.  
  
 *lpRectMinMargins*  
 Pointeur vers un `RECT` structure ou `CRect` objet qui décrit les marges d’impression minimales pour l’imprimante sélectionnée (en pouces de 1/1000 ou 1/100 mm). Transmettez **NULL** pour ce paramètre, si vous n’êtes pas intéressé par ce rectangle.  
  
##  <a name="a-namegetpapersizea--cpagesetupdialoggetpapersize"></a><a name="getpapersize"></a>CPageSetupDialog::GetPaperSize  
 Appelez cette fonction pour extraire la taille du papier sélectionné pour l’impression.  
  
```  
CSize GetPaperSize() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CSize](../../atl-mfc-shared/reference/csize-class.md) objet contenant la taille de la page (en pouces de 1/1000 ou 1/100 mm) sélectionnée pour l’impression.  
  
##  <a name="a-namegetportnamea--cpagesetupdialoggetportname"></a><a name="getportname"></a>CPageSetupDialog::GetPortName  
 Appelez cette fonction après avoir appelé `DoModal` pour récupérer le nom du port imprimante actuellement sélectionnée.  
  
```  
CString GetPortName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nom du port imprimante actuellement sélectionnée.  
  
##  <a name="a-namempsda--cpagesetupdialogmpsd"></a><a name="m_psd"></a>CPageSetupDialog::m_psd  
 Une structure de type **PAGESETUPDLG**, dont les membres stockent les caractéristiques de l’objet de la boîte de dialogue.  
  
```  
PAGESETUPDLG m_psd;  
```  
  
### <a name="remarks"></a>Notes  
 Après avoir construit un `CPageSetupDialog` de l’objet, vous pouvez utiliser `m_psd` pour définir les divers aspects de la boîte de dialogue avant d’appeler le `DoModal` fonction membre.  
  
 Si vous modifiez le `m_psd` membre de données directement, vous devez remplacer un comportement par défaut.  
  
 Pour plus d’informations sur la [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842) de la structure, consultez la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Consultez l’exemple de [CPageSetupDialog::CPageSetupDialog](#cpagesetupdialog).  
  
##  <a name="a-nameondrawpagea--cpagesetupdialogondrawpage"></a><a name="ondrawpage"></a>CPageSetupDialog::OnDrawPage  
 Appelé par l’infrastructure pour dessiner l’image d’une page imprimée.  
  
```  
virtual UINT OnDrawPage(
    CDC* pDC,  
    UINT nMessage,  
    LPRECT lpRect);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointeur vers le contexte de l’imprimante.  
  
 `nMessage`  
 Spécifie un message indiquant la zone de la page en cours de saisie. Il peut s'agir d'une des valeurs suivantes :  
  
- **WM_PSD_FULLPAGERECT** la zone de page entière.  
  
- **WM_PSD_MINMARGINRECT** marges minimales en cours.  
  
- **WM_PSD_MARGINRECT** marges.  
  
- **WM_PSD_GREEKTEXTRECT** contenu de la page.  
  
- **WM_PSD_ENVSTAMPRECT** zone réservée à une représentation sous forme de timbre.  
  
- **WM_PSD_YAFULLPAGERECT** zone pour obtenir une représentation de l’adresse de retour. Cette zone s’étend sur les bords de la zone de page d’exemple.  
  
 `lpRect`  
 Pointeur vers un [CRect](../../atl-mfc-shared/reference/crect-class.md) ou [RECT](https://www.microsoftonedoc.com/#/organizations/e6f6a65cf14f462597b64ac058dbe1d0/projects/3fedad16-eaf1-41a6-8f96-0c1949c68f32/containers/a3daf831-1c5f-4bbe-964d-503870caf874/tocpaths/18113766-3975-4369-bc07-92e34cba712e/locales/en-us) objet contenant les coordonnées de la zone de dessin.  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro si géré ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette image est ensuite affichée dans le cadre de la boîte de dialogue Mise en Page OLE courante. L’implémentation par défaut Dessine une image d’une page de texte.  
  
 Remplacez cette fonction pour personnaliser le dessin d’une zone spécifique de l’image ou l’image entière. Cela, utilisez un `switch` instruction avec **cas** instructions vérifiant la valeur de `nMessage`. Par exemple, pour personnaliser le rendu du contenu de l’image de page, vous pouvez utiliser l’exemple de code suivant :  
  
 [!code-cpp[NVC_MFCDocView&#96;](../../mfc/codesnippet/cpp/cpagesetupdialog-class_3.cpp)]  
  
 Notez que vous ne devez pas gérer tous les cas de `nMessage`. Vous pouvez choisir de gérer un composant de l’image, plusieurs composants de l’image, ou l’ensemble du domaine.  
  
##  <a name="a-namepredrawpagea--cpagesetupdialogpredrawpage"></a><a name="predrawpage"></a>CPageSetupDialog::PreDrawPage  
 Appelé par l’infrastructure avant de dessiner l’image d’écran d’une page imprimée.  
  
```  
virtual UINT PreDrawPage(
    WORD wPaper,  
    WORD wFlags,  
    LPPAGESETUPDLG pPSD);
```  
  
### <a name="parameters"></a>Paramètres  
 *wPaper*  
 Spécifie une valeur qui indique le format du papier. Cette valeur peut être une de le **DMPAPER_** les valeurs répertoriées dans la description de la [DEVMODE](http://msdn.microsoft.com/library/windows/desktop/dd183565) structure.  
  
 `wFlags`  
 Indique l’orientation du papier ou d’enveloppe, et si l’imprimante est matricielle ou l’appareil HPPCL (Hewlett Packard Printer Control Language). Ce paramètre peut prendre l'une des valeurs suivantes :  
  
-   0 x&001; papier en mode paysage (matricielle)  
  
-   0 x&003; papier en mode paysage (HPPCL)  
  
-   0x005 papier en mode portrait (matricielle)  
  
-   0x007 papier en mode portrait (HPPCL)  
  
-   0x00b enveloppe en mode paysage (HPPCL)  
  
-   0x00d enveloppe en mode portrait (matricielle)  
  
-   0x019 enveloppe en mode paysage (matricielle)  
  
-   0x01f enveloppe en mode portrait (matricielle)  
  
 `pPSD`  
 Pointeur vers un **PAGESETUPDLG** structure. Pour plus d’informations sur [PAGESETUPDLG](http://msdn.microsoft.com/library/windows/desktop/ms646842), consultez le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="return-value"></a>Valeur de retour  
 Valeur différente de zéro si géré ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction pour personnaliser le dessin de l’image. Si vous remplacez cette fonction et retourner **TRUE**, vous devez dessiner l’image entière. Si vous remplacez cette fonction et retourner **FALSE**, l’image entière par défaut est dessiné par le framework.  
  
## <a name="see-also"></a>Voir aussi  
 [Exemple MFC WORDPAD](../../visual-cpp-samples.md)   
 [CCommonDialog (classe)](../../mfc/reference/ccommondialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




