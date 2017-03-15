---
title: CPropertySheet (classe) | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CPropertySheet
dev_langs:
- C++
helpviewer_keywords:
- dialog boxes, tabs
- CPropertySheet class
- property sheets, CPropertySheet class
- tab dialog boxes
ms.assetid: 8461ccff-d14f-46e0-a746-42ad642ef94e
caps.latest.revision: 30
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
ms.openlocfilehash: 41ad7b598016b1fa04aa7ca63575f853195b5359
ms.lasthandoff: 02/24/2017

---
# <a name="cpropertysheet-class"></a>CPropertySheet (classe)
Représente des feuilles de propriétés, également appelées boîtes de dialogue à onglets.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CPropertySheet : public CWnd  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPropertySheet::CPropertySheet](#cpropertysheet)|Construit un objet `CPropertySheet`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CPropertySheet::AddPage](#addpage)|Ajoute une page à la feuille de propriétés.|  
|[CPropertySheet::Construct](#construct)|Construit un objet `CPropertySheet`.|  
|[CPropertySheet::Create](#create)|Affiche une feuille de propriétés non modale.|  
|[CPropertySheet::DoModal](#domodal)|Affiche une feuille de propriétés modale.|  
|[CPropertySheet::EnableStackedTabs](#enablestackedtabs)|Indique si la feuille de propriétés utilise des onglets empilées ou en mode de défilement.|  
|[CPropertySheet::EndDialog](#enddialog)|Met fin à la feuille de propriétés.|  
|[CPropertySheet::GetActiveIndex](#getactiveindex)|Récupère l’index de la page active de la feuille de propriétés.|  
|[CPropertySheet::GetActivePage](#getactivepage)|Retourne l’objet de la page active.|  
|[CPropertySheet::GetPage](#getpage)|Récupère un pointeur vers la page spécifiée.|  
|[CPropertySheet::GetPageCount](#getpagecount)|Récupère le nombre de pages dans la feuille de propriétés.|  
|[CPropertySheet::GetPageIndex](#getpageindex)|Récupère l’index de la page spécifiée de la feuille de propriétés.|  
|[CPropertySheet::GetTabControl](#gettabcontrol)|Récupère un pointeur vers un contrôle onglet.|  
|[CPropertySheet::MapDialogRect](#mapdialogrect)|Convertit les unités de boîte de dialogue d’un rectangle en unités d’écran.|  
|[CPropertySheet::OnInitDialog](#oninitdialog)|Substituez pour augmenter l’initialisation de feuille de propriétés.|  
|[CPropertySheet::PressButton](#pressbutton)|Simule le choix du bouton spécifié dans une feuille de propriétés.|  
|[CPropertySheet::RemovePage](#removepage)|Supprime une page de la feuille de propriétés.|  
|[CPropertySheet::SetActivePage](#setactivepage)|Définit par programmation l’objet de la page active.|  
|[CPropertySheet::SetFinishText](#setfinishtext)|Définit le texte pour le bouton Terminer.|  
|[CPropertySheet::SetTitle](#settitle)|Définit la légende de la feuille de propriétés.|  
|[CPropertySheet::SetWizardButtons](#setwizardbuttons)|Active les boutons de l’Assistant.|  
|[Fonction CPropertySheet::SetWizardMode](#setwizardmode)|Active le mode de l’Assistant.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CPropertySheet::m_psh](#m_psh)|Les fenêtres [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) structure. Fournit l’accès aux paramètres de feuille de propriétés de base.|  
  
## <a name="remarks"></a>Remarques  
 Une feuille de propriétés se compose d’un `CPropertySheet` objet et un ou plusieurs [CPropertyPage](../../mfc/reference/cpropertypage-class.md) objets. L’infrastructure affiche une feuille de propriétés sous la forme d’une fenêtre avec un ensemble d’index de l’onglet et une zone qui contient la page sélectionnée. L’utilisateur navigue vers une page spécifique à l’aide de l’onglet approprié.  
  
 `CPropertySheet`prend en charge la structure [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546) structure introduite dans [!INCLUDE[Win98](../../mfc/reference/includes/win98_md.md)] et Windows NT 2000. La structure contient des indicateurs supplémentaires et les membres qui prennent en charge à l’aide d’une image bitmap d’arrière-plan « filigrane ».  
  
 Pour afficher ces nouvelles images automatiquement dans votre objet de feuille de propriétés, passer les valeurs valides pour les images bitmap et de palette dans l’appel à [CPropertySheet::Construct](#construct) ou [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Même si `CPropertySheet` n’est pas dérivé [CDialog](../../mfc/reference/cdialog-class.md), gérer un `CPropertySheet` objet est similaire à la gestion un `CDialog` objet. Par exemple, la création d’une feuille de propriétés requiert la construction de deux parties : appeler le constructeur, puis appelez [DoModal](#domodal) d’une feuille de propriétés modale ou [créer](#create) d’une feuille de propriétés non modale. `CPropertySheet`propose deux types de constructeurs : [CPropertySheet::Construct](#construct) et [CPropertySheet::CPropertySheet](#cpropertysheet).  
  
 Lorsque vous construisez un `CPropertySheet` objet certaines [Styles de fenêtre](../../mfc/reference/window-styles.md) peuvent provoquer une exception de première chance de se produire. Ainsi, à partir du système essaie de modifier le style de la feuille de propriétés avant la création de la feuille. Pour éviter cette exception, assurez-vous que vous définissez les styles suivants lorsque vous créez votre `CPropertySheet`:  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Les styles suivants sont facultatifs et ne provoquent pas l’exception de première chance :  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 N’importe quel autre `Window Styles` sont interdites et vous ne devez pas activer les.  
  
 Échanger des données entre un `CPropertySheet` objet et un objet externe est similaire à échanger des données avec un `CDialog` objet. La différence importante est que les paramètres d’une feuille de propriétés sont généralement des variables de membre de la `CPropertyPage` objets plutôt que du `CPropertySheet` objet lui-même.  
  
 Vous pouvez créer un type de boîte de dialogue onglet appelé un Assistant qui se compose d’une feuille de propriétés avec une séquence de pages de propriétés qui guide l’utilisateur à travers les étapes d’une opération, telles que la configuration d’un périphérique ou un bulletin d’informations. Dans une boîte de dialogue Assistant type onglet, les pages de propriétés n’ont pas d’onglets, et uniquement une page de propriété est visible à la fois. Aussi, au lieu de **OK** et **appliquer maintenant** boutons, une boîte de dialogue type d’Assistant onglet a un **retour** bouton, un **suivant** ou **Terminer** bouton, un **Annuler** bouton et un **aide** bouton.  
  
 Pour créer une boîte de dialogue du type de l’Assistant, suivez les mêmes étapes que vous suivez pour créer une feuille de propriétés standard, mais appelle [SetWizardMode](#setwizardmode) avant d’appeler [DoModal](#domodal). Pour activer les boutons de l’Assistant, appelez [SetWizardButtons](#setwizardbuttons), à l’aide des indicateurs pour personnaliser leur fonctionnement et son apparence. Pour activer la **Terminer** bouton, appelez [SetFinishText](#setfinishtext) une fois que l’utilisateur a effectué l’action sur la dernière page de l’Assistant.  
  
 Pour plus d’informations sur l’utilisation de `CPropertySheet` , consultez l’article [feuilles de propriétés et Pages de propriétés](../../mfc/property-sheets-and-property-pages-in-mfc.md). Également, consultez l’article Q146916 de la Base de connaissances : comment faire : créer un objet de CPropertySheet non modal avec des boutons Standard et que l’article Q300606 : comment faire : concevoir une feuille de propriétés MFC redimensionnable.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CPropertySheet`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdlgs.h  
  
##  <a name="a-nameaddpagea--cpropertysheetaddpage"></a><a name="addpage"></a>CPropertySheet::AddPage  
 Ajoute la page fournie avec la plus à droite de l’onglet de la feuille de propriétés.  
  
```  
void AddPage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Paramètres  
 `pPage`  
 Pointe vers la page à ajouter à la feuille de propriétés. Ne peut pas être **NULL**.  
  
### <a name="remarks"></a>Remarques  
 Ajouter des pages à la feuille de propriétés dans l’ordre de gauche à droite que vous souhaitez qu’ils apparaissent.  
  
 `AddPage`Ajoute le [CPropertyPage](../../mfc/reference/cpropertypage-class.md#cpropertypage) de l’objet à le `CPropertySheet` objet de la liste des pages, mais ne crée pas réellement la fenêtre de la page. Le framework diffère la création de la fenêtre de la page jusqu'à ce que l’utilisateur sélectionne cette page.  
  
 Lorsque vous ajoutez une page de propriétés à l’aide de `AddPage`, le `CPropertySheet` est le parent de la `CPropertyPage`. Pour accéder à la feuille de propriétés à partir de la page de propriétés, appelez [CWnd::GetParent](../../mfc/reference/cwnd-class.md#getparent).  
  
 Il n’est pas nécessaire d’attendre jusqu'à ce que la création de la fenêtre de feuille de propriétés pour appeler `AddPage`. En général, vous appelez `AddPage` avant d’appeler [DoModal](#domodal) ou [créer](#create).  
  
 Si vous appelez `AddPage` après avoir affiché la page de propriétés, la ligne d’onglets reflète la page nouvellement ajoutée.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#129;](../../mfc/codesnippet/cpp/cpropertysheet-class_1.cpp)]  
  
##  <a name="a-nameconstructa--cpropertysheetconstruct"></a><a name="construct"></a>CPropertySheet::Construct  
 Construit un objet `CPropertySheet`.  
  
```  
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
void Construct(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
void Construct(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDCaption`  
 ID de la légende à utiliser pour la feuille de propriétés.  
  
 `pParentWnd`  
 Pointeur vers la fenêtre parente de la feuille de propriétés. Si **NULL**, la fenêtre parente est la fenêtre principale de l’application.  
  
 `iSelectPage`  
 L’index de la page qui sera initialement le premier. Valeur par défaut est la première page ajoutée à la feuille.  
  
 `pszCaption`  
 Pointeur vers une chaîne qui contient la légende à utiliser pour la feuille de propriétés. Ne peut pas être **NULL**.  
  
 `hbmWatermark`  
 Handle de bitmap filigrane de la page de propriétés.  
  
 `hpalWatermark`  
 Handle vers la palette de la bitmap de filigrane et/ou le bitmap de l’en-tête.  
  
 `hbmHeader`  
 Handle de la bitmap de l’en-tête de la page de propriétés.  
  
### <a name="remarks"></a>Remarques  
 Appelez cette fonction membre si un des constructeurs de classe n’a pas déjà été appelé. Par exemple, appeler `Construct` lorsque vous déclarez ou allouer des tableaux de `CPropertySheet` objets. Dans le cas de tableaux, vous devez appeler `Construct` pour chaque membre du tableau.  
  
 Pour afficher la feuille de propriétés, appelez [DoModal](#domodal) ou [créer](#create). La chaîne contenue dans le premier paramètre est placée dans la barre de légende de la feuille de propriétés.  
  
 Vous pouvez afficher des images en filigrane et/ou d’en-tête automatiquement si vous utilisez les troisièmes ou quatrième prototypes de `Construct`, répertoriés ci-dessus et que vous passez des valeurs valides le `hbmWatermark`, `hpalWatermark`, et/ou `hbmHeader` paramètres.  
  
### <a name="example"></a>Exemple  
 L’exemple suivant montre dans quelles circonstances vous appelleriez `Construct`.  
  
 [!code-cpp[NVC_MFCDocView&#130;](../../mfc/codesnippet/cpp/cpropertysheet-class_2.cpp)]  
  
##  <a name="a-namecpropertysheeta--cpropertysheetcpropertysheet"></a><a name="cpropertysheet"></a>CPropertySheet::CPropertySheet  
 Construit un objet `CPropertySheet`.  
  
```  
CPropertySheet();

 
explicit CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
explicit CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd = NULL,  
    UINT iSelectPage = 0);

 
CPropertySheet(
    UINT nIDCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);

 
CPropertySheet(
    LPCTSTR pszCaption,  
    CWnd* pParentWnd,  
    UINT iSelectPage,  
    HBITMAP hbmWatermark,  
    HPALETTE hpalWatermark = NULL,  
    HBITMAP hbmHeader = NULL);
```  
  
### <a name="parameters"></a>Paramètres  
 `nIDCaption`  
 ID de la légende à utiliser pour la feuille de propriétés.  
  
 `pParentWnd`  
 Pointe vers la fenêtre parente de la feuille de propriétés. Si **NULL**, la fenêtre parente est la fenêtre principale de l’application.  
  
 `iSelectPage`  
 L’index de la page qui sera initialement le premier. Valeur par défaut est la première page ajoutée à la feuille.  
  
 `pszCaption`  
 Pointe vers une chaîne qui contient la légende à utiliser pour la feuille de propriétés. Ne peut pas être **NULL**.  
  
 `hbmWatermark`  
 Handle de l’image bitmap d’arrière-plan de la feuille de propriétés.  
  
 `hpalWatermark`  
 Un handle vers la palette de la bitmap de filigrane et/ou le bitmap de l’en-tête.  
  
 `hbmHeader`  
 Handle vers le bitmap de l’en-tête de la page de propriétés.  
  
### <a name="remarks"></a>Notes  
 Pour afficher la feuille de propriétés, appelez [DoModal](#domodal) ou [créer](#create). La chaîne contenue dans le premier paramètre est placée dans la barre de légende de la feuille de propriétés.  
  
 Si vous avez plusieurs paramètres (par exemple, si vous utilisez un tableau), utilisez [construire](#construct) au lieu de `CPropertySheet`.  
  
 Vous pouvez afficher des images en filigrane et/ou d’en-tête automatiquement si vous utilisez les troisièmes ou quatrième prototypes de `CPropertySheet`, ci-dessus, et que vous passez des valeurs valides le `hbmWatermark`, `hpalWatermark`, et/ou `hbmHeader` paramètres.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#131;](../../mfc/codesnippet/cpp/cpropertysheet-class_3.cpp)]  
  
##  <a name="a-namecreatea--cpropertysheetcreate"></a><a name="create"></a>CPropertySheet::Create  
 Affiche une feuille de propriétés non modale.  
  
```  
virtual BOOL Create(CWnd* pParentWnd = NULL,
    DWORD dwStyle = (DWORD)–1,
    DWORD dwExStyle = 0);  
```  
  
### <a name="parameters"></a>Paramètres  
 `pParentWnd`  
 Pointe vers la fenêtre parente. Si **NULL**, le bureau est le parent.  
  
 `dwStyle`  
 Styles de fenêtre pour la feuille de propriétés. Pour obtenir une liste complète des styles disponibles, consultez la page [Styles de fenêtre](../../mfc/reference/window-styles.md).  
  
 `dwExStyle`  
 Styles de fenêtre étendus pour la feuille de propriétés. Pour obtenir une liste complète des styles disponibles, consultez la page [Styles de fenêtre étendus](../../mfc/reference/extended-window-styles.md)  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la feuille de propriétés est créée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 L’appel à **créer** peut se trouver dans le constructeur, ou vous pouvez l’appeler après que le constructeur est appelé.  
  
 Le style par défaut, exprimé en passant la valeur -1 comme `dwStyle`, est en fait **WS_SYSMENU |** `WS_POPUP`**| WS_CAPTION | DS_MODALFRAME | DS_CONTEXTHELP | WS_VISIBLE**. La valeur par défaut étendu de style de la fenêtre, exprimé en passant 0 comme `dwExStyle`, est en fait **WS_EX_DLGMODALFRAME**.  
  
 Le **créer** fonction membre retourne immédiatement après la création de la feuille de propriétés. Pour détruire la feuille de propriétés, appelez [CWnd::DestroyWindow](../../mfc/reference/cwnd-class.md#destroywindow).  
  
 Feuilles de propriétés non modale affichées par un appel à **créer** n’ont pas de boutons OK, Annuler, appliquer et aide tel que des feuilles de propriétés modale. Boutons de votre choix doit être créé par l’utilisateur.  
  
 Pour afficher une feuille de propriétés modale, appelez [DoModal](#domodal) à la place.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#132;](../../mfc/codesnippet/cpp/cpropertysheet-class_4.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#133;](../../mfc/codesnippet/cpp/cpropertysheet-class_5.cpp)]  
  
##  <a name="a-namedomodala--cpropertysheetdomodal"></a><a name="domodal"></a>CPropertySheet::DoModal  
 Affiche une feuille de propriétés modale.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 `IDOK`ou `IDCANCEL` si la fonction a réussi ; sinon, 0 ou de-1. Si la feuille de propriétés a été définie comme un Assistant (voir [SetWizardMode](#setwizardmode)), `DoModal` retourne `ID_WIZFINISH` ou `IDCANCEL`.  
  
### <a name="remarks"></a>Notes  
 La valeur de retour correspond à l’ID du contrôle qui a fermé la feuille de propriétés. Après le retour de cette fonction, les fenêtres correspondant à la feuille de propriétés et toutes les pages seront détruits. Les objets eux-mêmes existe toujours. En règle générale, vous allez récupérer des données à partir de la [CPropertyPage](../../mfc/reference/cpropertypage-class.md) objets après `DoModal` renvoie `IDOK`.  
  
 Pour afficher une feuille de propriétés non modale, appelez [créer](#create) à la place.  
  
 Lorsqu’une page de propriétés est créée à partir de la ressource de boîte de dialogue correspondante, il peut provoquer une exception de première chance. Cela résulte de la page de propriétés modifier le style de la ressource de boîte de dialogue du style requis avant la création de la page. Étant donné que les ressources sont généralement en lecture seule, cela provoque une exception. Le système gère l’exception et effectue une copie de la ressource modifiée. L’exception de première chance peut donc être ignorée.  
  
> [!NOTE]
>  Cette exception doit être gérée par le système d’exploitation si vous compilez avec le modèle de gestion des exceptions asynchrones. Pour plus d’informations sur les modèles de gestion des exceptions, consultez [/EH (Exception Handling Model)](../../build/reference/eh-exception-handling-model.md). Dans ce cas, n’imbriquez pas les appels à `CPropertySheet::DoModal` avec un bloc try-catch C++ dont catch gère toutes les exceptions, par exemple, `catch (...)`. Ce bloc permet de gérer l’exception destinée au système d’exploitation et cause un comportement imprévisible. Toutefois, vous pouvez utiliser en toute sécurité C++ exceptions avec des types d’exceptions spécifiques ou de la gestion structurée des exceptions dans lequel l’exception de Violation d’accès est passée par le biais du système d’exploitation.  
  
 Pour éviter la génération de cette exception de première chance, vous pouvez manuellement garantit que la feuille de propriétés dispose de la bonne [Styles de fenêtre](../../mfc/reference/window-styles.md). Vous devez définir les styles d’une feuille de propriétés suivants :  
  
-   DS_3DLOOK  
  
-   DS_CONTROL  
  
-   WS_CHILD  
  
-   WS_TABSTOP  
  
 Vous pouvez utiliser les styles suivants facultatif sans provoquer une exception de première chance :  
  
-   DS_SHELLFONT  
  
-   DS_LOCALEDIT  
  
-   WS_CLIPCHILDREN  
  
 Désactivez tous les autres styles de Windows, car ils ne sont pas compatibles avec les feuilles de propriétés. Ce Conseil ne s’applique pas aux styles étendus. Définir ces styles standards correctement garantit que la feuille de propriétés ne doit pas être modifié et éviter de générer l’exception de première chance.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPropertySheet::AddPage](#addpage).  
  
##  <a name="a-nameenablestackedtabsa--cpropertysheetenablestackedtabs"></a><a name="enablestackedtabs"></a>CPropertySheet::EnableStackedTabs  
 Indique si les lignes d’onglets dans une feuille de propriétés de la pile.  
  
```  
void EnableStackedTabs(BOOL bStacked);
```  
  
### <a name="parameters"></a>Paramètres  
 `bStacked`  
 Indique si les onglets empilées sont activés dans la feuille de propriétés. Désactiver les lignes empilées de balises en définissant `bStacked` à **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, si une feuille de propriétés compte plus d’onglets que ceux qui tiennent sur une seule ligne dans la largeur de la feuille de propriétés, les onglets seront empilent sur plusieurs lignes. Pour utiliser les onglets en mode de défilement au lieu des onglets de superposition, appelez `EnableStackedTabs` avec `bStacked` la valeur **FALSE** avant d’appeler [DoModal](#domodal) ou [créer](#create).  
  
 Vous devez appeler `EnableStackedTabs` lorsque vous créez une modale ou une feuille de propriétés non modale. Pour incorporer ce style dans un `CPropertySheet`-classe dérivée, écrivez un gestionnaire de messages pour `WM_CREATE`. Dans la version substituée de [CWnd::OnCreate](../../mfc/reference/cwnd-class.md#oncreate), appelez **EnableStackedTabs (FALSE)** avant d’appeler l’implémentation de classe de base.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#134;](../../mfc/codesnippet/cpp/cpropertysheet-class_6.cpp)]  
  
##  <a name="a-nameenddialoga--cpropertysheetenddialog"></a><a name="enddialog"></a>CPropertySheet::EndDialog  
 Met fin à la feuille de propriétés.  
  
```  
void EndDialog(int nEndID);
```  
  
### <a name="parameters"></a>Paramètres  
 *nEndID*  
 Identificateur à utiliser comme valeur de retour de la feuille de propriétés.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est appelée par l’infrastructure lorsque l’OK, annuler ou le bouton Fermer est enfoncé. Appel de cette fonction membre, si un événement produit, qui doit fermer la feuille de propriétés.  
  
 Cette fonction membre est utilisée uniquement avec une boîte de dialogue modale.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPropertySheet::PressButton](#pressbutton).  
  
##  <a name="a-namegetactiveindexa--cpropertysheetgetactiveindex"></a><a name="getactiveindex"></a>CPropertySheet::GetActiveIndex  
 Obtient le numéro d’index de la page active de la fenêtre de feuille de propriétés, puis utilise le numéro d’index retourné comme paramètre pour `GetPage`.  
  
```  
int GetActiveIndex() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le numéro d’index de la page active.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="a-namegetactivepagea--cpropertysheetgetactivepage"></a><a name="getactivepage"></a>CPropertySheet::GetActivePage  
 Récupère la page active de la fenêtre de feuille de propriétés.  
  
```  
CPropertyPage* GetActivePage() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers la page active.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette fonction membre pour effectuer une action sur la page active.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#135;](../../mfc/codesnippet/cpp/cpropertysheet-class_7.cpp)]  
  
##  <a name="a-namegetpagea--cpropertysheetgetpage"></a><a name="getpage"></a>CPropertySheet::GetPage  
 Retourne un pointeur vers la page spécifiée dans cette feuille de propriétés.  
  
```  
CPropertyPage* GetPage(int nPage) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nPage`  
 Index de la page souhaitée, commençant à 0. Doit comprendre entre 0 et inférieur au nombre de pages dans la feuille de propriétés, incluse.  
  
### <a name="return-value"></a>Valeur de retour  
 Le pointeur vers la page correspondant à le `nPage` paramètre.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="a-namegetpagecounta--cpropertysheetgetpagecount"></a><a name="getpagecount"></a>CPropertySheet::GetPageCount  
 Détermine le nombre de pages actuellement dans la feuille de propriétés.  
  
```  
int GetPageCount() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le nombre de pages dans la feuille de propriétés.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPropertyPage::OnWizardFinish](../../mfc/reference/cpropertypage-class.md#onwizardfinish).  
  
##  <a name="a-namegetpageindexa--cpropertysheetgetpageindex"></a><a name="getpageindex"></a>CPropertySheet::GetPageIndex  
 Récupère le numéro d’index de la page spécifiée dans la feuille de propriétés.  
  
```  
int GetPageIndex(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Paramètres  
 `pPage`  
 Pointe vers la page avec l’index doit être recherché. Ne peut pas être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Le numéro d’index d’une page.  
  
### <a name="remarks"></a>Remarques  
 Par exemple, vous utiliseriez `GetPageIndex` pour obtenir l’index de page afin d’utiliser [SetActivePage](#setactivepage) ou [GetPage](#getpage).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="a-namegettabcontrola--cpropertysheetgettabcontrol"></a><a name="gettabcontrol"></a>CPropertySheet::GetTabControl  
 Récupère un pointeur vers un contrôle onglet pour effectuer une action spécifique pour le contrôle d’onglet (autrement dit, d’utiliser les API de [CTabCtrl](../../mfc/reference/ctabctrl-class.md)).  
  
```  
CTabCtrl* GetTabControl() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un contrôle onglet.  
  
### <a name="remarks"></a>Notes  
 Par exemple, appelez cette fonction membre si vous souhaitez ajouter des bitmaps pour chacun des onglets lors de l’initialisation.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#136;](../../mfc/codesnippet/cpp/cpropertysheet-class_8.cpp)]  
  
##  <a name="a-namempsha--cpropertysheetmpsh"></a><a name="m_psh"></a>CPropertySheet::m_psh  
 Une structure dont les membres stockent les caractéristiques de [PROPSHEETHEADER](http://msdn.microsoft.com/library/windows/desktop/bb774546).  
  
### <a name="remarks"></a>Notes  
 Cette structure permet d’initialiser l’apparence de la feuille de propriétés une fois qu’il est construit mais avant qu’il est affiché avec le [DoModal](#domodal) fonction membre. Par exemple, définissez la `dwSize` membre `m_psh` à la taille souhaitée pour que la feuille de propriétés.  
  
 Pour plus d’informations sur cette structure, y compris une liste de ses membres, consultez la page **PROPSHEETHEADER** dans les [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#143;](../../mfc/codesnippet/cpp/cpropertysheet-class_9.cpp)]  
  
##  <a name="a-namemapdialogrecta--cpropertysheetmapdialogrect"></a><a name="mapdialogrect"></a>CPropertySheet::MapDialogRect  
 Convertit les unités de boîte de dialogue d’un rectangle en unités d’écran.  
  
```  
void MapDialogRect(LPRECT lpRect) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `lpRect`  
 Pointe vers une [RECT](http://msdn.microsoft.com/library/windows/desktop/dd162897) structure ou [CRect](../../atl-mfc-shared/reference/crect-class.md) objet qui contient la boîte de dialogue coordonnées à convertir.  
  
### <a name="remarks"></a>Remarques  
 Unités de boîte de dialogue sont exprimées dans l’unité de base de la boîte de dialogue actuelle dérivée de la largeur moyenne et la hauteur des caractères de la police utilisée pour le texte de la boîte de dialogue. Une unité horizontale est un quart de l’unité de largeur de la base de la boîte de dialogue et une unité verticale est un huitième de l’unité de base hauteur de la boîte de dialogue.  
  
 Le [GetDialogBaseUnits](http://msdn.microsoft.com/library/windows/desktop/ms645475) fonction Windows retourne des informations sur la taille de la police système, mais vous pouvez spécifier une police différente pour chaque feuille de propriétés si vous utilisez la **DS_SETFONT** style dans le fichier de définition de la ressource. Le [MapDialogRect](http://msdn.microsoft.com/library/windows/desktop/ms645502) fonction Windows, décrite dans la [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)], utilise la police appropriée pour cette boîte de dialogue.  
  
 Le `MapDialogRect` fonction membre remplace les unités de boîte de dialogue de `lpRect` avec afin que le rectangle peut être utilisé pour créer une boîte de dialogue ou la position d’un contrôle dans une zone de l’écran unités (pixels).  
  
##  <a name="a-nameoninitdialoga--cpropertysheetoninitdialog"></a><a name="oninitdialog"></a>CPropertySheet::OnInitDialog  
 Les remplacements pour augmenter l’initialisation de feuille de propriétés.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Spécifie si l’application a défini le focus d’entrée à l’un des contrôles dans la feuille de propriétés. Si **OnInitDialog** retourne zéro, Windows définit le focus d’entrée sur le premier contrôle dans la feuille de propriétés. L’application peut retourner 0 uniquement si elle a explicitement définir le focus d’entrée à l’un des contrôles dans la feuille de propriétés.  
  
### <a name="remarks"></a>Remarques  
 Cette fonction membre est appelée en réponse à la **WM_INITDIALOG** message. Ce message est envoyé à la feuille de propriétés lors de la [créer](#create) ou [DoModal](#domodal) appels, qui se produisent immédiatement avant l’affichage de la feuille de propriétés.  
  
 Remplacez cette fonction membre, si vous avez besoin exécuter un traitement spécial lors de l’initialisation de la feuille de propriétés. Dans la version substituée, appelez d’abord la classe de base `OnInitDialog` mais ne pas tenir compte de sa valeur de retour. Vous allez normalement retourner **TRUE** à partir de votre fonction membre substitué.  
  
 Il est inutile une entrée de table des messages pour cette fonction membre.  
  
##  <a name="a-namepressbuttona--cpropertysheetpressbutton"></a><a name="pressbutton"></a>CPropertySheet::PressButton  
 Simule le choix du bouton spécifié dans une feuille de propriétés.  
  
```  
void PressButton(int nButton);
```  
  
### <a name="parameters"></a>Paramètres  
 `nButton`  
 nButton : identifie le bouton. Ce paramètre peut être une des valeurs suivantes :  
  
- **PSBTN_BACK** choisit le bouton retour.  
  
- **PSBTN_NEXT** choisit le bouton suivant.  
  
- **PSBTN_FINISH** choisit le bouton Terminer.  
  
- **PSBTN_OK** choisit le bouton OK.  
  
- **PSBTN_APPLYNOW** choisit le bouton Appliquer.  
  
- **PSBTN_CANCEL** choisit le bouton Annuler.  
  
- **PSBTN_HELP** choisit le bouton aide.  
  
### <a name="remarks"></a>Remarques  
 Consultez la page [PSM_PRESSBUTTON](http://msdn.microsoft.com/library/windows/desktop/bb774597) pour plus d’informations sur le message Pressbutton du Kit de développement logiciel Windows.  
  
 Un appel à `PressButton` n’envoie pas le [PSN_APPLY](http://msdn.microsoft.com/library/windows/desktop/bb774552) notification à partir d’une page de propriétés de l’infrastructure. Pour envoyer cette notification, appelez [CPropertyPage::OnOK](../../mfc/reference/cpropertypage-class.md#onok).  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#137;](../../mfc/codesnippet/cpp/cpropertysheet-class_10.cpp)]  
  
##  <a name="a-nameremovepagea--cpropertysheetremovepage"></a><a name="removepage"></a>CPropertySheet::RemovePage  
 Supprime une page de la feuille de propriétés et détruit la fenêtre associée.  
  
```  
void RemovePage(CPropertyPage* pPage);  
void RemovePage(int nPage);
```  
  
### <a name="parameters"></a>Paramètres  
 `pPage`  
 Pointe vers la page à supprimer de la feuille de propriétés. Ne peut pas être `NULL`.  
  
 `nPage`  
 Index de la page à supprimer. Doit comprendre entre 0 et inférieur au nombre de pages dans la feuille de propriétés, incluse.  
  
### <a name="remarks"></a>Remarques  
 Le [CPropertyPage](../../mfc/reference/cpropertypage-class.md) objet lui-même n’est pas détruit tant que le propriétaire de la `CPropertySheet` fenêtre est fermée.  
  
##  <a name="a-namesetactivepagea--cpropertysheetsetactivepage"></a><a name="setactivepage"></a>CPropertySheet::SetActivePage  
 Modifie la page active.  
  
```  
BOOL SetActivePage(int nPage);  
BOOL SetActivePage(CPropertyPage* pPage);
```  
  
### <a name="parameters"></a>Paramètres  
 `nPage`  
 Index de la page à définir. Doit être comprise entre 0 et inférieur au nombre de pages dans la feuille de propriétés, incluse.  
  
 `pPage`  
 Pointe vers la page à définir dans la feuille de propriétés. Il ne peut pas être **NULL**.  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la feuille de propriétés est activée avec succès ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Par exemple, utilisez `SetActivePage` si l’action d’un utilisateur sur une page doit provoquer une autre page pour devenir la page active.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CPropertySheet::GetActivePage](#getactivepage).  
  
##  <a name="a-namesetfinishtexta--cpropertysheetsetfinishtext"></a><a name="setfinishtext"></a>CPropertySheet::SetFinishText  
 Définit le texte du bouton de commande Terminer.  
  
```  
void SetFinishText(LPCTSTR lpszText);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszText`  
 Pointe vers le texte à afficher sur le bouton de commande de fin.  
  
### <a name="remarks"></a>Remarques  
 Appelez `SetFinishText` pour afficher le texte sur le bouton de commande Terminer et masquer les boutons suivant et précédent, une fois que l’utilisateur termine l’action sur la dernière page de l’Assistant.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#138;](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="a-namesettitlea--cpropertysheetsettitle"></a><a name="settitle"></a>CPropertySheet::SetTitle  
 Spécifie la légende de la feuille de propriétés (le texte affiché dans la barre de titre d’une fenêtre frame).  
  
```  
void SetTitle(
    LPCTSTR lpszText,  
    UINT nStyle = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 `nStyle`  
 Spécifie le style de titre de la feuille de propriété. Le style doit être spécifié à 0 ou en tant que **PSH_PROPTITLE**. Si le style est défini en tant que **PSH_PROPTITLE**, le mot « Propriétés » s’affiche après le texte spécifié comme légende. Par exemple, l’appel `SetTitle`(« Simple », **PSH_PROPTITLE**) entraîne une légende de feuille de propriété de « Propriétés Simple ».  
  
 `lpszText`  
 Pointe vers le texte à utiliser comme légende dans la barre de titre de la feuille de propriétés.  
  
### <a name="remarks"></a>Remarques  
 Par défaut, une feuille de propriétés utilise le paramètre de la légende dans le constructeur de la feuille des propriétés.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#139;](../../mfc/codesnippet/cpp/cpropertysheet-class_12.cpp)]  
  
##  <a name="a-namesetwizardbuttonsa--cpropertysheetsetwizardbuttons"></a><a name="setwizardbuttons"></a>CPropertySheet::SetWizardButtons  
 Active ou désactive le bouton précédent, suivant ou terminer dans une feuille de propriétés d’Assistant.  
  
```  
void SetWizardButtons(DWORD dwFlags);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwFlags`  
 Un jeu d’indicateurs qui personnalisent la fonction et l’apparence des boutons de l’Assistant. Ce paramètre peut être une combinaison des valeurs suivantes :  
  
- **PSWIZB_BACK** bouton précédent  
  
- **PSWIZB_NEXT** bouton suivant  
  
- **PSWIZB_FINISH** bouton Terminer  
  
- **PSWIZB_DISABLEDFINISH** bouton Terminer désactivé  
  
### <a name="remarks"></a>Remarques  
 Appelez `SetWizardButtons` uniquement après que la boîte de dialogue est ouverte ; vous ne pouvez pas appeler `SetWizardButtons` avant d’appeler [DoModal](#domodal). En règle générale, vous devez appeler `SetWizardButtons` de [notifications CPropertyPage::OnSetActive](../../mfc/reference/cpropertypage-class.md#onsetactive).  
  
 Si vous souhaitez modifier le texte sur le bouton Terminer ou masquer la prochaine arrière des boutons et une fois que l’utilisateur a terminé l’Assistant, appel [SetFinishText](#setfinishtext). Notez que le bouton est partagé pour terminer et suivant. Vous pouvez afficher un état ou un bouton suivant à la fois, mais pas les deux.  
  
### <a name="example"></a>Exemple  
 A `CPropertySheet` a trois pages de propriétés d’Assistant : `CStylePage`, `CColorPage`, et `CShapePage`.  Le fragment de code ci-dessous montre comment activer et désactiver la **retour** et **suivant** boutons sur la page de propriétés d’Assistant.  
  
 [!code-cpp[NVC_MFCDocView&#140;](../../mfc/codesnippet/cpp/cpropertysheet-class_13.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#141;](../../mfc/codesnippet/cpp/cpropertysheet-class_14.cpp)]  
  
 [!code-cpp[NVC_MFCDocView&#138;](../../mfc/codesnippet/cpp/cpropertysheet-class_11.cpp)]  
  
##  <a name="a-namesetwizardmodea--cpropertysheetsetwizardmode"></a><a name="setwizardmode"></a>Fonction CPropertySheet::SetWizardMode  
 Définit une page de propriétés comme un Assistant.  
  
```  
void SetWizardMode();
```  
  
### <a name="remarks"></a>Notes  
 Une caractéristique clé d’une page de propriétés Assistant est que l’utilisateur accède à l’aide de suivant ou terminer, sauvegarder et annuler des boutons au lieu des onglets.  
  
 Appelez `SetWizardMode` avant d’appeler [DoModal](#domodal). Après avoir appelé `SetWizardMode`, `DoModal` renvoie soit **ID_WIZFINISH** (si l’utilisateur ferme avec le bouton Terminer) ou **IDCANCEL**.  
  
 `SetWizardMode`définit l’indicateur PSH_WIZARD.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCDocView&#142;](../../mfc/codesnippet/cpp/cpropertysheet-class_15.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple CMNCTRL1](../../visual-cpp-samples.md)   
 [MFC exemple CMNCTRL2](../../visual-cpp-samples.md)   
 [Exemple MFC PROPDLG](../../visual-cpp-samples.md)   
 [Exemple MFC SNAPVW](../../visual-cpp-samples.md)   
 [CWnd (classe)](../../mfc/reference/cwnd-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)




