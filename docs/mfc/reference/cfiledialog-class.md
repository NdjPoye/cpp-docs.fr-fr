---
title: "CFileDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CFileDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CFileDialog class"
  - "common file dialog boxes"
  - "boîtes de dialogue, common"
ms.assetid: fda4fd3c-08b8-4ce0-8e9d-7bab23f8c6c0
caps.latest.revision: 47
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 49
---
# CFileDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Encapsule la boîte de dialogue commune utilisée pour ouvrir le fichier ou les opérations de sauvegarde de fichier.  
  
## Syntaxe  
  
```  
class CFileDialog : public CCommonDialog  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md)|Construit un objet `CFileDialog`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileDialog::AddCheckButton](../Topic/CFileDialog::AddCheckButton.md)|Ajoute un contrôle au bouton de dialogue.|  
|[CFileDialog::AddComboBox](../Topic/CFileDialog::AddComboBox.md)|Ajoute une zone de liste déroulante de dialogue.|  
|[CFileDialog::AddControlItem](../Topic/CFileDialog::AddControlItem.md)|Ajoute un élément à un contrôle conteneur dans la boîte de dialogue.|  
|[CFileDialog::AddEditBox](../Topic/CFileDialog::AddEditBox.md)|Ajoute une zone d'édition au dialogue.|  
|[CFileDialog::AddMenu](../Topic/CFileDialog::AddMenu.md)|Ajoute un menu à la boîte de dialogue.|  
|[CFileDialog::AddPlace](../Topic/CFileDialog::AddPlace.md)|Surchargé.  Ajoute un dossier à la liste d'emplacements disponibles pour l'utilisateur ouvre ou pour enregistrer des éléments.|  
|[CFileDialog::AddPushButton](../Topic/CFileDialog::AddPushButton.md)|Ajoute un bouton au dialogue.|  
|[CFileDialog::AddRadioButtonList](../Topic/CFileDialog::AddRadioButtonList.md)|Ajoute un groupe de case d'option \(également appelé la case d'option\) à la boîte de dialogue.|  
|[CFileDialog::AddSeparator](../Topic/CFileDialog::AddSeparator.md)|Ajoute un séparateur de dialogue.|  
|[CFileDialog::AddText](../Topic/CFileDialog::AddText.md)|Ajoute le contenu de texte au dialogue.|  
|[CFileDialog::ApplyOFNToShellDialog](../Topic/CFileDialog::ApplyOFNToShellDialog.md)|Met à jour l'état d' `CFileDialog` pour correspondre aux paramètres et les balises stockés dans la variable membre d' `m_ofn` .|  
|[CFileDialog::DoModal](../Topic/CFileDialog::DoModal.md)|Affiche la boîte de dialogue et permet à l'utilisateur d'effectuer une sélection.|  
|[CFileDialog::EnableOpenDropDown](../Topic/CFileDialog::EnableOpenDropDown.md)|Active une liste déroulante du bouton **Ouvrir** ou **Enregistrer** dans la boîte de dialogue.|  
|[CFileDialog::EndVisualGroup](../Topic/CFileDialog::EndVisualGroup.md)|Arrête l'ajout d'éléments à un groupe visuel dans la boîte de dialogue.|  
|[CFileDialog::GetCheckButtonState](../Topic/CFileDialog::GetCheckButtonState.md)|Obtient l'état actuel d'un bouton de contrôle \(case à cocher\) dans la boîte de dialogue.|  
|[CFileDialog::GetControlItemState](../Topic/CFileDialog::GetControlItemState.md)|Obtient l'état actuel d'un élément dans un contrôle conteneur trouvé dans la boîte de dialogue.|  
|[CFileDialog::GetControlState](../Topic/CFileDialog::GetControlState.md)|Passe la visibilité actuelle et les rapports activés d'un contrôle donné.|  
|[CFileDialog::GetEditBoxText](../Topic/CFileDialog::GetEditBoxText.md)|Obtient le texte actuel dans un contrôle de zone d'édition.|  
|[CFileDialog::GetFileExt](../Topic/CFileDialog::GetFileExt.md)|Retourne l'extension du fichier sélectionné.|  
|[CFileDialog::GetFileName](../Topic/CFileDialog::GetFileName.md)|Retourne le nom de fichier du fichier sélectionné.|  
|[CFileDialog::GetFileTitle](../Topic/CFileDialog::GetFileTitle.md)|Retourne le titre du fichier sélectionné.|  
|[CFileDialog::GetFolderPath](../Topic/CFileDialog::GetFolderPath.md)|Récupère le chemin d'accès du dossier ou du dossier actuellement ouvert pour **Ouvrir** ou une boîte de dialogue de style explorateur communs **Enregistrer sous** .|  
|[CFileDialog::GetIFileDialogCustomize](../Topic/CFileDialog::GetIFileDialogCustomize.md)|Récupère l'objet COM interne d'un objet personnalisé d' `CFileDialog` .|  
|[CFileDialog::GetIFileOpenDialog](../Topic/CFileDialog::GetIFileOpenDialog.md)|Récupère l'objet COM interne pour `CFileDialog` utilisé en tant que boîte de dialogue Fichier **Ouvrir** .|  
|[CFileDialog::GetIFileSaveDialog](../Topic/CFileDialog::GetIFileSaveDialog.md)|Récupère l'objet COM interne pour `CFileDialog` utilisé en tant que boîte de dialogue Fichier **Enregistrer** .|  
|[CFileDialog::GetNextPathName](../Topic/CFileDialog::GetNextPathName.md)|Retourne le chemin d'accès complet suivant du fichier sélectionné.|  
|[CFileDialog::GetOFN](../Topic/CFileDialog::GetOFN.md)|Extrait la structure d' `OPENFILENAME` de l'objet d' `CFileDialog` .|  
|[CFileDialog::GetPathName](../Topic/CFileDialog::GetPathName.md)|Retourne le chemin d'accès complet du fichier sélectionné.|  
|[CFileDialog::GetReadOnlyPref](../Topic/CFileDialog::GetReadOnlyPref.md)|Retourne l'état de lecture seule du fichier sélectionné.|  
|[CFileDialog::GetResult](../Topic/CFileDialog::GetResult.md)|Obtient le choix que l'utilisateur a fait dans la boîte de dialogue.|  
|[CFileDialog::GetResults](../Topic/CFileDialog::GetResults.md)|Obtient les choix de l'utilisateur dans une boîte de dialogue qui permet la sélection multiple.|  
|[CFileDialog::GetSelectedControlItem](../Topic/CFileDialog::GetSelectedControlItem.md)|Obtient un élément particulier les contrôles conteneur spécifiés dans la boîte de dialogue.|  
|[CFileDialog::GetStartPosition](../Topic/CFileDialog::GetStartPosition.md)|Retourne la position du premier élément de la liste de noms.|  
|[CFileDialog::HideControl](../Topic/CFileDialog::HideControl.md)|Masque le contrôle spécifié dans **Ouvrir** ou une boîte de dialogue de style explorateur communs **Enregistrer sous** .|  
|[CFileDialog::IsPickFoldersMode](../Topic/CFileDialog::IsPickFoldersMode.md)|Détermine si la boîte de dialogue actuel en mode de sélecteur de dossier.|  
|[CFileDialog::MakeProminent](../Topic/CFileDialog::MakeProminent.md)|Définit un contrôle dans la boîte de dialogue afin qu'il fasse tienne par rapport à d'autres contrôles ajoutés.|  
|[CFileDialog::RemoveControlItem](../Topic/CFileDialog::RemoveControlItem.md)|Supprime un élément d'un contrôle conteneur dans la boîte de dialogue.|  
|[CFileDialog::SetCheckButtonState](../Topic/CFileDialog::SetCheckButtonState.md)|Définit l'état actuel d'un bouton de contrôle \(case à cocher\) dans la boîte de dialogue.|  
|[CFileDialog::SetControlItemState](../Topic/CFileDialog::SetControlItemState.md)|Définit l'état actuel d'un élément dans un contrôle conteneur trouvé dans la boîte de dialogue.|  
|[CFileDialog::SetControlItemText](../Topic/CFileDialog::SetControlItemText.md)|Définit le texte d'un élément de contrôle.  Par exemple, le texte court qui accompagne une case d'option ou un élément d'un menu.|  
|[CFileDialog::SetControlLabel](../Topic/CFileDialog::SetControlLabel.md)|Définit le texte associé à un contrôle, par exemple le texte du bouton ou une étiquette de la zone d'édition.|  
|[CFileDialog::SetControlState](../Topic/CFileDialog::SetControlState.md)|Définit la visibilité actuelle et les rapports activés d'un contrôle donné.|  
|[CFileDialog::SetControlText](../Topic/CFileDialog::SetControlText.md)|Définit le texte du contrôle spécifié dans **Ouvrir** ou une boîte de dialogue de style explorateur communs **Enregistrer sous** .|  
|[CFileDialog::SetDefExt](../Topic/CFileDialog::SetDefExt.md)|Définit l'extension de nom de fichier par défaut pour **Ouvrir** ou une boîte de dialogue de style explorateur communs **Enregistrer sous** .|  
|[CFileDialog::SetEditBoxText](../Topic/CFileDialog::SetEditBoxText.md)|Définit le texte actuel dans un contrôle de zone d'édition.|  
|[CFileDialog::SetProperties](../Topic/CFileDialog::SetProperties.md)|Fournit une mémoire de propriété qui définit les valeurs par défaut à utiliser pour l'élément qui est enregistré.|  
|[CFileDialog::SetSelectedControlItem](../Topic/CFileDialog::SetSelectedControlItem.md)|Définit l'état sélectionné d'un élément particulier à un groupe de cases d'option ou une zone de liste déroulante a trouvé dans la boîte de dialogue.|  
|[CFileDialog::SetTemplate](../Topic/CFileDialog::SetTemplate.md)|Définit le modèle de boîte de dialogue pour l'objet d' `CFileDialog` .|  
|[CFileDialog::StartVisualGroup](../Topic/CFileDialog::StartVisualGroup.md)|Déclare un groupe visuel dans la boîte de dialogue.  Les appels suivants à dans « add » la méthode ajoutez ces éléments à ce groupe.|  
|[CFileDialog::UpdateOFNFromShellDialog](../Topic/CFileDialog::UpdateOFNFromShellDialog.md)|Met à jour les données stockées dans la variable membre d' `m_ofn` pour faire correspondre l'état actuel de la boîte de dialogue Fichier.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileDialog::OnButtonClicked](../Topic/CFileDialog::OnButtonClicked.md)|Appelé lorsque l'utilisateur clique sur le bouton.|  
|[CFileDialog::OnCheckButtonToggled](../Topic/CFileDialog::OnCheckButtonToggled.md)|Appelé lorsque la case à cocher est activée ou non réprimé.|  
|[CFileDialog::OnControlActivating](../Topic/CFileDialog::OnControlActivating.md)|Appelé lorsque le contrôle est actif.|  
|[CFileDialog::OnFileNameChange](../Topic/CFileDialog::OnFileNameChange.md)|Gère le message d' `WM_NOTIFY CDN_SELCHANGE` .|  
|[CFileDialog::OnFileNameOK](../Topic/CFileDialog::OnFileNameOK.md)|Valide le nom de fichier spécifié dans la boîte de dialogue.|  
|[CFileDialog::OnFolderChange](../Topic/CFileDialog::OnFolderChange.md)|Gère le message d' `WM_NOTIFY CDN_FOLDERCHANGE` .|  
|[CFileDialog::OnInitDone](../Topic/CFileDialog::OnInitDone.md)|Gère le message d' `WM_NOTIFY CDN_INITDONE` .|  
|[CFileDialog::OnItemSelected](../Topic/CFileDialog::OnItemSelected.md)|Appelé lorsque l'élément de conteneur est sélectionné.|  
|[CFileDialog::OnLBSelChangedNotify](../Topic/CFileDialog::OnLBSelChangedNotify.md)|Vous permet d'exécuter des actions personnalisées lorsque la sélection du fichier change.|  
|[CFileDialog::OnShareViolation](../Topic/CFileDialog::OnShareViolation.md)|Violations de partage de handles.|  
|[CFileDialog::OnTypeChange](../Topic/CFileDialog::OnTypeChange.md)|Gère le message d' `WM_NOTIFY CDN_TYPECHANGE` .|  
  
### Données membres publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CFileDialog::m\_ofn](../Topic/CFileDialog::m_ofn.md)|La structure d' `OPENFILENAME` windows.  Fournit l'accès aux paramètres de base de la boîte de dialogue Fichier.|  
  
## Notes  
 Les boîtes de dialogue courantes Fichier vous permettent d'implémenter des boîtes de dialogue de sélection de fichier, par exemple, **Ouvrir un fichier** et **Enregistrer sous**, d'une manière qui est compatible avec les normes de windows.  
  
 Vous pouvez utiliser [CFileDialog](../../mfc/reference/cfiledialog-class.md) tel quel avec le constructeur fourni, ou vous pouvez dériver votre propre classe de boîte de dialogue d' `CFileDialog` et écrire un constructeur pour l'adapter à vos besoins.  Dans les deux cas, ces boîtes de dialogue se comporteront comme les boîtes de dialogue MFC standard car elles proviennent de [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md).  `CFileDialog` repose sur le fichier de COMMDLG.DLL inclus dans windows.  
  
 L'apparence et les fonctionnalités d' `CFileDialog` avec [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] diffèrent des versions antérieures de windows.  La valeur par défaut `CFileDialog` utilise automatiquement le style d' [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] sans modifications de code si un programme est compilé et exécuté sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  Utilisez le paramètre d' `bVistaStyle` dans le constructeur pour substituer manuellement cette mise à jour automatique.  L'exception à la mise à jour automatique sont les boîtes de dialogue personnalisées.  Elles ne sont pas converties vers le nouveau style.  Pour plus d'informations sur le constructeur, consultez [CFileDialog::CFileDialog](../Topic/CFileDialog::CFileDialog.md).  
  
> [!NOTE]
>  Le système ID de contrôle diffère dans [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] les versions antérieures de windows lorsque vous utilisez `CFileDialog`.  Vous devez mettre à jour toutes les références aux contrôles d' `CFileDialog` dans le code avant de pouvoir déplacer votre projet d'une version antérieure de windows.  
  
 Certaines méthodes d' `CFileDialog` ne sont pas prises en charge dans [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  Consultez la rubrique individuel de méthode pour les informations sur si la méthode est prise en charge.  En outre, les fonctions héritées suivantes ne sont pas prises en charge dans [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]:  
  
-   [CDialog::OnInitDialog](../Topic/CDialog::OnInitDialog.md)  
  
-   [CDialog::OnSetFont](../Topic/CDialog::OnSetFont.md)  
  
 Les messages windows pour la classe d' `CFileDialog` varient selon le système d'exploitation vous utilisez.  Par exemple, Windows XP ne prend pas [CDialog::OnCancel](../Topic/CDialog::OnCancel.md) et [CDialog::OnOK](../Topic/CDialog::OnOK.md) pour la classe d' `CFileDialog` .  Toutefois, [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] les prend en charge.  Pour plus d'informations sur les différents messages générés et l'ordre dans lequel ils sont reçus, consultez l' [Exemple de CFileDialog : Commande de enregistrement d'événements](../../top/visual-cpp-samples.md).  
  
 Pour utiliser un objet d' `CFileDialog` , créez d'abord l'objet à l'aide de le constructeur d' `CFileDialog` .  Une fois la boîte de dialogue a été générée, vous pouvez définir ou modifier les valeurs dans la structure de [CFileDialog::m\_ofn](../Topic/CFileDialog::m_ofn.md) pour initialiser les valeurs ou les états des contrôles de boîte de dialogue.  La structure d' `m_ofn` est de type `OPENFILENAME`.  Pour plus d'informations, consultez la structure d' [OPENFILENAME](http://msdn.microsoft.com/library/windows/desktop/ms646839) dans [!INCLUDE[winSDK](../../atl/includes/winsdk_md.md)].  
  
 Après avoir initialisé les contrôles de boîte de dialogue, appelez la méthode de [CFileDialog::DoModal](../Topic/CFileDialog::DoModal.md) pour afficher la boîte de dialogue afin que l'utilisateur puisse entrer le chemin d'accès et le nom de fichier.  `DoModal` retourne si l'utilisateur a cliqué sur OK  \(IDOK\) ou le bouton de l'annulation \(IDCANCEL\).  Si `DoModal` retourne IDOK, vous pouvez utiliser l'une des fonctions membres publiques d' `CFileDialog` pour récupérer les informations mises dans par l'utilisateur.  
  
> [!NOTE]
>  Sous [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], les appels multiples à [IFileDialog::SetFileTypes](http://msdn.microsoft.com/library/windows/desktop/bb775980) provoque une erreur.  Le deuxième appel à `SetFileTypes` pour toute instance d' `CFileDialog` retourne `E_UNEXPECTED` dans [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  Un appel de fonctions de méthode d' `CFileDialog``SetFileTypes`.  Par exemple, deux appels à `CFileDialog::DoModal` pour la même instance d' `CFileDialog` génère [ASSERT](../Topic/ASSERT%20\(MFC\).md).  
  
 `CFileDialog` inclut plusieurs membres protégés qui vous permettent d'effectuer la gestion personnalisée des violations de partage, la validation de nom de fichier, et la notification de modifications de zone de liste.  Ces membres protégés sont des fonctions de rappel que la plupart des applications n'ont pas les utiliser car la gestion par défaut est exécutée automatiquement.  Les entrées de la table des messages pour ces fonctions ne sont pas requises parce qu'ils sont des fonctions virtuelles standard.  
  
 Vous pouvez utiliser la fonction de [CommDlgExtendedError](http://msdn.microsoft.com/library/windows/desktop/ms646916) windows pour déterminer si une erreur s'est produite pendant l'initialisation de la boîte de dialogue et pour en savoir plus sur l'erreur.  
  
 La destruction des objets d' `CFileDialog` est gérée automatiquement.  Vous ne devez pas appeler [CDialog::EndDialog](../Topic/CDialog::EndDialog.md).  
  
 Pour conserver les fichiers threads sélectionnés d'utilisateur, définissez l'indicateur d' `OFN_ALLOWMULTISELECT` avant d'appeler `DoModal`.  Vous devez fournir votre propre mémoire tampon de nom de fichier pour s'adapter à la liste retournée de noms de fichier en.  Faites ceci en remplaçant `m_ofn.lpstrFile` par un pointeur vers une mémoire tampon que vous avez alloué, après avoir construit `CFileDialog`, mais avant d'appeler `DoModal`.  
  
 En outre, vous devez définir `m_ofn.nMaxFile` à l'aide de le nombre de caractères dans la mémoire tampon pointée pointe vers `m_ofn.lpstrFile`.  Si vous définissez le nombre maximal de fichiers à sélectionner à `n`, la taille de mémoire tampon requise est `n * (_MAX_PATH + 1) + 1`.  Le premier élément retourné en mémoire tampon est le chemin d'accès au dossier dans lequel les fichiers ont été sélectionnés.  Pour les boîtes de dialogue de style d' [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)], les chaînes de répertoire et de nom de fichier sont se terminant par null, avec un caractère Null supplémentaire après le dernier nom de fichier.  Ce format permet aux boîtes de dialogue de style explorateur de retourner les noms de fichiers longs qui incluent des espaces.  Pour les boîtes de dialogue à l'ancien, les chaînes de répertoire et de nom de fichier sont séparées par des espaces et la fonction utilise des noms de fichiers courts pour les noms de fichiers avec des espaces.  
  
 L'exemple suivant montre comment utiliser une mémoire tampon pour récupérer et répertorier les noms de fichier en.  
  
 [!code-cpp[NVC_MFCFiles#23](../../mfc/codesnippet/CPP/cfiledialog-class_1.cpp)]  
  
 Pour modifier la taille de la mémoire tampon en réponse à l'utilisateur en sélectionnant les noms de fichier en, vous devez dériver une nouvelle classe d' `CFileDialog` et substituer la méthode d' [CFileDialog::OnFileNameChange](../Topic/CFileDialog::OnFileNameChange.md) .  
  
 Si vous dérivez une nouvelle classe d' `CFileDialog`, vous pouvez utiliser une table des messages pour gérer tous les messages.  Pour étendre la gestion des messages par défaut, dérivez une classe d' `CFileDialog`, ajoutez une table des messages à la nouvelle classe, et fournissent les fonctions membres pour les nouveaux messages.  Vous ne devez pas fournir une fonction de raccordement pour personnaliser la boîte de dialogue.  
  
 Pour personnaliser la boîte de dialogue, dérivez une classe d' `CFileDialog`, fournissez un modèle de boîte de dialogue personnalisé, puis ajoutez une table des messages pour traiter les messages de notification des contrôles étendus.  Passez tous les messages non\-traités à la classe de base.  Vous ne devez pas personnaliser la fonction de raccordement.  
  
 Lorsque vous utilisez le style d' [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)] d' `CFileDialog`, vous ne pouvez pas utiliser les tables des messages et les modèles de boîte de dialogue.  À la place, vous devez utiliser les interfaces COM pour des fonctionnalités semblables.  
  
 Pour plus d'informations sur l'utilisation de `CFileDialog`, consultez [Classes de boîtes de dialogue communes](../../mfc/common-dialog-classes.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CDialog](../../mfc/reference/cdialog-class.md)  
  
 [CCommonDialog](../../mfc/reference/ccommondialog-class.md)  
  
 `CFileDialog`  
  
## Configuration requise  
 **en\-tête :** afxdlgs.h  
  
## Voir aussi  
 [CCommonDialog Class](../../mfc/reference/ccommondialog-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)