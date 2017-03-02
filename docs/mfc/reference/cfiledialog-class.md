---
title: Classe CFileDialog | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CFileDialog
dev_langs:
- C++
helpviewer_keywords:
- CFileDialog class
- common file dialog boxes
- dialog boxes, common
ms.assetid: fda4fd3c-08b8-4ce0-8e9d-7bab23f8c6c0
caps.latest.revision: 47
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
ms.openlocfilehash: 7cde10ee445a719bce6be4167698bd86c46a18c0
ms.lasthandoff: 02/24/2017

---
# <a name="cfiledialog-class"></a>CFileDialog (classe)
Encapsule la boîte de dialogue commune qui est utilisée pour l’ouverture du fichier ou les opérations de sauvegarde du fichier.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
class CFileDialog : public CCommonDialog  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-constructors"></a>Constructeurs publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileDialog::CFileDialog](#cfiledialog)|Construit un objet `CFileDialog`.|  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileDialog::AddCheckButton](#addcheckbutton)|Ajoute un bouton de vérification de la boîte de dialogue.|  
|[CFileDialog::AddComboBox](#addcombobox)|Ajoute une zone de liste déroulante de la boîte de dialogue.|  
|[CFileDialog::AddControlItem](#addcontrolitem)|Ajoute un élément à un contrôle conteneur dans la boîte de dialogue.|  
|[CFileDialog::AddEditBox](#addeditbox)|Ajoute une zone d’édition à la boîte de dialogue.|  
|[CFileDialog::AddMenu](#addmenu)|Ajoute un menu dans la boîte de dialogue.|  
|[CFileDialog::AddPlace](#addplace)|Surchargé. Ajoute qu'un dossier à la liste des places disponible pour l’utilisateur à ouvrir ou enregistrer des éléments.|  
|[CFileDialog::AddPushButton](#addpushbutton)|Ajoute un bouton à la boîte de dialogue.|  
|[CFileDialog::AddRadioButtonList](#addradiobuttonlist)|Ajoute un groupe d’options (également appelé bouton radio) dans la boîte de dialogue.|  
|[CFileDialog::AddSeparator](#addseparator)|Ajoute un séparateur à la boîte de dialogue.|  
|[CFileDialog::AddText](#addtext)|Ajoute le contenu de texte à la boîte de dialogue.|  
|[CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog)|Met à jour l’état de la `CFileDialog` pour faire correspondre les paramètres et les indicateurs stockés dans le `m_ofn` variable membre.|  
|[CFileDialog::DoModal](#domodal)|Affiche la boîte de dialogue et permet à l’utilisateur d’effectuer une sélection.|  
|[CFileDialog::EnableOpenDropDown](#enableopendropdown)|Active la liste déroulante sur le **Open** ou **enregistrer** bouton dans la boîte de dialogue.|  
|[CFileDialog::EndVisualGroup](#endvisualgroup)|Arrête l’ajout d’éléments à un groupe visuel dans la boîte de dialogue.|  
|[CFileDialog::GetCheckButtonState](#getcheckbuttonstate)|Obtient l’état actuel d’un bouton de vérification (case à cocher) dans la boîte de dialogue.|  
|[CFileDialog::GetControlItemState](#getcontrolitemstate)|Obtient l’état actuel d’un élément dans un contrôle conteneur dans la boîte de dialogue.|  
|[CFileDialog::GetControlState](#getcontrolstate)|Obtient la visibilité et activé les États d’un contrôle donné.|  
|[CFileDialog::GetEditBoxText](#geteditboxtext)|Obtient le texte actuel dans un contrôle de zone d’édition.|  
|[CFileDialog::GetFileExt](#getfileext)|Retourne l’extension du fichier sélectionné.|  
|[CFileDialog::GetFileName](#getfilename)|Retourne le nom de fichier du fichier sélectionné.|  
|[CFileDialog::GetFileTitle](#getfiletitle)|Retourne le titre du fichier sélectionné.|  
|[CFileDialog::GetFolderPath](#getfolderpath)|Récupère le chemin d’accès du dossier actuellement ouvert ou du répertoire Explorer-style **ouvrir** ou **Enregistrer sous** boîte de dialogue commune.|  
|[CFileDialog::GetIFileDialogCustomize](#getifiledialogcustomize)|Récupère l’objet COM interne pour personnalisé `CFileDialog` objet.|  
|[CFileDialog::GetIFileOpenDialog](#getifileopendialog)|Récupère l’objet COM interne pour un `CFileDialog` qui est utilisé comme un **Open** boîte de dialogue fichier.|  
|[CFileDialog::GetIFileSaveDialog](#getifilesavedialog)|Récupère l’objet COM interne pour un `CFileDialog` qui est utilisé comme un **enregistrer** boîte de dialogue fichier.|  
|[CFileDialog::GetNextPathName](#getnextpathname)|Retourne le chemin d’accès complet du fichier sélectionné suivant.|  
|[CFileDialog::GetOFN](#getofn)|Récupère le `OPENFILENAME` structure de le `CFileDialog` objet.|  
|[CFileDialog::GetPathName](#getpathname)|Retourne le chemin d’accès complet du fichier sélectionné.|  
|[CFileDialog::GetReadOnlyPref](#getreadonlypref)|Retourne l’état en lecture seule du fichier sélectionné.|  
|[CFileDialog::GetResult](#getresult)|Obtient le choix de l’utilisateur dans la boîte de dialogue.|  
|[CFileDialog::GetResults](#getresults)|Obtient le choix de l’utilisateur dans une boîte de dialogue permet la sélection multiple.|  
|[CFileDialog::GetSelectedControlItem](#getselectedcontrolitem)|Obtient un élément particulier de contrôles de conteneur spécifié dans la boîte de dialogue.|  
|[CFileDialog::GetStartPosition](#getstartposition)|Retourne la position du premier élément de la liste nom de fichier.|  
|[CFileDialog::HideControl](#hidecontrol)|Masque le contrôle spécifié dans un style Explorateur **Open** ou **Enregistrer sous** boîte de dialogue commune.|  
|[CFileDialog::IsPickFoldersMode](#ispickfoldersmode)|Détermine si la boîte de dialogue en cours en mode de sélecteur de dossier.|  
|[CFileDialog::MakeProminent](#makeprominent)|Place un contrôle dans la boîte de dialogue afin qu’il soit comparé à d’autres contrôles ajoutés.|  
|[CFileDialog::RemoveControlItem](#removecontrolitem)|Supprime un élément d’un contrôle conteneur dans la boîte de dialogue.|  
|[CFileDialog::SetCheckButtonState](#setcheckbuttonstate)|Définit l’état actuel d’un bouton de vérification (case à cocher) dans la boîte de dialogue.|  
|[CFileDialog::SetControlItemState](#setcontrolitemstate)|Définit l’état actuel d’un élément dans un contrôle conteneur dans la boîte de dialogue.|  
|[CFileDialog::SetControlItemText](#setcontrolitemtext)|Définit le texte d’un élément de contrôle. Par exemple, le texte qui accompagne une case d’option ou un élément dans un menu.|  
|[CFileDialog::SetControlLabel](#setcontrollabel)|Définit le texte associé à un contrôle, telles que le texte du bouton ou une étiquette de la zone Modifier.|  
|[CFileDialog::SetControlState](#setcontrolstate)|Définit la visibilité et activé les États d’un contrôle donné.|  
|[CFileDialog::SetControlText](#setcontroltext)|Définit le texte pour le contrôle spécifié dans un style Explorateur **Open** ou **Enregistrer sous** boîte de dialogue commune.|  
|[CFileDialog::SetDefExt](#setdefext)|Définit l’extension de nom de fichier par défaut pour un style Explorateur **Open** ou **Enregistrer sous** boîte de dialogue commune.|  
|[CFileDialog::SetEditBoxText](#seteditboxtext)|Définit le texte actuel dans un contrôle de zone d’édition.|  
|[CFileDialog::SetProperties](#setproperties)|Fournit une banque de propriétés qui définit les valeurs par défaut à utiliser pour l'élément en cours d'enregistrement.|  
|[CFileDialog::SetSelectedControlItem](#setselectedcontrolitem)|Définit l’état sélectionné d’un élément particulier dans un groupe de bouton d’option ou une zone de liste déroulante dans la boîte de dialogue.|  
|[CFileDialog::SetTemplate](#settemplate)|Définit le modèle de boîte de dialogue pour le `CFileDialog` objet.|  
|[CFileDialog::StartVisualGroup](#startvisualgroup)|Déclare un groupe visuel dans la boîte de dialogue. Les appels suivants à toute méthode « add » ajoutent ces éléments à ce groupe.|  
|[CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog)|Met à jour les données stockées dans le `m_ofn` variable de membre pour refléter l’état actuel de la boîte de dialogue de fichier.|  
  
### <a name="protected-methods"></a>Méthodes protégées  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileDialog::OnButtonClicked](#onbuttonclicked)|Appelé lorsque le bouton est activé.|  
|[CFileDialog::OnCheckButtonToggled](#oncheckbuttontoggled)|Appelé lorsque la case à cocher est activée/désactivée.|  
|[CFileDialog::OnControlActivating](#oncontrolactivating)|Appelée lorsque le contrôle est actif.|  
|[CFileDialog::OnFileNameChange](#onfilenamechange)|Gère la `WM_NOTIFY CDN_SELCHANGE` message.|  
|[CFileDialog::OnFileNameOK](#onfilenameok)|Valide le nom de fichier entré dans la boîte de dialogue.|  
|[CFileDialog::OnFolderChange](#onfolderchange)|Gère la `WM_NOTIFY CDN_FOLDERCHANGE` message.|  
|[CFileDialog::OnInitDone](#oninitdone)|Gère la `WM_NOTIFY CDN_INITDONE` message.|  
|[CFileDialog::OnItemSelected](#onitemselected)|Appelé lorsque l’élément conteneur est sélectionné.|  
|[CFileDialog::OnLBSelChangedNotify](#onlbselchangednotify)|Vous permet d’effectuer des actions personnalisées lors de la modification de la sélection de fichier.|  
|[CFileDialog::OnShareViolation](#onshareviolation)|Poignées de partagent les violations.|  
|[CFileDialog::OnTypeChange](#ontypechange)|Gère la `WM_NOTIFY CDN_TYPECHANGE` message.|  
  
### <a name="public-data-members"></a>Membres de données publics  
  
|Nom|Description|  
|----------|-----------------|  
|[CFileDialog::m_ofn](#m_ofn)|Les fenêtres `OPENFILENAME` structure. Fournit l’accès aux paramètres de zone de boîte de dialogue de fichier de base.|  
  
## <a name="remarks"></a>Notes  
 Les boîtes de dialogue de fichiers courantes vous permettent d’implémenter des boîtes de dialogue Sélection de fichier, par exemple, **ouvrir le fichier** et **Enregistrer sous**, de manière cohérente avec les normes de Windows.  
  
 Vous pouvez utiliser `CFileDialog` en l’état avec le constructeur fourni, ou vous pouvez dériver votre propre classe de boîte de dialogue de `CFileDialog` et écrire un constructeur pour répondre à vos besoins. Dans les deux cas, ces boîtes de dialogue seront comporte comme les boîtes de dialogue MFC standard, car elles sont dérivées de la [CCommonDialog classe](../../mfc/reference/ccommondialog-class.md). `CFileDialog`s’appuie sur le COMMDLG. Fichier DLL qui est incluse dans Windows.  
  
 L’apparence et les fonctionnalités de la `CFileDialog` avec [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] diffèrent des versions antérieures de Windows. La valeur par défaut `CFileDialog` utilise automatiquement la nouvelle [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] style sans modifications de code si un programme est compilé et exécuté sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Utilisez le `bVistaStyle` paramètre dans le constructeur pour substituer manuellement cette mise à jour automatique. L’exception à la mise à jour automatique est de boîtes de dialogue personnalisées. Ils ne seront pas convertis vers le nouveau style. Pour plus d’informations sur le constructeur, consultez [CFileDialog::CFileDialog](#cfiledialog).  
  
> [!NOTE]
>  Le système de contrôle de code diffère dans [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] à partir de versions antérieures de Windows lorsque vous utilisez un `CFileDialog`. Vous devez mettre à jour toutes les références à `CFileDialog` contrôles dans le code avant que vous pouvez porter votre projet à partir d’une version antérieure de Windows.  
  
 Certains `CFileDialog` méthodes ne sont pas prises en charge sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Consultez la rubrique de la méthode individuelle pour savoir si la méthode est prise en charge. En outre, les fonctions héritées suivantes ne sont pas pris en charge sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- [CDialog::OnInitDialog](../../mfc/reference/cdialog-class.md#oninitdialog)  
  
- [CDialog::OnSetFont](../../mfc/reference/cdialog-class.md#onsetfont)  
  
 Les messages windows pour le `CFileDialog` classe varient selon le système d’exploitation que vous utilisez. Par exemple, Windows XP ne prend pas en charge [CDialog::OnCancel](../../mfc/reference/cdialog-class.md#oncancel) et [CDialog::OnOK](../../mfc/reference/cdialog-class.md#onok) pour la `CFileDialog` classe. Toutefois, [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] les prend en charge. Pour plus d’informations sur les différents messages générés et l’ordre dans lequel ils sont reçus, consultez [CFileDialog, exemple : ordre des événements de journalisation](../../visual-cpp-samples.md).  
  
 Pour utiliser un `CFileDialog` d’objet, commencez par créer l’objet à l’aide de la `CFileDialog` constructeur. Une fois la boîte de dialogue a été construite, vous pouvez définir ou modifier des valeurs dans le [CFileDialog::m_ofn](#m_ofn) structure pour initialiser les valeurs ou les États de contrôle de la boîte de dialogue. Le `m_ofn` structure est de type `OPENFILENAME`. Pour plus d’informations, consultez la [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Après avoir initialisé les contrôles de boîte de dialogue, appelez le [CFileDialog::DoModal](#domodal) méthode pour afficher la boîte de dialogue zone afin que l’utilisateur peut taper le chemin d’accès et nom de fichier. `DoModal`Retourne si l’utilisateur a cliqué sur OK (IDOK) ou sur le bouton Annuler (IDCANCEL). Si `DoModal` retourne IDOK, vous pouvez utiliser l’une de le `CFileDialog` pour récupérer les informations des fonctions membres publiques placer dans par l’utilisateur.  
  
> [!NOTE]
>  Sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], plusieurs appels à [IFileDialog::SetFileTypes](http://msdn.microsoft.com/library/windows/desktop/bb775980) provoque une erreur. Le deuxième appel à `SetFileTypes` des instances d’un `CFileDialog` retournera `E_UNEXPECTED` dans [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Certains `CFileDialog` méthode fonctions appellent `SetFileTypes`. Par exemple, deux appels à `CFileDialog::DoModal` pour la même instance d’un `CFileDialog` génère [ASSERT](http://msdn.microsoft.com/library/1e70902d-d58c-4e7b-9f69-2aeb6cbe476c).  
  
 `CFileDialog`inclut plusieurs membres protégés qui vous permettent d’effectuer la gestion personnalisée des violations de partage, validation du nom du fichier et notification de modification de zone de liste. Ces membres protégés sont des fonctions de rappel que la plupart des applications n’ont pas à utiliser la gestion par défaut étant effectuée automatiquement. Entrées de table des messages pour ces fonctions ne sont pas requises, car ils sont des fonctions virtuelles standards.  
  
 Vous pouvez utiliser les fenêtres [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) fonction pour déterminer si une erreur s’est produite lors de l’initialisation de la boîte de dialogue et pour en savoir plus sur l’erreur.  
  
 La destruction de `CFileDialog` objets est gérée automatiquement. Vous n’avez pas à appeler [CDialog::EndDialog](../../mfc/reference/cdialog-class.md#enddialog).  
  
 Pour permettre à l’utilisateur de sélectionner plusieurs fichiers, définissez les `OFN_ALLOWMULTISELECT` indicateur avant d’appeler `DoModal`. Vous devez fournir votre propre tampon du nom de fichier pour prendre en charge de la liste renvoyée de plusieurs noms de fichiers. Cela en remplaçant `m_ofn.lpstrFile` avec un pointeur vers une mémoire tampon vous avez alloué, après avoir construit le `CFileDialog`, mais avant d’appeler `DoModal`.  
  
 En outre, vous devez définir `m_ofn.nMaxFile` en utilisant le nombre de caractères dans la mémoire tampon pointée par `m_ofn.lpstrFile`. Si vous définissez le nombre maximal de fichiers pour `n`, la taille de la mémoire tampon requise est `n * (_MAX_PATH + 1) + 1`. Le premier élément retourné dans la mémoire tampon est le chemin d’accès au dossier dans lequel les fichiers ont été sélectionnés. Pour [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]-boîtes de dialogue, les chaînes de nom de fichier et de répertoire sont nul, avec un caractère null supplémentaire après le dernier nom de fichier. Ce format permet les boîtes de dialogue de style Explorateur retourner les noms de fichiers longs qui comprennent des espaces. Pour les boîtes de dialogue de l’ancienne, les chaînes de nom de fichier et de répertoire sont séparés par des espaces, et la fonction utilise les noms de fichiers courts pour les noms de fichier avec des espaces.  
  
 L’exemple suivant montre comment utiliser une mémoire tampon pour récupérer et de répertorier plusieurs noms de fichiers.  
  
 [!code-cpp[NVC_MFCFiles n °&23;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 Pour modifier la taille du tampon en réponse à l’utilisateur de sélectionner plusieurs noms de fichiers, vous devez dériver une nouvelle classe à partir de `CFileDialog` et remplacez le [CFileDialog::OnFileNameChange](#onfilenamechange) (méthode).  
  
 Si vous dérivez une nouvelle classe à partir de `CFileDialog`, vous pouvez utiliser une table des messages pour traiter les messages. Pour étendre le traitement du message par défaut, dérivez une classe de `CFileDialog`, ajouter une table des messages à la nouvelle classe et fournissent des fonctions membres pour les nouveaux messages. Vous n’avez pas à fournir une fonction de raccordement pour personnaliser la boîte de dialogue.  
  
 Pour personnaliser la boîte de dialogue, dérivez une classe de `CFileDialog`, fournir un modèle de boîte de dialogue personnalisée et ajouter une table des messages pour traiter les messages de notification à partir de contrôles étendus. Passer les messages non traités à la classe de base. Vous n’avez pas à personnaliser la fonction de raccordement.  
  
 Lorsque vous utilisez la [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] le style de la `CFileDialog`, vous ne pouvez pas utiliser les tables des messages et les modèles de boîte de dialogue. Au lieu de cela, vous devez utiliser les interfaces COM pour une fonctionnalité similaire.  
  
 Pour plus d’informations sur l’utilisation de `CFileDialog`, consultez [Classes de](../../mfc/common-dialog-classes.md).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFileDialog`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxdlgs.h  
  
##  <a name="a-nameaddcheckbuttona--cfiledialogaddcheckbutton"></a><a name="addcheckbutton"></a>CFileDialog::AddCheckButton  
 Ajoute un bouton de vérification de la boîte de dialogue.  
  
```  
HRESULT AddCheckButton(
    DWORD dwIDCtl,  
    const CString& strLabel,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la coche à ajouter.  
  
 `strLabel`  
 Le nom du contrôle bouton.  
  
 `bChecked`  
 Valeur booléenne indiquant l’état actuel de la case. `TRUE`Si elle est activée ; `FALSE` dans le cas contraire  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameaddcomboboxa--cfiledialogaddcombobox"></a><a name="addcombobox"></a>CFileDialog::AddComboBox  
 Ajoute une zone de liste déroulante de la boîte de dialogue.  
  
```  
HRESULT AddComboBox(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la zone de liste déroulante à ajouter.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameaddcontrolitema--cfiledialogaddcontrolitem"></a><a name="addcontrolitem"></a>CFileDialog::AddControlItem  
 Ajoute un élément à un contrôle conteneur dans la boîte de dialogue.  
  
```  
HRESULT AddControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle conteneur à ajouter l’élément.  
  
 `dwIDItem`  
 L’ID de l’élément.  
  
 `strLabel`  
 Texte de l’élément.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameaddeditboxa--cfiledialogaddeditbox"></a><a name="addeditbox"></a>CFileDialog::AddEditBox  
 Ajoute une zone d’édition à la boîte de dialogue.  
  
```  
HRESULT AddEditBox(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la zone d’édition à ajouter.  
  
 `strText`  
 Le nom de la modifier.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameaddmenua--cfiledialogaddmenu"></a><a name="addmenu"></a>CFileDialog::AddMenu  
 Ajoute un menu dans la boîte de dialogue.  
  
```  
HRESULT AddMenu(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du menu à ajouter.  
  
 `strLabel`  
 Le nom de menu.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameaddplacea--cfiledialogaddplace"></a><a name="addplace"></a>CFileDialog::AddPlace  
 Ajoute qu'un dossier à la liste des places disponible pour l’utilisateur à ouvrir ou enregistrer des éléments.  
  
```  
void AddPlace(
    LPCWSTR lpszFolder,  
    FDAP fdap = FDAP_TOP) throw();

 
void AddPlace(
    IShellItem* psi,  
    FDAP fdap = FDAP_TOP) throw();
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszFolder`  
 Un chemin d’accès au dossier à disposition à l’utilisateur. Cela ne peut être un dossier.  
  
 `fdap`  
 Spécifie où le dossier est placé dans la liste.  
  
 `psi`  
 Pointeur vers une instance de IShellItem qui représente le dossier à disposition à l’utilisateur. Cela ne peut être un dossier.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameaddpushbuttona--cfiledialogaddpushbutton"></a><a name="addpushbutton"></a>CFileDialog::AddPushButton  
 Ajoute un bouton à la boîte de dialogue.  
  
```  
HRESULT AddPushButton(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du bouton Ajouter.  
  
 `strLabel`  
 Le nom du bouton.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameaddradiobuttonlista--cfiledialogaddradiobuttonlist"></a><a name="addradiobuttonlist"></a>CFileDialog::AddRadioButtonList  
 Ajoute un groupe d’options (également appelé bouton radio) dans la boîte de dialogue.  
  
```  
HRESULT AddRadioButtonList(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID du groupe de bouton d’option à ajouter.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameaddseparatora--cfiledialogaddseparator"></a><a name="addseparator"></a>CFileDialog::AddSeparator  
 Ajoute un séparateur à la boîte de dialogue.  
  
```  
HRESULT AddSeparator(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 Ajout de l’ID du séparateur.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameaddtexta--cfiledialogaddtext"></a><a name="addtext"></a>CFileDialog::AddText  
 Ajoute du texte à la boîte de dialogue.  
  
```  
HRESULT AddText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du texte à ajouter.  
  
 `strText`  
 Le nom de texte.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameapplyofntoshelldialoga--cfiledialogapplyofntoshelldialog"></a><a name="applyofntoshelldialog"></a>CFileDialog::ApplyOFNToShellDialog  
 Met à jour l’état actuel de la [CFileDialog](../../mfc/reference/cfiledialog-class.md) basées sur les valeurs stockées dans le `m_ofn` structure de données.  
  
```  
void ApplyOFNToShellDialog();
```  
  
### <a name="remarks"></a>Remarques  
 Dans les versions de Windows antérieures à [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], le membre [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx) structure de données a été soit constamment synchronisée avec l’état de la `CFileDialog`. Les modifications apportées à la [m_ofn](#m_ofn) variable de membre sont immédiatement répercutées dans l’état de la boîte de dialogue. En outre, toute modification apportée à l’état de la boîte de dialogue Mettre à jour immédiatement la `m_ofn` variable membre.  
  
 Dans [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], les valeurs dans le `m_ofn` variable de membre et l’état de la `CFileDialog` n’est pas garanti pour être synchronisé. Cette fonction oblige l’état de la `CFileDialog` mise à jour pour correspondre à la `m_ofn` structure. Windows appelle cette fonction automatiquement lors de la [CFileDialog::DoModal](#domodal).  
  
 Pour plus d’informations sur l’utilisation de la `CFileDialog` classe sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], consultez [classe CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog).  
  
##  <a name="a-namecfiledialoga--cfiledialogcfiledialog"></a><a name="cfiledialog"></a>CFileDialog::CFileDialog  
 Appelez cette fonction pour construire une boîte de dialogue Windows standard.  
  
```  
explicit CFileDialog(
    BOOL bOpenFileDialog,  
    LPCTSTR lpszDefExt = NULL,  
    LPCTSTR lpszFileName = NULL,  
    DWORD dwFlags = OFN_HIDEREADONLY | OFN_OVERWRITEPROMPT,  
    LPCTSTR lpszFilter = NULL,  
    CWnd* pParentWnd = NULL,  
    DWORD dwSize = 0,  
    BOOL bVistaStyle = TRUE);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `bOpenFileDialog`  
 Le paramètre qui spécifie le type de boîte de dialogue pour créer. Affectez-lui la valeur `TRUE` pour construire un **ouvrir le fichier** boîte de dialogue. Affectez-lui la valeur `FALSE` pour construire un **enregistrer le fichier sous** boîte de dialogue.  
  
 [in] `lpszDefExt`  
 Extension de nom de fichier par défaut. Si l’utilisateur n’inclut pas d’extension connue (une association sur l’ordinateur de l’utilisateur) dans la zone Nom de fichier, l’extension spécifiée par `lpszDefExt` est automatiquement ajouté au nom du fichier. Si ce paramètre est `NULL`, aucune extension n’est ajoutée.  
  
 [in] `lpszFileName`  
 Le nom de fichier initial qui s’affiche dans la zone Nom de fichier. Si `NULL`, aucun nom de fichier initial s’affiche.  
  
 [in] `dwFlags`  
 Une combinaison d’un ou plusieurs indicateurs que vous pouvez utiliser pour personnaliser la boîte de dialogue. Pour obtenir une description de ces indicateurs, consultez la [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)]. Si vous modifiez le `m_ofn.Flags` membre de structure, d’utiliser un opérateur de bits OR dans les changements pour préserver le comportement par défaut.  
  
 [in] `lpszFilter`  
 Une série de paires de chaînes qui spécifient des filtres que vous pouvez appliquer au fichier. Si vous spécifiez des filtres de fichiers, uniquement les fichiers qui correspondent aux critères de filtre s’affichent dans la liste de fichiers. Consultez la section Notes pour plus d’informations sur l’utilisation des filtres de fichiers.  
  
 [in] `pParentWnd`  
 Pointeur vers la fenêtre parente ou propriétaire de la boîte de dialogue de fichier.  
  
 [in] `dwSize`  
 La taille de la `OPENFILENAME` structure. Cette valeur dépend de la version du système d’exploitation. MFC utilisé ce paramètre pour déterminer le type approprié de la boîte de dialogue Créer (par exemple, les nouveaux [!INCLUDE[Win2kFamily](../../c-runtime-library/includes/win2kfamily_md.md)] boîtes de dialogue au lieu de boîtes de dialogue NT4). La taille par défaut de 0 signifie que le code MFC déterminent la taille de la boîte de dialogue correct à utiliser en fonction de la version du système d’exploitation sur lequel le programme est exécuté.  
  
 [in] `bVistaStyle`  
 **Remarque** ce paramètre est disponible dans Visual Studio 2008 et versions ultérieures et elle va entraîner la boîte de dialogue Nouveau style à utiliser uniquement si vous êtes en [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] ou version ultérieure.  
  
 Le paramètre qui spécifie le style de la boîte de dialogue fichier. Affectez-lui la valeur `TRUE` à utiliser les nouvelles boîtes de dialogue fichier de style Vista. Dans le cas contraire, l’ancien style des boîtes de dialogue servira. Consultez la section Notes pour plus d’informations en cours d’exécution sous Vista.  
  
### <a name="remarks"></a>Notes  
 Soit un **ouvrir le fichier** ou **enregistrer le fichier sous** boîte de dialogue est construite, selon la valeur de `bOpenFileDialog`.  
  
 Spécification d’une extension par défaut à l’aide `lpszDefExt` peut ne pas produire le comportement que vous attendez, car il est rarement prévisibles les extensions ont des associations de fichiers sur l’ordinateur de l’utilisateur. Si vous avez besoin de davantage de contrôle sur l’ajout d’une extension par défaut, vous pouvez dériver votre propre classe de `CFileDialog`et remplacez le `CFileDialog::OnFileNameOK` méthode pour effectuer votre propre gestion de l’extension.  
  
 Pour permettre à l’utilisateur de sélectionner plusieurs fichiers, définissez les `OFN_ALLOWMULTISELECT` indicateur avant d’appeler [DoModal](#domodal). Vous devez fournir votre propre tampon du nom de fichier pour stocker la liste des noms de fichier multiples renvoyée. Cela en remplaçant `m_ofn.lpstrFile` avec un pointeur vers une mémoire tampon vous avez alloué, après avoir construit le [CFileDialog](../../mfc/reference/cfiledialog-class.md), mais avant d’appeler `DoModal`. En outre, vous devez définir `m_ofn.nMaxFile` avec le nombre de caractères dans la mémoire tampon pointée par `m_ofn.lpstrFile`. Si vous définissez le nombre maximal de fichiers pour `n`, la taille de mémoire tampon nécessaire est `n`*(_MAX_PATH + 1) + 1. Exemple :  
  
 [!code-cpp[NVC_MFCFiles n °&23;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_1.cpp)]  
  
 Pour permettre à l’utilisateur de redimensionner une boîte de dialogue de style Internet Explorer à l’aide de la souris ou du clavier, définissez la `OFN_ENABLESIZING` indicateur. Définition de cet indicateur est uniquement nécessaire si vous fournissez une procédure de raccordement ou d’un modèle personnalisé. L’indicateur fonctionne uniquement avec une boîte de dialogue Explorer-style ; boîtes de dialogue de l’ancienne ne peut pas être redimensionnés.  
  
 Le `lpszFilter` paramètre est utilisé pour déterminer le type d’un fichier doit avoir pour être affiché dans la liste des fichiers de nom de fichier. La première chaîne de la paire de chaîne décrit le filtre ; la deuxième chaîne indique l’extension de nom de fichier à utiliser. Plusieurs extensions peuvent être spécifiées à l’aide d’un point-virgule (le caractère « ; ») comme délimiteur. La chaîne se termine par deux ' |' caractères, suivi d’une `NULL` caractère. Vous pouvez également utiliser un [CString](../../atl-mfc-shared/using-cstring.md) objet pour ce paramètre.  
  
 Par exemple, [!INCLUDE[ofprexcel](../../mfc/reference/includes/ofprexcel_md.md)] permet aux utilisateurs d’ouvrir des fichiers qui ont des extensions .xlc (graphique) ou .xls (feuille de calcul), entre autres. Le filtre pour Excel peut être écrit comme suit :  
  
 [!code-cpp[NVC_MFCFiles&#24;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_2.cpp)]  
  
 Toutefois, si vous prévoyez d’utiliser cette chaîne directement mettre à jour le `OPENFILENAME` structure, vous devez délimiter vos chaînes avec le caractère null, « \0 », au lieu de barres verticales (« | »).  
  
 Le `bVistaStyle` paramètre s’applique uniquement lors de l’exécution sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]. Dans les versions antérieures de Windows, ce paramètre est ignoré. Si `bVistaStyle` a `TRUE`, lorsque vous compilez un programme avec [!INCLUDE[vs_orcas_long](../../atl/reference/includes/vs_orcas_long_md.md)] ou version ultérieure, le nouveau style Vista **boîte de dialogue fichier** sera utilisé. Dans le cas contraire, le style MFC précédent **boîte de dialogue fichier** sera utilisé.  
  
 Modèles de boîte de dialogue ne sont pas pris en charge basée sur des boîtes de dialogue`bVistaStyle`  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileDialog::DoModal](#domodal).  
  
##  <a name="a-namedomodala--cfiledialogdomodal"></a><a name="domodal"></a>CFileDialog::DoModal  
 Appelez cette fonction pour afficher la boîte de dialogue Fichier commune Windows et autoriser l’utilisateur à parcourir les fichiers et répertoires et entrez un nom de fichier.  
  
```  
virtual INT_PTR DoModal();
```  
  
### <a name="return-value"></a>Valeur de retour  
 **IDOK** ou **IDCANCEL**. Si **IDCANCEL** est retourné, appelez Windows [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) fonction pour déterminer si une erreur s’est produite.  
  
 **IDOK** et **IDCANCEL** sont des constantes qui indiquent si l’utilisateur a sélectionné le bouton OK ou annuler.  
  
### <a name="remarks"></a>Notes  
 Si vous souhaitez initialiser les diverses options de la boîte de dialogue de fichier en définissant les membres de la **m_ofn** structure, vous devez le faire avant d’appeler `DoModal`, mais une fois que l’objet de la boîte de dialogue est construit.  
  
 Par exemple, si vous souhaitez autoriser l’utilisateur à sélectionner plusieurs fichiers, définissez les `OFN_ALLOWMULTISELECT` indicateur avant d’appeler `DoModal`, comme illustré dans l’exemple de code dans cette rubrique.  
  
 Lorsque l’utilisateur clique sur les boutons OK ou annuler la boîte de dialogue, ou sélectionne la fermeture d’option à partir de la boîte de dialogue contrôle de menu, le contrôle est renvoyé à votre application. Vous pouvez ensuite appeler les autres fonctions membres pour récupérer les paramètres ou les informations entrées utilisateur dans la boîte de dialogue.  
  
 `DoModal`est une fonction virtuelle substituée à partir de la classe `CDialog`.  
  
### <a name="example"></a>Exemple  
 [!code-cpp[NVC_MFCFiles&#25;](../../atl-mfc-shared/reference/codesnippet/cpp/cfiledialog-class_3.cpp)]  
  
##  <a name="a-nameenableopendropdowna--cfiledialogenableopendropdown"></a><a name="enableopendropdown"></a>CFileDialog::EnableOpenDropDown  
 Active la liste déroulante à l’ouverture ou de bouton dans la boîte de dialogue Enregistrer.  
  
```  
HRESULT EnableOpenDropDown(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la liste déroulante.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameendvisualgroupa--cfiledialogendvisualgroup"></a><a name="endvisualgroup"></a>CFileDialog::EndVisualGroup  
 Arrête l’ajout d’éléments à un groupe visuel dans la boîte de dialogue.  
  
```  
HRESULT EndVisualGroup();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK si l’opération a réussi ; une valeur d’erreur dans le cas contraire.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetcheckbuttonstatea--cfiledialoggetcheckbuttonstate"></a><a name="getcheckbuttonstate"></a>CFileDialog::GetCheckButtonState  
 Récupère l’état actuel d’un bouton de vérification (case à cocher) dans la boîte de dialogue.  
  
```  
HRESULT GetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL& bChecked);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la case à cocher.  
  
 `bChecked`  
 L’état de la case à cocher. `TRUE`Indique activé ; `FALSE` indique est désactivée.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namegetcontrolitemstatea--cfiledialoggetcontrolitemstate"></a><a name="getcontrolitemstate"></a>CFileDialog::GetControlItemState  
 Récupère l’état actuel d’un élément dans un contrôle conteneur dans la boîte de dialogue.  
  
```  
HRESULT GetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle conteneur.  
  
 `dwIDItem`  
 L’ID de l’élément.  
  
 `dwState`  
 Une référence à une variable qui reçoit un des plus de valeurs de l’énumération CDCONTROLSTATE qui indique l’état actuel du contrôle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetcontrolstatea--cfiledialoggetcontrolstate"></a><a name="getcontrolstate"></a>CFileDialog::GetControlState  
 Récupère la visibilité et activé les États d’un contrôle donné.  
  
```  
HRESULT GetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF& dwState);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle.  
  
 `dwState`  
 Une référence à une variable qui reçoit une ou plusieurs valeurs de l’énumération CDCONTROLSTATE qui indique l’état actuel du contrôle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegeteditboxtexta--cfiledialoggeteditboxtext"></a><a name="geteditboxtext"></a>CFileDialog::GetEditBoxText  
 Extrait le texte actuel dans un contrôle de zone d’édition.  
  
```  
HRESULT GetEditBoxText(
    DWORD dwIDCtl,  
    CString& strText);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la zone d’édition.  
  
 `strText`  
 Valeur du texte.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetfileexta--cfiledialoggetfileext"></a><a name="getfileext"></a>CFileDialog::GetFileExt  
 Appelez cette fonction pour récupérer l’extension du nom de fichier entré dans la boîte de dialogue.  
  
```  
CString GetFileExt() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 L’extension du nom de fichier.  
  
### <a name="remarks"></a>Remarques  
 Par exemple, si le nom du fichier entré donnée. TXT, `GetFileExt` retourne « TXT ».  
  
 Si `m_ofn.Flags` a le `OFN_ALLOWMULTISELECT` indicateur est défini, cette chaîne contient une séquence de chaînes se terminant par null, avec la première chaîne est le chemin d’accès du groupe de fichiers sélectionné, suivie des noms de tous les fichiers sélectionnés par l’utilisateur. Pour récupérer les chemins d’accès de fichier, utilisez la [GetStartPosition](#getstartposition) et [GetNextPathName](#getnextpathname) les fonctions membres.  
  
##  <a name="a-namegetfilenamea--cfiledialoggetfilename"></a><a name="getfilename"></a>CFileDialog::GetFileName  
 Appelez cette fonction pour récupérer le nom de fichier entré dans la boîte de dialogue.  
  
```  
CString GetFileName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Nom du fichier.  
  
### <a name="remarks"></a>Notes  
 Le nom du fichier inclut le préfixe et l’extension. Par exemple, `GetFileName` renvoie « TEXT. DAT » pour le fichier C:\FILES\TEXT.DAT.  
  
 Si `m_ofn.Flags` a le `OFN_ALLOWMULTISELECT` l’indicateur est défini, vous devez appeler [GetStartPosition](#getstartposition) et [GetNextPathName](#getnextpathname) pour récupérer un chemin d’accès de fichier.  
  
##  <a name="a-namegetfiletitlea--cfiledialoggetfiletitle"></a><a name="getfiletitle"></a>CFileDialog::GetFileTitle  
 Appelez cette fonction pour récupérer le titre du fichier entré dans la boîte de dialogue.  
  
```  
CString GetFileTitle() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le titre du fichier.  
  
### <a name="remarks"></a>Remarques  
 Le titre du fichier inclut son préfixe uniquement, sans le chemin d’accès ou l’extension. Par exemple, `GetFileTitle` renvoie « TEXT » pour le fichier C:\FILES\TEXT.DAT.  
  
 Si `m_ofn.Flags` a le `OFN_ALLOWMULTISELECT` indicateur est défini, cette chaîne contient une séquence de chaînes se terminant par null, avec la première chaîne est le chemin d’accès du groupe de fichiers sélectionné, suivie des noms de tous les fichiers sélectionnés par l’utilisateur. Pour cette raison, utilisez la [GetStartPosition](#getstartposition) et [GetNextPathName](#getnextpathname) des fonctions membres pour récupérer le nom du fichier suivant dans la liste.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileDialog::DoModal](#domodal).  
  
##  <a name="a-namegetfolderpatha--cfiledialoggetfolderpath"></a><a name="getfolderpath"></a>CFileDialog::GetFolderPath  
 Appelez cette fonction membre pour récupérer le chemin d’accès du dossier actuellement ouvert ou du répertoire pour une boîte de dialogue commune Explorer-style ouvrir ou enregistrer sous.  
  
```  
CString GetFolderPath() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A [CString](../../atl-mfc-shared/reference/cstringt-class.md) objet contenant le dossier actuellement ouvert ou le répertoire.  
  
### <a name="remarks"></a>Notes  
 La boîte de dialogue doit avoir été créée avec le **OFN_EXPLORER** de style ; sinon, la méthode échoue avec une assertion.  
  
 Vous pouvez appeler cette méthode uniquement lorsque la boîte de dialogue est affichée. Cette fonction ne fonctionnera plus après la fermeture de la boîte de dialogue, et la méthode échoue avec une assertion.  
  
##  <a name="a-namegetifiledialogcustomizea--cfiledialoggetifiledialogcustomize"></a><a name="getifiledialogcustomize"></a>CFileDialog::GetIFileDialogCustomize  
 Récupère un pointeur vers l’objet COM interne pour une donnée [CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
```  
IFileDialogCustomize* GetIFileDialogCustomize();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le pointeur vers l’objet COM interne pour le `CFileDialog`. Il vous incombe de version appropriée de ce pointeur.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette fonction uniquement sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] avec un objet qui a `bVistaStyle` la valeur `true`. Si vous utilisez cette fonction lorsque `bVistaStyle` est `false`, elle retournera `NULL` en mode version finale et lève une assertion en mode débogage.  
  
 Pour plus d’informations sur la `IFileDialogCustomize` , consultez [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912).  
  
### <a name="example"></a>Exemple  
 Cet exemple récupère l’objet COM interne. Pour exécuter cet exemple de code, vous devez le compiler sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog n °&4;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_4.cpp)]  
  
##  <a name="a-namegetifileopendialoga--cfiledialoggetifileopendialog"></a><a name="getifileopendialog"></a>CFileDialog::GetIFileOpenDialog  
 Récupère un pointeur vers l’objet COM interne pour une donnée `CFileDialog`.  
  
```  
IFileOpenDialog* GetIFileOpenDialog();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le pointeur vers l’objet COM interne pour le `CFileDialog`. Il vous incombe de version appropriée de ce pointeur.  
  
### <a name="remarks"></a>Remarques  
 Utilisez cette fonction uniquement sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] avec un objet qui a `bVistaStyle` la valeur `true`. Cette fonction retourne `NULL` si le `CFileDialog` n’est pas un **Open** boîte de dialogue ou si `bVistaStyle` est défini sur `false`. Dans ce dernier cas, la fonction retourne uniquement `NULL` en mode release - mode débogage il lèvera une assertion.  
  
 Pour plus d’informations sur la `IFileOpenDialog` , consultez [IFileOpenDialog](http://msdn.microsoft.com/library/windows/desktop/bb775834).  
  
### <a name="example"></a>Exemple  
 Cet exemple récupère l’objet COM interne. Pour exécuter ce code, vous devez le compiler sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog n °&2;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_5.cpp)]  
  
##  <a name="a-namegetifilesavedialoga--cfiledialoggetifilesavedialog"></a><a name="getifilesavedialog"></a>CFileDialog::GetIFileSaveDialog  
 Récupère un pointeur vers l’objet COM interne pour une donnée `CFileDialog`.  
  
```  
IFileSaveDialog* GetIFileSaveDialog();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Le pointeur vers l’objet COM interne pour le `CFileDialog`. Il vous incombe de version appropriée de ce pointeur.  
  
### <a name="remarks"></a>Notes  
 Utilisez cette fonction uniquement sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] avec un objet qui a `bVistaStyle` la valeur `true`. Cette fonction retourne `NULL` si le `CFileDialog` n’est pas un **enregistrer** boîte de dialogue ou si `bVistaStyle` est défini sur `false`. Dans ce dernier cas, la fonction retourne uniquement `NULL` en mode release - mode débogage il lèvera une assertion.  
  
 Pour plus d’informations sur la `IFileSaveDialog` , consultez [IFileSaveDialog](http://msdn.microsoft.com/library/windows/desktop/bb775688).  
  
### <a name="example"></a>Exemple  
 Cet exemple récupère l’objet COM interne. Pour exécuter cet exemple de code, vous devez le compiler sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!code-cpp[NVC_MFC_CFileDialog n °&3;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_6.cpp)]  
  
##  <a name="a-namegetnextpathnamea--cfiledialoggetnextpathname"></a><a name="getnextpathname"></a>CFileDialog::GetNextPathName  
 Appelez cette fonction pour récupérer le nom du fichier suivant à partir du groupe sélectionné dans la boîte de dialogue.  
  
```  
CString GetNextPathName(POSITION& pos) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `pos`  
 Une référence à un **POSITION** valeur retournée par une précédente `GetNextPathName` ou `GetStartPosition` appel de fonction. **NULL** si la fin de la liste a été atteinte.  
  
### <a name="return-value"></a>Valeur de retour  
 Chemin d’accès complet du fichier.  
  
### <a name="remarks"></a>Remarques  
 Le chemin d’accès du nom de fichier inclut le titre du fichier ainsi que le chemin d’accès de l’intégralité de l’annuaire. Par exemple, `GetNextPathName` renvoie « C:\FILES\TEXT. DAT » pour le fichier C:\FILES\TEXT.DAT. Vous pouvez utiliser `GetNextPathName` dans une boucle d’itération en avant si vous établissez la position initiale avec un appel à `GetStartPosition`.  
  
 Si la sélection se compose d’un seul fichier, ce nom de fichier est retourné.  
  
##  <a name="a-namegetofna--cfiledialoggetofn"></a><a name="getofn"></a>CFileDialog::GetOFN  
 Récupère le texte associé **OPENFILENAME** structure.  
  
```  
const OPENFILENAME& GetOFN() const;  
  
OPENFILENAME& GetOFN();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Un [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) structure.  
  
### <a name="remarks"></a>Remarques  
 Utiliser la deuxième version de cette fonction pour initialiser l’apparence d’un **ouvrir le fichier** ou **enregistrer le fichier sous** boîte de dialogue une fois qu’il est construit mais avant qu’il est affiché avec le `DoModal` fonction membre. Par exemple, vous pouvez définir le **lpstrTitle** membre **m_ofn** la légende vous souhaitez avoir la boîte de dialogue.  
  
##  <a name="a-namegetpathnamea--cfiledialoggetpathname"></a><a name="getpathname"></a>CFileDialog::GetPathName  
 Appelez cette fonction pour récupérer le chemin d’accès complet du fichier entré dans la boîte de dialogue.  
  
```  
CString GetPathName() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Chemin d’accès complet du fichier.  
  
### <a name="remarks"></a>Remarques  
 Le chemin d’accès du nom de fichier inclut le titre du fichier ainsi que le chemin d’accès de l’intégralité de l’annuaire. Par exemple, `GetPathName` renvoie « C:\FILES\TEXT. DAT » pour le fichier C:\FILES\TEXT.DAT.  
  
 Si `m_ofn.Flags` a le `OFN_ALLOWMULTISELECT` indicateur est défini, cette chaîne contient une séquence de null-teminated chaînes, avec la première chaîne est le chemin d’accès du groupe de fichiers sélectionné, suivie des noms de tous les fichiers sélectionnés par l’utilisateur. Pour cette raison, utilisez la [GetStartPosition](#getstartposition) et [GetNextPathName](#getnextpathname) des fonctions membres pour récupérer le nom du fichier suivant dans la liste.  
  
### <a name="example"></a>Exemple  
  Consultez l’exemple de [CFileDialog::DoModal](#domodal).  
  
##  <a name="a-namegetreadonlyprefa--cfiledialoggetreadonlypref"></a><a name="getreadonlypref"></a>CFileDialog::GetReadOnlyPref  
 Appelez cette fonction pour déterminer si la case à cocher lecture seule a été sélectionnée dans les Windows ouvrir et enregistrer le fichier sous boîtes de dialogue standard.  
  
```  
BOOL GetReadOnlyPref() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Différent de zéro si la case à cocher lecture seule dans la boîte de dialogue est activée ; sinon 0.  
  
### <a name="remarks"></a>Remarques  
 Vous pouvez masquer la case à cocher lecture seule en définissant le `OFN_HIDEREADONLY` de style dans le `CFileDialog` constructeur.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]style `CFileDialog` objets ne prennent pas en charge cette fonction. Tentative d’utilisation de cette fonction sur un [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] style `CFileDialog` lèvera [exception CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md).   
  
##  <a name="a-namegetresulta--cfiledialoggetresult"></a><a name="getresult"></a>CFileDialog::GetResult  
 Récupère le choix de l’utilisateur dans la boîte de dialogue.  
  
```  
IShellItem* GetResult() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers une instance de IShellItem qui représente le choix de l’utilisateur.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetresultsa--cfiledialoggetresults"></a><a name="getresults"></a>CFileDialog::GetResults  
 Récupère le choix de l’utilisateur dans une boîte de dialogue permet la sélection multiple.  
  
```  
IShellItemArray* GetResults() throw();
```  
  
### <a name="return-value"></a>Valeur de retour  
 Pointeur vers un IShellItemArray par le biais duquel les éléments sélectionnés dans la boîte de dialogue est accessible.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetselectedcontrolitema--cfiledialoggetselectedcontrolitem"></a><a name="getselectedcontrolitem"></a>CFileDialog::GetSelectedControlItem  
 Récupère un élément particulier du contrôle conteneur spécifié dans la boîte de dialogue.  
  
```  
HRESULT GetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD& dwIDItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle conteneur.  
  
 `dwIDItem`  
 L’ID de l’élément sélectionné par l’utilisateur dans le contrôle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namegetstartpositiona--cfiledialoggetstartposition"></a><a name="getstartposition"></a>CFileDialog::GetStartPosition  
 Appelez cette fonction membre pour récupérer la position du premier chemin d’accès de fichier dans la liste, si `m_ofn.Flags` a le `OFN_ALLOWMULTISELECT` l’indicateur est défini.  
  
```  
POSITION GetStartPosition() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 A **POSITION** valeur qui peut être utilisé pour l’itération ; **NULL** si la liste est vide.  
  
##  <a name="a-namehidecontrola--cfiledialoghidecontrol"></a><a name="hidecontrol"></a>CFileDialog::HideControl  
 Appelez cette fonction membre pour masquer le contrôle spécifié dans la boîte de dialogue commune Explorer-style ouvrir ou enregistrer sous.  
  
```  
void HideControl(int nID);
```  
  
### <a name="parameters"></a>Paramètres  
 `nID`  
 L’ID du contrôle à masquer.  
  
### <a name="remarks"></a>Remarques  
 La boîte de dialogue doit avoir été créée avec le **OFN_EXPLORER** de style ; sinon, la fonction échoue avec une assertion.  
  
##  <a name="a-nameispickfoldersmodea--cfiledialogispickfoldersmode"></a><a name="ispickfoldersmode"></a>CFileDialog::IsPickFoldersMode  
 Détermine si la boîte de dialogue en cours est en mode de sélecteur de dossier.  
  
```  
BOOL IsPickFoldersMode() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 `TRUE`Si la boîte de dialogue est en mode de sélecteur de dossier ; dans le cas contraire `FALSE`.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namemofna--cfiledialogmofn"></a><a name="m_ofn"></a>CFileDialog::m_ofn  
 `m_ofn`est une structure de type `OPENFILENAME`. Les données de cette structure représentent l’état actuel de la `CFileDialog`.  
  
### <a name="remarks"></a>Remarques  
 Cette structure permet d’initialiser l’apparence d’un **ouvrir le fichier** ou **enregistrer le fichier sous** boîte de dialogue après avoir il construit mais avant de les afficher avec la [DoModal](#domodal) (méthode). Par exemple, vous pouvez définir le `lpstrTitle` membre `m_ofn` la légende vous souhaitez avoir la boîte de dialogue.  
  
 Avec le [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] style de [CFileDialog](../../mfc/reference/cfiledialog-class.md), `m_ofn` n’est pas garantie toujours correspondre à l’état de la boîte de dialogue. Il est synchronisé avec la boîte de dialogue dans les versions antérieures de Windows. Consultez [CFileDialog::ApplyOFNToShellDialog](#applyofntoshelldialog) et [CFileDialog::UpdateOFNFromShellDialog](#updateofnfromshelldialog) pour plus d’informations sur la synchronisation de la `m_ofn` structure et `CFileDialog` état sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  
  
 [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]boîtes de dialogue de fichier style ne gèrent pas certains membres et les indicateurs de le `CFileDialog`. Par conséquent, il aura aucun effet.  
  
 Voici une liste des membres qui ne sont pas pris en charge par [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
- `lpstrCustomFilter`  
  
- `lpstrInitialDir`  
  
- `lCustData`  
  
- `lpfnHook`  
  
- `lpTemplateName`  
  
 Les indicateurs suivants ne sont pas prises en charge et n’ont donc aucun effet lorsque vous utilisez la [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] style de `CFileDialog`:  
  
-   OFN_ENABLEHOOK  
  
-   OFN_ENABLEINCLUDENOTIFY  
  
-   OFN_ENABLETEMPLATE  
  
-   OFN_ENABLETEMPLATEHANDLE  
  
-   OFN_EXPLORER  
  
-   OFN_EXTENSIONDIFFERENT  
  
-   OFN_HIDEREADONLY  
  
-   OFN_LONGNAMES - efficacement toujours sur dans[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NOLONGNAMES - efficacement toujours désactivée dans[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_NONETWORKBUTTON - efficacement toujours sur dans[!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
-   OFN_READONLY  
  
-   OFN_SHOWHELP  
  
 Pour plus d’informations sur cette structure, consultez la [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) de la structure dans le [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
##  <a name="a-namemakeprominenta--cfiledialogmakeprominent"></a><a name="makeprominent"></a>CFileDialog::MakeProminent  
 Place un contrôle dans la boîte de dialogue afin qu’il soit comparé à d’autres contrôles.  
  
```  
HRESULT MakeProminent(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonbuttonclickeda--cfiledialogonbuttonclicked"></a><a name="onbuttonclicked"></a>CFileDialog::OnButtonClicked  
 Appelé lorsque le bouton est activé.  
  
```  
virtual void OnButtonClicked(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du bouton.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameoncheckbuttontoggleda--cfiledialogoncheckbuttontoggled"></a><a name="oncheckbuttontoggled"></a>CFileDialog::OnCheckButtonToggled  
 Appelé lorsque la case à cocher est activée ou désactivée.  
  
```  
virtual void OnCheckButtonToggled(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la case à cocher.  
  
 `bChecked`  
 Activé ou désactivé.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameoncontrolactivatinga--cfiledialogoncontrolactivating"></a><a name="oncontrolactivating"></a>CFileDialog::OnControlActivating  
 Appelée lorsque le contrôle est activé.  
  
```  
virtual void OnControlActivating(DWORD dwIDCtl);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameonfilenamechangea--cfiledialogonfilenamechange"></a><a name="onfilenamechange"></a>CFileDialog::OnFileNameChange  
 Substituez cette méthode si vous souhaitez gérer les `WM_NOTIFY``CDN_SELCHANGE` message.  
  
```  
virtual void OnFileNameChange();
```  
  
### <a name="remarks"></a>Remarques  
 Le système envoie la `CDN_SELCHANGE` de message lorsque l’utilisateur sélectionne un nouveau fichier ou un dossier dans la liste des fichiers de la **Open** ou **Enregistrer sous** boîte de dialogue. Substituez cette méthode si vous souhaitez effectuer des actions en réponse à ce message.  
  
 Le système envoie le message uniquement si la boîte de dialogue a été créée avec l’indicateur OFN_EXPLORER sous tension. Pour plus d’informations sur la notification, consultez [CDN_SELCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646865). Pour plus d’informations sur l’indicateur OFN_EXPLORER, consultez la [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) structure et [ouvrir et enregistrer en tant que boîtes de dialogue](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="a-nameonfilenameoka--cfiledialogonfilenameok"></a><a name="onfilenameok"></a>CFileDialog::OnFileNameOK  
 Remplacez cette fonction uniquement si vous souhaitez fournir une validation personnalisée des noms de fichiers qui sont entrés dans la boîte de dialogue de fichier courante.  
  
```  
virtual BOOL OnFileNameOK();
```  
  
### <a name="return-value"></a>Valeur de retour  
 1 si le nom de fichier n’est pas un nom de fichier valide ; sinon 0.  
  
### <a name="remarks"></a>Notes  
 Cette fonction vous permet de rejeter un nom de fichier pour une raison quelconque spécifiques à l’application. En règle générale, il est inutile d’utiliser cette fonction, car l’infrastructure fournit la validation des noms de fichiers par défaut et affiche un message si un nom de fichier non valide est entré.  
  
 Si 1 est retournée, la boîte de dialogue reste affichée pour l’utilisateur à entrer un autre nom. La procédure de la boîte de dialogue ferme la boîte de dialogue si la valeur de retour est 0. Autres différente de zéro valeurs de retour sont actuellement réservées et ne doivent pas être utilisés.  
  
##  <a name="a-nameonfolderchangea--cfiledialogonfolderchange"></a><a name="onfolderchange"></a>CFileDialog::OnFolderChange  
 Remplacez cette fonction pour traiter les **WM_NOTIFYCDN_FOLDERCHANGE** message.  
  
```  
virtual void OnFolderChange();
```  
  
### <a name="remarks"></a>Remarques  
 Le message de notification est envoyé lorsqu’un nouveau dossier est ouvert dans la boîte de dialogue Ouvrir ou enregistrer sous.  
  
 Notification est envoyée uniquement si la boîte de dialogue a été créée avec le style OFN_EXPLORER. Pour plus d’informations sur la notification, consultez [CDN_FOLDERCHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646859). Pour plus d’informations sur le style OFN_EXPLORER, consultez la [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) structure et [ouvrir et enregistrer en tant que boîtes de dialogue](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="a-nameoninitdonea--cfiledialogoninitdone"></a><a name="oninitdone"></a>CFileDialog::OnInitDone  
 Remplacez cette fonction pour gérer les `WM_NOTIFY``CDN_INITDONE` message.  
  
```  
virtual void OnInitDone();
```  
  
### <a name="remarks"></a>Notes  
 Le système envoie ce message de notification lorsque le système a terminé la disposition des contrôles dans les **Open** ou **Enregistrer sous** boîte de dialogue pour faire de la place pour les contrôles de la boîte de dialogue enfant.  
  
 Le système envoie uniquement si la boîte de dialogue a été créée avec le style OFN_EXPLORER. Pour plus d’informations sur la notification, consultez [CDN_INITDONE](http://msdn.microsoft.com/library/windows/desktop/ms646863). Pour plus d’informations sur le style OFN_EXPLORER, consultez la [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) structure et [ouvrir et enregistrer en tant que boîtes de dialogue](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]boîtes de dialogue de fichier style ne gèrent pas cette fonction. Tentative d’utilisation de cette fonction sur un [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] boîte de dialogue de fichier style lève [exception CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md). 
  
##  <a name="a-nameonitemselecteda--cfiledialogonitemselected"></a><a name="onitemselected"></a>CFileDialog::OnItemSelected  
 Appelé lorsque l’élément conteneur est sélectionné.  
  
```  
virtual void OnItemSelected(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle conteneur.  
  
 `dwIDItem`  
 L’ID de l’élément.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-nameonlbselchangednotifya--cfiledialogonlbselchangednotify"></a><a name="onlbselchangednotify"></a>CFileDialog::OnLBSelChangedNotify  
 Cette fonction est appelée chaque fois que la sélection actuelle dans une zone de liste est sur le point de changer.  
  
```  
virtual void OnLBSelChangedNotify(
    UINT nIDBox,  
    UINT iCurSel,  
    UINT nCode);
```  
  
### <a name="parameters"></a>Paramètres  
 *nIDBox*  
 ID de la zone de liste ou zone de liste déroulante dans laquelle la sélection s’est produite.  
  
 `iCurSel`  
 L’index de la sélection actuelle.  
  
 `nCode`  
 Le code de notification de contrôle. Ce paramètre doit avoir une des valeurs suivantes :  
  
- **CD_LBSELCHANGE** spécifie `iCurSel` est l’élément sélectionné dans une zone de liste à sélection unique.  
  
- **CD_LBSELSUB** Spécifie que `iCurSel` n’est plus sélectionné dans une zone de liste à sélection multiple.  
  
- **CD_LBSELADD** Spécifie que `iCurSel` est sélectionné dans une zone de liste à sélection multiple.  
  
- **CD_LBSELNOITEMS** Spécifie qu’aucune sélection n’existe dans une zone de liste à sélection multiple.  
  
### <a name="remarks"></a>Notes  
 Remplacez cette fonction pour fournir une gestion personnalisée des modifications de sélection dans la zone de liste. Par exemple, vous pouvez utiliser cette fonction pour afficher les droits d’accès ou date-last-modified de chaque fichier de l’utilisateur sélectionne.  
  
##  <a name="a-nameonshareviolationa--cfiledialogonshareviolation"></a><a name="onshareviolation"></a>CFileDialog::OnShareViolation  
 Remplacez cette fonction pour fournir la gestion personnalisée des violations de partage.  
  
```  
virtual UINT OnShareViolation(LPCTSTR lpszPathName);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPathName`  
 Le chemin d’accès du fichier sur lequel la violation de partage s’est produite.  
  
### <a name="return-value"></a>Valeur de retour  
 Une des valeurs suivantes :  
  
- **OFN_SHAREFALLTHROUGH** le nom de fichier est retourné à partir de la boîte de dialogue.  
  
- **OFN_SHARENOWARN** aucune action supplémentaire ne doit être prise.  
  
- **OFN_SHAREWARN** l’utilisateur reçoit le message d’avertissement standard pour cette erreur.  
  
### <a name="remarks"></a>Notes  
 En règle générale, il est inutile d’utiliser cette fonction, car l’infrastructure fournit la vérification des violations de partage par défaut et affiche un message si une violation de partage se produit.  
  
 Si vous souhaitez désactiver la vérification de violation de partage, utilisez l’opérateur OR pour combiner l’indicateur **OFN_SHAREAWARE** avec `m_ofn.Flags`.  
  
##  <a name="a-nameontypechangea--cfiledialogontypechange"></a><a name="ontypechange"></a>CFileDialog::OnTypeChange  
 Remplacez cette fonction pour traiter les **WM_NOTIFYCDN_TYPECHANGE** message.  
  
```  
virtual void OnTypeChange();
```  
  
### <a name="remarks"></a>Notes  
 Le message de notification est envoyé lorsque l’utilisateur sélectionne un nouveau type de fichier dans la liste des types de fichiers dans l’ouverture ou de la boîte de dialogue Enregistrer sous.  
  
 Notification est envoyée uniquement si la boîte de dialogue a été créée avec le style OFN_EXPLORER. Pour plus d’informations sur la notification, consultez [CDN_TYPECHANGE](http://msdn.microsoft.com/library/windows/desktop/ms646868). Pour plus d’informations sur le style OFN_EXPLORER, consultez la [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) structure et [ouvrir et enregistrer en tant que boîtes de dialogue](http://msdn.microsoft.com/library/windows/desktop/ms646960).  
  
##  <a name="a-nameremovecontrolitema--cfiledialogremovecontrolitem"></a><a name="removecontrolitem"></a>CFileDialog::RemoveControlItem  
 Supprime un élément d’un contrôle conteneur dans la boîte de dialogue.  
  
```  
HRESULT RemoveControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID du contrôle conteneur à supprimer l’élément.  
  
 `dwIDItem`  
 L’ID de l’élément.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetcheckbuttonstatea--cfiledialogsetcheckbuttonstate"></a><a name="setcheckbuttonstate"></a>CFileDialog::SetCheckButtonState  
 Définit l’état actuel d’un bouton de vérification (case à cocher) dans la boîte de dialogue.  
  
```  
HRESULT SetCheckButtonState(
    DWORD dwIDCtl,  
    BOOL bChecked);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la case à cocher.  
  
 `bChecked`  
 L’état de la case à cocher. `TRUE`Indique activé ; `FALSE` indique non cochée.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetcontrolitemstatea--cfiledialogsetcontrolitemstate"></a><a name="setcontrolitemstate"></a>CFileDialog::SetControlItemState  
 Définit l’état actuel d’un élément dans un contrôle conteneur dans la boîte de dialogue.  
  
```  
HRESULT SetControlItemState(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle conteneur.  
  
 `dwIDItem`  
 L’ID de l’élément.  
  
 `dwState`  
 Une ou plusieurs valeurs de l’énumération CDCONTROLSTATE qui indiquent le nouvel état du contrôle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetcontrolitemtexta--cfiledialogsetcontrolitemtext"></a><a name="setcontrolitemtext"></a>CFileDialog::SetControlItemText  
 Définit le texte d’un élément de contrôle. Par exemple, le texte qui accompagne une case d’option ou un élément dans un menu.  
  
```  
HRESULT SetControlItemText(
    DWORD dwIDCtl,  
    DWORD dwIDItem,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle conteneur.  
  
 `dwIDItem`  
 L’ID de l’élément.  
  
 `strLabel`  
 Texte de l’élément.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetcontrollabela--cfiledialogsetcontrollabel"></a><a name="setcontrollabel"></a>CFileDialog::SetControlLabel  
 Définit le texte associé à un contrôle, telles que le texte du bouton ou une étiquette de la zone Modifier.  
  
```  
HRESULT SetControlLabel(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle.  
  
 `strLabel`  
 Le nom du contrôle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetcontrolstatea--cfiledialogsetcontrolstate"></a><a name="setcontrolstate"></a>CFileDialog::SetControlState  
 Définit la visibilité et activé les États d’un contrôle donné.  
  
```  
HRESULT SetControlState(
    DWORD dwIDCtl,  
    CDCONTROLSTATEF dwState);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle.  
  
 `dwState`  
 Une ou plusieurs valeurs de l’énumération CDCONTROLSTATE qui indiquent l’état actuel du contrôle.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetcontroltexta--cfiledialogsetcontroltext"></a><a name="setcontroltext"></a>CFileDialog::SetControlText  
 Appelez cette méthode pour définir le texte pour le contrôle spécifié dans un style Explorateur **Open** ou **Enregistrer sous** boîte de dialogue.  
  
```  
void SetControlText(
    int nID,  
    LPCSTR lpsz);

 
void SetControlText(
    int nID,  
    const wchar_t *lpsz);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nID`  
 L’ID du contrôle pour lequel définir le texte.  
  
 [in] `lpsz`  
 Pointeur vers la chaîne qui contient le texte à définir pour le contrôle.  
  
### <a name="remarks"></a>Remarques  
 Les deux versions de cette fonction sont valides pour les applications qui utilisent Unicode. Toutefois, seule la version avec le type LPCSTR est valide pour les applications qui utilisent [!INCLUDE[vcpransi](../../atl-mfc-shared/reference/includes/vcpransi_md.md)].  
  
 Pour utiliser cette méthode, vous devez créer la boîte de dialogue avec le style OFN_EXPLORER. Sinon, la fonction échoue avec une assertion.  
  
##  <a name="a-namesetdefexta--cfiledialogsetdefext"></a><a name="setdefext"></a>CFileDialog::SetDefExt  
 Appelez cette fonction pour définir l’extension de nom de fichier par défaut pour une boîte de dialogue commune Explorer-style ouvrir ou enregistrer sous.  
  
```  
void SetDefExt(LPCSTR lpsz);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpsz`  
 Pointeur vers une chaîne contenant l’extension par défaut à utiliser pour l’objet de boîte de dialogue. Cette chaîne ne doit pas contenir un point (.).  
  
### <a name="remarks"></a>Remarques  
 La boîte de dialogue doit avoir été créée avec le **OFN_EXPLORER** de style ; sinon, la fonction échoue avec une assertion.  
  
##  <a name="a-nameseteditboxtexta--cfiledialogseteditboxtext"></a><a name="seteditboxtext"></a>CFileDialog::SetEditBoxText  
 Définit le texte actuel dans un contrôle de zone d’édition.  
  
```  
HRESULT SetEditBoxText(
    DWORD dwIDCtl,  
    const CString& strText);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID de la zone d’édition.  
  
 `strText`  
 Valeur du texte.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesetpropertiesa--cfiledialogsetproperties"></a><a name="setproperties"></a>CFileDialog::SetProperties  
 Fournit une banque de propriétés qui définit les valeurs par défaut à utiliser pour l'élément en cours d'enregistrement.  
  
```  
BOOL SetProperties(LPCWSTR lpszPropList);
```  
  
### <a name="parameters"></a>Paramètres  
 `lpszPropList`  
 Liste de propriétés prédéfinies séparées par un « ; ». Pour obtenir la liste des indicateurs, consultez la `Flags` section de [OPENFILENAME](http://msdn.microsoft.com/en-us/8cecfd45-f7c1-4f8d-81a0-4e7fecc3b104).  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-namesetselectedcontrolitema--cfiledialogsetselectedcontrolitem"></a><a name="setselectedcontrolitem"></a>CFileDialog::SetSelectedControlItem  
 Définit l’état sélectionné d’un élément particulier dans un groupe de bouton d’option ou une zone de liste déroulante dans la boîte de dialogue.  
  
```  
HRESULT SetSelectedControlItem(
    DWORD dwIDCtl,  
    DWORD dwIDItem);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 L’ID du contrôle conteneur.  
  
 `dwIDItem`  
 L’ID de l’élément sélectionné par l’utilisateur dans le contrôle.  
  
### <a name="remarks"></a>Remarques  
  
##  <a name="a-namesettemplatea--cfiledialogsettemplate"></a><a name="settemplate"></a>CFileDialog::SetTemplate  
 Définit le modèle de boîte de dialogue pour le [CFileDialog](../../mfc/reference/cfiledialog-class.md) objet.  
  
```  
void SetTemplate(
    UINT nWin3ID,  
    UINT nWin4ID);

 
void SetTemplate(
    LPCTSTR lpWin3ID,  
    LPCTSTR lpWin4ID);
```  
  
### <a name="parameters"></a>Paramètres  
 [in] `nWin3ID`  
 Contient le numéro d’identification de la ressource de modèle pour le non-Explorer `CFileDialog` objet. Ce modèle est utilisé uniquement sur Windows NT 3.51 ou lorsque le style OFN_EXPLORER n’est pas présent.  
  
 [in] `nWin4ID`  
 Contient le numéro d’identification de la ressource de modèle pour l’Explorateur `CFileDialog` objet. Ce modèle est utilisé uniquement avec [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] et versions ultérieures, Windows 95 et versions ultérieures, ou lorsque le style OFN_EXPLORER est présent.  
  
 [in] `lpWin3ID`  
 Contient le nom de la ressource de modèle pour le non-Explorer `CFileDialog` objet. Ce modèle est utilisé uniquement sur Windows NT 3.51 ou lorsque le style OFN_EXPLORER n’est pas présent.  
  
 [in] `lpWin4ID`  
 Contient le nom de la ressource de modèle de l’Explorateur `CFileDialog` objet. Ce modèle est utilisé uniquement avec [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] et versions ultérieures, Windows 95 et versions ultérieures, ou lorsque le style OFN_EXPLORER est présent.  
  
### <a name="remarks"></a>Remarques  
 Le système utilisera uniquement un des modèles spécifiés. Le système détermine le modèle à utiliser en fonction de la présence du style OFN_EXPLORER et le système d’exploitation que l’application est en cours d’exécution. En spécifiant un modèle de style Explorateur et non-Explorer, il est facile de prise en charge de Windows NT 3.51, [!INCLUDE[WinNt4Family](../../mfc/reference/includes/winnt4family_md.md)] et versions ultérieures et Windows 95 et les versions ultérieures.  
  
> [!NOTE]
> [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]les boîtes de dialogue fichier ne gèrent pas cette fonction. Tentative d’utilisation de cette fonction sur un [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] boîte de dialogue de fichier style lèvera [exception CNotSupportedException](../../mfc/reference/cnotsupportedexception-class.md). Une alternative consiste à utiliser une boîte de dialogue personnalisée. Pour plus d’informations sur l’aide d’un `CFileDialog`, consultez [IFileDialogCustomize](http://msdn.microsoft.com/library/windows/desktop/bb775912).  
  
##  <a name="a-namestartvisualgroupa--cfiledialogstartvisualgroup"></a><a name="startvisualgroup"></a>CFileDialog::StartVisualGroup  
 Déclare un groupe visuel dans la boîte de dialogue. Les appels suivants à toute méthode « add » ajoutent ces éléments à ce groupe.  
  
```  
HRESULT StartVisualGroup(
    DWORD dwIDCtl,  
    const CString& strLabel);
```  
  
### <a name="parameters"></a>Paramètres  
 `dwIDCtl`  
 ID du groupe visual.  
  
 `strLabel`  
 Le nom du groupe.  
  
### <a name="remarks"></a>Notes  
  
##  <a name="a-nameupdateofnfromshelldialoga--cfiledialogupdateofnfromshelldialog"></a><a name="updateofnfromshelldialog"></a>CFileDialog::UpdateOFNFromShellDialog  
 Mises à jour la `m_ofn` structure de données de la [CFileDialog](../../mfc/reference/cfiledialog-class.md) selon l’état actuel de l’objet interne.  
  
```  
void UpdateOFNFromShellDialog();
```  
  
### <a name="remarks"></a>Remarques  
 Dans les versions de Windows antérieures à [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], le membre [OPENFILENAME](https://msdn.microsoft.com/library/ms911906.aspx) structure de données a été soit constamment synchronisée avec l’état de la `CFileDialog`. Les modifications apportées à la [m_ofn](#m_ofn) variable membre directement affecté l’état de la boîte de dialogue. En outre, toute modification apportée à l’état de la boîte de dialogue Mise à jour la variable de membre m_ofn immédiatement.  
  
 Dans [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], le `m_ofn` structure de données n’est pas automatiquement mis à jour. Pour garantir l’exactitude des données dans le `m_ofn` variable de membre, vous devez appeler le `UpdateOFNFromShellDialog` fonction avant d’accéder aux données. Windows appelle cette fonction automatiquement lors du traitement de [IFileDialog::OnFileOK](http://msdn.microsoft.com/library/windows/desktop/bb775879).  
  
 Pour plus d’informations sur l’utilisation de la `CFileDialog` classe sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], consultez [classe CFileDialog](../../mfc/reference/cfiledialog-class.md).  
  
### <a name="example"></a>Exemple  
 Cet exemple met à jour le `CFileDialog` avant de les afficher. Avant de mettre à jour le `m_ofn` variable de membre, nous avons besoin synchroniser l’état actuel de la boîte de dialogue.  
  
 [!code-cpp[NVC_MFC_CFileDialog n °&1;](../../mfc/reference/codesnippet/cpp/cfiledialog-class_7.cpp)]  
  
## <a name="see-also"></a>Voir aussi  
 [CCommonDialog (classe)](../../mfc/reference/ccommondialog-class.md)   
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)


