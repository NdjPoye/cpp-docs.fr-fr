---
title: Classe de COlePropertyPage | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- COlePropertyPage
- AFXCTL/COlePropertyPage
- AFXCTL/COlePropertyPage::COlePropertyPage
- AFXCTL/COlePropertyPage::GetControlStatus
- AFXCTL/COlePropertyPage::GetObjectArray
- AFXCTL/COlePropertyPage::GetPageSite
- AFXCTL/COlePropertyPage::IgnoreApply
- AFXCTL/COlePropertyPage::IsModified
- AFXCTL/COlePropertyPage::OnEditProperty
- AFXCTL/COlePropertyPage::OnHelp
- AFXCTL/COlePropertyPage::OnInitDialog
- AFXCTL/COlePropertyPage::OnObjectsChanged
- AFXCTL/COlePropertyPage::OnSetPageSite
- AFXCTL/COlePropertyPage::SetControlStatus
- AFXCTL/COlePropertyPage::SetDialogResource
- AFXCTL/COlePropertyPage::SetHelpInfo
- AFXCTL/COlePropertyPage::SetModifiedFlag
- AFXCTL/COlePropertyPage::SetPageName
dev_langs:
- C++
helpviewer_keywords:
- OLE property pages
- custom controls [MFC], properties
- COlePropertyPage class
- properties [C++], displaying
- displaying properties
- property pages, OLE
ms.assetid: e9972872-8e6b-4550-905e-d36a274d64dc
caps.latest.revision: 23
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
ms.openlocfilehash: 20d70cc25305fc5d17860314d9cfbe927df65c70
ms.lasthandoff: 02/24/2017

---
# <a name="colepropertypage-class"></a>COlePropertyPage (classe)
Utilisée pour afficher les propriétés d'un contrôle personnalisé dans une interface graphique, similaire à une boîte de dialogue.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class AFX_NOVTABLE COlePropertyPage : public CDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[COlePropertyPage::COlePropertyPage](#colepropertypage)|Construit un objet `COlePropertyPage`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[COlePropertyPage::GetControlStatus](#getcontrolstatus)|Indique si l’utilisateur a modifié la valeur dans le contrôle.|  
|[COlePropertyPage::GetObjectArray](#getobjectarray)|Retourne le tableau d’objets en cours de modification par la page de propriétés.|  
|[COlePropertyPage::GetPageSite](#getpagesite)|Retourne un pointeur vers la page de propriétés `IPropertyPageSite` interface.|  
|[COlePropertyPage::IgnoreApply](#ignoreapply)|Détermine quels contrôles de ne pas activer le bouton Appliquer.|  
|[COlePropertyPage::IsModified](#ismodified)|Indique si l’utilisateur a modifié la page de propriétés.|  
|[COlePropertyPage::OnEditProperty](#oneditproperty)|Appelé par l’infrastructure lorsque l’utilisateur modifie une propriété.|  
|[COlePropertyPage::OnHelp](#onhelp)|Appelé par l’infrastructure lorsque l’utilisateur appelle l’aide.|  
|[COlePropertyPage::OnInitDialog](#oninitdialog)|Appelé par l’infrastructure lors de l’initialisation de la page de propriétés.|  
|[COlePropertyPage::OnObjectsChanged](#onobjectschanged)|Appelé par l’infrastructure lorsque vous sélectionnez un autre contrôle OLE, avec de nouvelles propriétés.|  
|[COlePropertyPage::OnSetPageSite](#onsetpagesite)|Appelé par l’infrastructure lorsque le frame de propriété fournit le site de la page.|  
|[COlePropertyPage::SetControlStatus](#setcontrolstatus)|Définit un indicateur qui indique si l’utilisateur a modifié la valeur dans le contrôle.|  
|[COlePropertyPage::SetDialogResource](#setdialogresource)|Définit la ressource de boîte de dialogue de la page de propriétés.|  
|[COlePropertyPage::SetHelpInfo](#sethelpinfo)|Définit le texte d’aide succincte de la page de propriété, le nom de son fichier d’aide et son contexte d’aide.|  
|[COlePropertyPage::SetModifiedFlag](#setmodifiedflag)|Définit un indicateur qui indique si l’utilisateur a modifié la page de propriétés.|  
|[COlePropertyPage::SetPageName](#setpagename)|Définit le nom de la page de propriétés (légende).|  
  
## <a name="remarks"></a>Remarques  
 Par exemple, une page de propriétés peut inclure un contrôle d’édition qui permet à l’utilisateur d’afficher et de modifier la propriété caption du contrôle.  
  
 Chaque propriété de contrôle personnalisé ou stock peut avoir un contrôle de boîte de dialogue qui permet à l’utilisateur du contrôle afficher la valeur actuelle de la propriété et de modifier cette valeur si nécessaire.  
  
 Pour plus d’informations sur l’utilisation de `COlePropertyPage`, consultez l’article [contrôles ActiveX : Pages de propriétés](../../mfc/mfc-activex-controls-property-pages.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 `COlePropertyPage`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxctl.h  
  
##  <a name="colepropertypage"></a>COlePropertyPage::COlePropertyPage  
 Construit un objet `COlePropertyPage`.  
  
```  
COlePropertyPage(
    UINT idDlg,  
    UINT idCaption);
```  
  
### <a name="parameters"></a>Paramètres  
 *idDlg*  
 ID de ressource de modèle de la boîte de dialogue.  
  
 *idCaption*  
 ID de ressource de la légende de la page propriété.  
  
### <a name="remarks"></a>Notes  
 Lorsque vous implémentez une sous-classe de `COlePropertyPage`, constructeur de votre sous-classe doit utiliser le `COlePropertyPage` constructeur pour identifier la ressource modèle de boîte de dialogue sur la page de propriétés est basé et la ressource de chaîne qui contient la légende.  
  
##  <a name="getcontrolstatus"></a>COlePropertyPage::GetControlStatus  
 Détermine si l’utilisateur a modifié la valeur de la propriété du contrôle de page avec l’ID de ressource spécifié.  
  
```  
BOOL GetControlStatus(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 ID de ressource d’un contrôle de page de propriétés.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si la valeur du contrôle a été modifié ; sinon **FALSE**.  
  
##  <a name="getobjectarray"></a>COlePropertyPage::GetObjectArray  
 Retourne le tableau d’objets en cours de modification par la page de propriétés.  
  
```  
LPDISPATCH* GetObjectArray(ULONG* pnObjects);
```  
  
### <a name="parameters"></a>Paramètres  
 `pnObjects`  
 Pointeur vers un entier long non signé qui reçoit le nombre d’objets en cours de modification par la page.  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un tableau de `IDispatch` pointeurs qui sont utilisés pour accéder aux propriétés de chaque contrôle sur la page de propriétés. L’appelant ne doit pas libérer ces pointeurs d’interface.  
  
### <a name="remarks"></a>Remarques  
 Chaque objet de page de propriétés conserve un tableau de pointeurs vers les `IDispatch` interfaces des objets en cours de modification par la page. Cette fonction définit son `pnObjects` argument au nombre d’éléments dans ce tableau et retourne un pointeur vers le premier élément du tableau.  
  
##  <a name="getpagesite"></a>COlePropertyPage::GetPageSite  
 Obtient un pointeur vers la page de propriétés `IPropertyPageSite` interface.  
  
```  
LPPROPERTYPAGESITE GetPageSite();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un pointeur vers la page de propriétés `IPropertyPageSite` interface.  
  
### <a name="remarks"></a>Remarques  
 Contrôles et conteneurs coopèrent afin que les utilisateurs peuvent parcourir et modifier les propriétés du contrôle. Le contrôle fournit des pages de propriétés, chacune d’elles est un objet OLE qui permet à l’utilisateur de modifier un ensemble de propriétés. Le conteneur fournit un frame de propriété qui affiche les pages de propriétés. Pour chaque page, le frame de propriété fournit un site de la page, qui prend en charge la `IPropertyPageSite` interface.  
  
##  <a name="ignoreapply"></a>COlePropertyPage::IgnoreApply  
 Détermine quels contrôles de ne pas activer le bouton Appliquer.  
  
```  
void IgnoreApply(UINT nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 ID du contrôle doivent être ignorés.  
  
### <a name="remarks"></a>Remarques  
 Bouton Appliquer de la page propriété est activée uniquement lorsque les valeurs de propriété de contrôle de page ont été modifiées. Cette fonction permet de spécifier des contrôles qui ne provoquent pas le bouton Appliquer être activé que leurs valeurs changent.  
  
##  <a name="ismodified"></a>COlePropertyPage::IsModified  
 Détermine si l’utilisateur a modifié des valeurs dans la page de propriétés.  
  
```  
BOOL IsModified();
```  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE** si la page de propriétés a été modifiée.  
  
##  <a name="oneditproperty"></a>COlePropertyPage::OnEditProperty  
 L’infrastructure appelle cette fonction lorsqu’une propriété spécifique doit être modifié.  
  
```  
virtual BOOL OnEditProperty(DISPID dispid);
```  
  
### <a name="parameters"></a>Paramètres  
 `dispid`  
 ID de dispatch de la propriété en cours de modification.  
  
### <a name="return-value"></a>Valeur de retour  
 L’implémentation par défaut retourne **FALSE**. Remplacements de cette fonction doivent retourner **TRUE**.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez substituer pour définir le focus sur le contrôle approprié sur la page. L’implémentation par défaut ne fait rien et retourne **FALSE**.  
  
##  <a name="onhelp"></a>COlePropertyPage::OnHelp  
 L’infrastructure appelle cette fonction lorsque l’utilisateur demande l’aide en ligne.  
  
```  
virtual BOOL OnHelp(LPCTSTR lpszHelpDir);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszHelpDir*  
 Répertoire contenant le fichier d’aide de la page de propriétés.  
  
### <a name="return-value"></a>Valeur de retour  
 L’implémentation par défaut retourne **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Remplacer si votre page de propriétés doit effectuer une action spéciale lorsque l’utilisateur accède à l’aide. L’implémentation par défaut ne fait rien et retourne **FALSE**, qui indique à l’infrastructure d’appeler WinHelp.  
  
##  <a name="oninitdialog"></a>COlePropertyPage::OnInitDialog  
 L’infrastructure appelle cette fonction lorsque la boîte de dialogue de la page de propriétés est initialisée.  
  
```  
virtual BOOL OnInitDialog();
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’implémentation par défaut retourne **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Remplacer si une action spéciale est requise lors de l’initialisation de la boîte de dialogue. L’implémentation par défaut appelle `CDialog::OnInitDialog` et retourne **FALSE**.  
  
##  <a name="onobjectschanged"></a>COlePropertyPage::OnObjectsChanged  
 Appelé par l’infrastructure lorsque vous sélectionnez un autre contrôle OLE, avec de nouvelles propriétés.  
  
```  
virtual void OnObjectsChanged();
```  
  
### <a name="remarks"></a>Notes  
 Lorsque vous affichez les propriétés d’un contrôle OLE dans l’environnement de développement, une boîte de dialogue non modale est utilisée pour afficher ses pages de propriétés. Si un autre contrôle est sélectionné, un ensemble différent de pages de propriétés doit être affiché pour le nouvel ensemble de propriétés. L’infrastructure appelle cette fonction pour informer la page de propriétés de la modification.  
  
 Remplacez cette fonction pour recevoir une notification de cette action et d’effectuer d’actions particulières.  
  
##  <a name="onsetpagesite"></a>COlePropertyPage::OnSetPageSite  
 L’infrastructure appelle cette fonction lorsque le frame de propriété fournit le site de la page de la page de propriétés.  
  
```  
virtual void OnSetPageSite();
```  
  
### <a name="remarks"></a>Remarques  
 L’implémentation par défaut charge légende de la page et tente de déterminer la taille de la page à partir de la ressource de boîte de dialogue. Remplacez cette fonction si votre page de propriétés requiert aucune action supplémentaire ; votre substitution doit appeler l’implémentation de classe de base.  
  
##  <a name="setcontrolstatus"></a>COlePropertyPage::SetControlStatus  
 Modifie l’état d’un contrôle de page de propriétés.  
  
```  
BOOL SetControlStatus(
    UINT nID,  
    BOOL bDirty);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 Contient l’ID d’un contrôle de page de propriétés.  
  
 `bDirty`  
 Spécifie si un champ de la page de propriétés a été modifié. La valeur **TRUE** si le champ a été modifié, **FALSE** s’il n’a pas été modifié.  
  
### <a name="return-value"></a>Valeur de retour  
 **TRUE**, si le contrôle spécifié a été défini ; sinon **FALSE**.  
  
### <a name="remarks"></a>Remarques  
 Si l’état d’un contrôle de page de propriétés est modifié lors de la fermeture de la page de propriétés ou le bouton Appliquer est choisi, la propriété du contrôle est mis à jour avec la valeur appropriée.  
  
##  <a name="setdialogresource"></a>COlePropertyPage::SetDialogResource  
 Définit la ressource de boîte de dialogue de la page de propriétés.  
  
```  
void SetDialogResource(HGLOBAL hDialog);
```  
  
### <a name="parameters"></a>Paramètres  
 *hDialog*  
 Handle de ressource de boîte de dialogue de la page de propriétés.  
  
##  <a name="sethelpinfo"></a>COlePropertyPage::SetHelpInfo  
 Spécifie les informations de l’info-bulle, le nom du fichier d’aide et le contexte d’aide pour la page de propriétés.  
  
```  
void SetHelpInfo(
    LPCTSTR lpszDocString,  
    LPCTSTR lpszHelpFile = NULL,  
    DWORD dwHelpContext = 0);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszDocString*  
 Chaîne contenant les informations d’aide succincte pour l’affichage dans la barre d’état ou un autre emplacement.  
  
 `lpszHelpFile`  
 Nom du fichier d’aide de la page de propriétés.  
  
 *dwHelpContext*  
 Contexte d’aide pour la page de propriétés.  
  
##  <a name="setmodifiedflag"></a>COlePropertyPage::SetModifiedFlag  
 Indique si l’utilisateur a modifié la page de propriétés.  
  
```  
void SetModifiedFlag(BOOL bModified = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 `bModified`  
 Spécifie la nouvelle valeur de l’indicateur modifié de la page de propriétés.  
  
##  <a name="setpagename"></a>COlePropertyPage::SetPageName  
 Définit le nom de la page de propriétés, qui affiche généralement le frame de propriété sur l’onglet de la page.  
  
```  
void SetPageName(LPCTSTR lpszPageName);
```  
  
### <a name="parameters"></a>Paramètres  
 *lpszPageName*  
 Pointeur vers une chaîne contenant le nom de la page propriété.  
  
## <a name="see-also"></a>Voir aussi  
 [MFC exemple CIRC3](../../visual-cpp-samples.md)   
 [Exemple MFC TESTHELP](../../visual-cpp-samples.md)   
 [CDialog (classe)](../../mfc/reference/cdialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [CDialog (classe)](../../mfc/reference/cdialog-class.md)

