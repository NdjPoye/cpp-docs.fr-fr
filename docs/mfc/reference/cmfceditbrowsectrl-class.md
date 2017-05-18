---
title: Classe de CMFCEditBrowseCtrl | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFileBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::EnableFolderBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::GetMode
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnAfterUpdate
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnBrowse
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnChangeLayout
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnDrawBrowseButton
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::OnIllegalFileName
- AFXEDITBROWSECTRL/CMFCEditBrowseCtrl::SetBrowseButtonImage
dev_langs:
- C++
helpviewer_keywords:
- CMFCEditBrowseCtrl::PreTranslateMessage method
- CMFCEditBrowseCtrl constructor
- CMFCEditBrowseCtrl class
ms.assetid: 69cfd886-3d35-4bee-8901-7c88fcf9520f
caps.latest.revision: 33
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
ms.translationtype: Machine Translation
ms.sourcegitcommit: 0e0c08ddc57d437c51872b5186ae3fc983bb0199
ms.openlocfilehash: 5c5650da677a442628049c9ef4b41c2142cfb2c2
ms.contentlocale: fr-fr
ms.lasthandoff: 02/24/2017

---
# <a name="cmfceditbrowsectrl-class"></a>CMFCEditBrowseCtrl (classe)
La `CMFCEditBrowseCtrl` classe prend en charge le contrôle de modification, qui est une zone de texte modifiable contenant éventuellement un bouton Parcourir. Lorsque l’utilisateur clique sur le bouton Parcourir, le contrôle effectue une action personnalisée ou affiche une boîte de dialogue standard qui contient un explorateur de fichiers ou de dossiers.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CMFCEditBrowseCtrl : public CEdit  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|`CMFCEditBrowseCtrl::CMFCEditBrowseCtrl`|Constructeur par défaut.|  
|`CMFCEditBrowseCtrl::~CMFCEditBrowseCtrl`|Destructeur.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton)|Active ou désactive (masque) le bouton Parcourir.|  
|[CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton)|Active le bouton Parcourir et place le contrôle edit dans *recherche* mode.|  
|[CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton)|Active le bouton Parcourir et place le contrôle edit dans *recherche de dossiers* mode.|  
|[CMFCEditBrowseCtrl::GetMode](#getmode)|Retourne le mode de navigation en cours.|  
|[CMFCEditBrowseCtrl::OnAfterUpdate](#onafterupdate)|Appelé par l’infrastructure une fois que le contrôle edit est mis à jour avec le résultat d’une action de navigation.|  
|[CMFCEditBrowseCtrl::OnBrowse](#onbrowse)|Appelé par l’infrastructure une fois que l’utilisateur clique sur le bouton Parcourir.|  
|[CMFCEditBrowseCtrl::OnChangeLayout](#onchangelayout)|Redessine le contrôle de navigation modifier actuel.|  
|[CMFCEditBrowseCtrl::OnDrawBrowseButton](#ondrawbrowsebutton)|Appelé par l’infrastructure pour dessiner le bouton Parcourir.|  
|[CMFCEditBrowseCtrl::OnIllegalFileName](#onillegalfilename)|Appelé par l’infrastructure lorsqu’un nom de fichier non valide a été entré dans le contrôle d’édition.|  
|`CMFCEditBrowseCtrl::PreTranslateMessage`|Convertit les messages de fenêtre avant qu’ils soient distribués à le [TranslateMessage](http://msdn.microsoft.com/library/windows/desktop/ms644955) et [DispatchMessage](http://msdn.microsoft.com/library/windows/desktop/ms644934) fonctions de Windows. Pour la syntaxe et plus d’informations, consultez [CWnd::PreTranslateMessage](../../mfc/reference/cwnd-class.md#pretranslatemessage).|  
|[CMFCEditBrowseCtrl::SetBrowseButtonImage](#setbrowsebuttonimage)|Définit une image personnalisée pour le bouton Parcourir.|  
  
## <a name="remarks"></a>Remarques  
 Utilisez un contrôle d’édition Parcourir pour sélectionner un nom de fichier ou dossier. Vous pouvez également utiliser le contrôle pour effectuer une action personnalisée comme pour afficher une boîte de dialogue. Vous pouvez afficher ou pas le bouton Parcourir, et vous pouvez appliquer une étiquette personnalisée ou une image sur le bouton.  
  
 Le *en mode de navigation* du modifier pour parcourir le contrôle détermine s’il affiche un bouton de navigation et l’action qui se produit lorsque l’utilisateur clique sur le bouton. Pour plus d’informations, consultez la [GetMode](#getmode) méthode.  
  
 La `CMFCEditBrowseCtrl` classe prend en charge les modes suivants.  
  
 `custom mode`  
 Une action personnalisée est effectuée lorsque l’utilisateur clique sur le bouton Parcourir. Par exemple, vous pouvez afficher une boîte de dialogue spécifique à l’application.  
  
 `file mode`  
 Une boîte de dialogue de sélection de fichier standard s’affiche lorsque l’utilisateur clique sur le bouton Parcourir.  
  
 `folder mode`  
 Une boîte de dialogue de sélection de dossier standard s’affiche lorsque l’utilisateur clique sur le bouton Parcourir.  
  
## <a name="how-to-specify-an-edit-browse-control"></a>Comment : Spécifier un contrôle de zone de modification  
 Procédez comme suit pour incorporer un contrôle d’édition Parcourir dans votre application :  
  
1.  Si vous souhaitez implémenter un mode de navigation personnalisé, dérivez votre propre classe à partir de la `CMFCEditBrowseCtrl` de classe, puis vous remplacez le [CMFCEditBrowseCtrl::OnBrowse](#onbrowse) (méthode). Dans la méthode substituée, exécuter une action Parcourir personnalisée et mettre à jour le contrôle de modification avec le résultat.  
  
2.  Soit incorporer la `CMFCEditBrowseCtrl` objet ou l’objet contrôle edit dérivée dans l’objet de fenêtre parent.  
  
3.  Si vous utilisez la **Assistant classe** pour créer une boîte de dialogue, ajoutez un contrôle d’édition ( `CEdit`) pour le formulaire de boîte de dialogue. En outre, ajoutez une variable pour accéder au contrôle dans votre fichier d’en-tête. Dans votre fichier d’en-tête, modifiez le type de la variable de `CEdit` à `CMFCEditBrowseCtrl`. Le contrôle edit est créé automatiquement. Si vous n’utilisez pas le **Assistant classe**, ajoutez un `CMFCEditBrowseCtrl` à votre fichier d’en-tête et l’appel puis la variable son `Create` (méthode).  
  
4.  Si vous ajoutez un contrôle de zone de modification à une boîte de dialogue, utilisez le **ClassWizard** outil pour configurer l’échange de données.  
  
5.  Appelez le [EnableFolderBrowseButton](#enablefolderbrowsebutton), [EnableFileBrowseButton](#enablefilebrowsebutton), ou [EnableBrowseButton](#enablebrowsebutton) méthode pour définir le mode de navigation et afficher le bouton Parcourir. Appelez le [GetMode](#getmode) méthode pour obtenir le mode de navigation en cours.  
  
6.  Pour fournir une image personnalisée pour le bouton Parcourir, appelez le [SetBrowseButtonImage](#setbrowsebuttonimage) méthode ou remplacement le [OnDrawBrowseButton](#ondrawbrowsebutton) (méthode).  
  
7.  Pour supprimer le bouton Parcourir le contrôle de modification, appelez le [EnableBrowseButton](#enablebrowsebutton) méthode avec la `bEnable` paramètre la valeur `FALSE`.  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CEdit](../../mfc/reference/cedit-class.md)  
  
 [CMFCEditBrowseCtrl](../../mfc/reference/cmfceditbrowsectrl-class.md)  
  
## <a name="example"></a>Exemple  
 L’exemple suivant montre comment utiliser les deux méthodes dans le `CMFCEditBrowseCtrl` classe : `EnableFolderBrowseButton` et `EnableFileBrowseButton`. Cet exemple fait partie de la [exemple de nouveaux contrôles](../../visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_NewControls n °&6;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_1.h)]  
[!code-cpp[NVC_MFC_NewControls&#7;](../../mfc/reference/codesnippet/cpp/cmfceditbrowsectrl-class_2.cpp)]  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxeditbrowsectrl.h  
  
##  <a name="enablebrowsebutton"></a>CMFCEditBrowseCtrl::EnableBrowseButton  
 Affiche ou n’affiche pas le bouton Parcourir sur le contrôle de navigation modifier actuel.  
  
```  
void EnableBrowseButton(
    BOOL bEnable=TRUE,  
    LPCTSTR szLabel=_T("..."));
```  
  
### <a name="parameters"></a>Paramètres  
 `bEnable`  
 `TRUE`Pour afficher le bouton Parcourir. `FALSE` ne pas à afficher le bouton Parcourir. La valeur par défaut est `TRUE`.  
  
 `szLabel`  
 L’étiquette est affichée sur le bouton Parcourir. La valeur par défaut est « **... **".  
  
### <a name="remarks"></a>Remarques  
 Si le `bEnable` paramètre est `TRUE`, implémenter une action personnalisée à effectuer lorsque l’utilisateur clique sur le bouton Parcourir. Pour implémenter une action personnalisée, dérivez une classe à partir de la `CMFCEditBrowseCtrl` de classe, puis vous remplacez sa [OnBrowse](#onbrowse) (méthode).  
  
 Si le `bEnable` paramètre est `TRUE`, est le mode de navigation du contrôle `BrowseMode_Default`; sinon, le mode de navigation est `BrowseMode_None`. Pour plus d’informations sur les modes d’exploration, consultez le [GetMode](#getmode) méthode.  
  
##  <a name="enablefilebrowsebutton"></a>CMFCEditBrowseCtrl::EnableFileBrowseButton  
 Affiche le bouton Parcourir sur le contrôle de navigation modifier actuel et place le contrôle en *recherche* mode.  
  
```  
void EnableFileBrowseButton(
    LPCTSTR lpszDefExt=NULL,  
    LPCTSTR lpszFilter=NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszDefExt`  
 Spécifie l’extension de nom de fichier par défaut utilisée dans la boîte de dialogue de sélection de fichier. La valeur par défaut est `NULL`.  
  
 `lpszFilter`  
 Spécifie la chaîne de filtrage par défaut utilisée dans la boîte de dialogue de sélection de fichier. La valeur par défaut est `NULL`.  
  
 `dwFlags`  
 Indicateurs de boîte de dialogue. La valeur par défaut est une combinaison (OR) au niveau du bit de OFN_HIDEREADONLY et OFN_OVERWRITEPROMPT.  
  
### <a name="remarks"></a>Notes  
 Quand le contrôle de zone de modification est en mode de navigation de fichiers et que l'utilisateur clique sur le bouton parcourir, le contrôle affiche la boîte de dialogue de sélection de fichier standard.  
  
 Pour obtenir une liste complète des indicateurs disponibles, consultez la page [structure OPENFILENAME](https://msdn.microsoft.com/library/ms646839.aspx).  
  
##  <a name="enablefolderbrowsebutton"></a>CMFCEditBrowseCtrl::EnableFolderBrowseButton  
 Affiche le bouton Parcourir sur le contrôle de navigation modifier actuel et place le contrôle en *recherche de dossiers* mode.  
  
```  
void EnableFolderBrowseButton();
```  
  
### <a name="remarks"></a>Remarques  
 Lorsque le contrôle edit est en mode de navigation de dossier et que l’utilisateur clique sur le bouton Parcourir, le contrôle affiche la boîte de dialogue de sélection du dossier standard.  
  
##  <a name="getmode"></a>CMFCEditBrowseCtrl::GetMode  
 Récupère le mode de navigation du contrôle edit Parcourir en cours.  
  
```  
CMFCEditBrowseCtrl::BrowseMode GetMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs d’énumération qui spécifie le mode actuel de la modification parcourir le contrôle. Le mode de navigation détermine si l’infrastructure affiche le bouton Parcourir et l’action qui se produit lorsqu’un utilisateur clique sur ce bouton.  
  
 Le tableau ci-dessous répertorie les valeurs de retour possibles.  
  
|Valeur|Description|  
|-----------|-----------------|  
|`BrowseMode_Default`|`custom mode`. Une action définie par le programmeur est effectuée.|  
|`BrowseMode_File`|`file mode`. La boîte de dialogue navigateur standard s’affiche.|  
|`BrowseMode_Folder`|`folder mode`. La boîte de dialogue navigateur standard s’affiche.|  
|`BrowseMode_None`|Le bouton Parcourir n’est pas affiché.|  
  
### <a name="remarks"></a>Remarques  
 Par défaut, un `CMFCEditBrowseCtrl` objet est initialisé à `BrowseMode_None` mode. Modifier le mode de navigation avec le [CMFCEditBrowseCtrl::EnableBrowseButton](#enablebrowsebutton), [CMFCEditBrowseCtrl::EnableFileBrowseButton](#enablefilebrowsebutton), et [CMFCEditBrowseCtrl::EnableFolderBrowseButton](#enablefolderbrowsebutton) méthodes.  
  
##  <a name="onafterupdate"></a>CMFCEditBrowseCtrl::OnAfterUpdate  
 Appelé par l’infrastructure une fois que le contrôle edit est mis à jour avec le résultat d’une action de navigation.  
  
```  
virtual void OnAfterUpdate();
```  
  
### <a name="remarks"></a>Remarques  
 Substituez cette méthode dans une classe dérivée pour implémenter une action personnalisée.  
  
##  <a name="onbrowse"></a>CMFCEditBrowseCtrl::OnBrowse  
 Appelé par l’infrastructure une fois que l’utilisateur clique sur le bouton Parcourir le parcourir de contrôle d’édition.  
  
```  
virtual void OnBrowse();
```  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette méthode pour exécuter du code personnalisé lorsque l’utilisateur clique sur le bouton Parcourir le parcourir de contrôle d’édition. Dérivez votre propre classe de la `CMFCEditBrowseCtrl` classe et substituer sa `OnBrowse` méthode. Dans cette méthode, implémenter une action Parcourir personnalisée et éventuellement mettre à jour la zone de texte du contrôle d’édition Parcourir. Dans votre application, utilisez la [EnableBrowseButton](#enablebrowsebutton) méthode permettant de placer le contrôle edit *Parcourir personnalisée* mode.  
  
##  <a name="onchangelayout"></a>CMFCEditBrowseCtrl::OnChangeLayout  
 Redessine le contrôle de navigation modifier actuel.  
  
```  
virtual void OnChangeLayout();
```  
  
### <a name="remarks"></a>Remarques  
 L’infrastructure appelle cette méthode lorsque le mode de navigation de la parcourir Edition contrôle change. Pour plus d’informations, consultez [CMFCEditBrowseCtrl::GetMode](#getmode).  
  
##  <a name="ondrawbrowsebutton"></a>CMFCEditBrowseCtrl::OnDrawBrowseButton  
 Appelé par l’infrastructure pour dessiner le bouton Parcourir sur le contrôle de modification.  
  
```  
virtual void OnDrawBrowseButton(
    CDC* pDC,  
    CRect rect,  
    BOOL bIsButtonPressed,  
    BOOL bIsButtonHot);
```  
  
### <a name="parameters"></a>Paramètres  
 `pDC`  
 Pointeur vers un contexte de périphérique.  
  
 `Rect`  
 Le rectangle englobant du bouton Parcourir.  
  
 `bIsButtonPressed`  
 `TRUE`Si le bouton est activé ; dans le cas contraire, `FALSE`.  
  
 `bIsButtonHot`  
 `TRUE`Si le bouton est mis en surbrillance ; dans le cas contraire, `FALSE`.  
  
### <a name="remarks"></a>Remarques  
 Remplacez cette fonction dans une classe dérivée pour personnaliser l’apparence du bouton Parcourir.  
  
##  <a name="setbrowsebuttonimage"></a>CMFCEditBrowseCtrl::SetBrowseButtonImage  
 Définit une image personnalisée sur le bouton Parcourir le parcourir de contrôle d’édition.  
  
```  
void SetBrowseButtonImage(
    HICON hIcon,  
    BOOL bAutoDestroy= TRUE);

 
void SetBrowseButtonImage(
    HBITMAP hBitmap,  
    BOOL bAutoDestroy= TRUE);  
  
void SetBrowseButtonImage(UINT uiBmpResId);
```  
  
### <a name="parameters"></a>Paramètres  
 `hIcon`  
 Le handle d’une icône.  
  
 `hBitmap`  
 Le handle d’une bitmap.  
  
 `uiBmpResId`  
 L’ID de ressource de la bitmap.  
  
 `bAutoDestroy`  
 `TRUE`Pour supprimer l’icône spécifiée ou bitmap lorsque cette méthode se termine ; dans le cas contraire, `FALSE`. La valeur par défaut est `TRUE`.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette méthode pour appliquer une image personnalisée pour le bouton Parcourir. Par défaut, le framework Obtient une image standard lorsque le contrôle edit est dans *recherche* ou *recherche de dossiers* mode.  
  
##  <a name="onillegalfilename"></a>CMFCEditBrowseCtrl::OnIllegalFileName  
 Appelé par l’infrastructure lorsqu’un nom de fichier non valide a été entré dans le contrôle d’édition.  
  
```  
virtual BOOL OnIllegalFileName(CString& strFileName);
```  
  
### <a name="parameters"></a>Paramètres  
 `strFileName`  
 Spécifie le nom de fichier non valide.  
  
### <a name="return-value"></a>Valeur de retour  
 Doit retourner `FALSE` si ce nom de fichier ne peut pas être transmis à la suite de la boîte de dialogue fichier. Dans ce cas, est activé dans le contrôle d’édition et l’utilisateur doit continuer à modifier. L’implémentation par défaut affiche une boîte de message qui informe l’utilisateur sur le nom de fichier non conforme et retourne `FALSE`. Vous pouvez substituer cette méthode, veuillez corriger le nom de fichier et renvoyer `TRUE` pour un traitement ultérieur.  
  
### <a name="remarks"></a>Remarques  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)

