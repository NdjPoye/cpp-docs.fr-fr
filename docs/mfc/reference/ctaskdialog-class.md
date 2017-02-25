---
title: "CTaskDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CTaskDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CTaskDialog class"
ms.assetid: 1991ec98-ae56-4483-958b-233809c8c559
caps.latest.revision: 29
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 31
---
# CTaskDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une boîte de dialogue contextuelle qui fonctionne comme un message mais peut afficher des informations supplémentaires à l'utilisateur.  `CTaskDialog` inclut également les fonctionnalités pour rassembler des informations auprès de l'utilisateur.  
  
## Syntaxe  
  
```  
class CTaskDialog : public CObject  
```  
  
## Membres  
  
### Constructeurs  
  
|||  
|-|-|  
|[CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md)|Construit un objet `CTaskDialog`.|  
  
### Méthodes  
  
|||  
|-|-|  
|[CTaskDialog::AddCommandControl](../Topic/CTaskDialog::AddCommandControl.md)|Ajoute un contrôle bouton de commande à `CTaskDialog`.|  
|[CTaskDialog::AddRadioButton](../Topic/CTaskDialog::AddRadioButton.md)|Ajoute une case d'option à `CTaskDialog`.|  
|[CTaskDialog::ClickCommandControl](../Topic/CTaskDialog::ClickCommandControl.md)|Clique sur un contrôle bouton de commande ou un bouton\) par programme.|  
|[CTaskDialog::ClickRadioButton](../Topic/CTaskDialog::ClickRadioButton.md)|Clique sur une case d'option par programme.|  
|[CTaskDialog::DoModal](../Topic/CTaskDialog::DoModal.md)|Affiche la `CTaskDialog`.|  
|[CTaskDialog::GetCommonButtonCount](../Topic/CTaskDialog::GetCommonButtonCount.md)|Récupère le nombre de boutons courants disponibles.|  
|[CTaskDialog::GetCommonButtonFlag](../Topic/CTaskDialog::GetCommonButtonFlag.md)|Convertit les fenêtres bouton standard au bouton le type commun associé à la classe d' `CTaskDialog` .|  
|[CTaskDialog::GetCommonButtonId](../Topic/CTaskDialog::GetCommonButtonId.md)|Les convertit un des types courants de boutons associés à la classe d' `CTaskDialog` à l'des fenêtres standard bouton événements.|  
|[CTaskDialog::GetOptions](../Topic/CTaskDialog::GetOptions.md)|Retourne les balises d'option pour cet `CTaskDialog`.|  
|[CTaskDialog::GetSelectedCommandControlID](../Topic/CTaskDialog::GetSelectedCommandControlID.md)|Retourne le contrôle sélectionné de bouton de commande.|  
|[CTaskDialog::GetSelectedRadioButtonID](../Topic/CTaskDialog::GetSelectedRadioButtonID.md)|Retourne la case d'option sélectionnée.|  
|[CTaskDialog::GetVerificationCheckboxState](../Topic/CTaskDialog::GetVerificationCheckboxState.md)|Récupère l'état de la case à cocher de vérification.|  
|[CTaskDialog::IsCommandControlEnabled](../Topic/CTaskDialog::IsCommandControlEnabled.md)|Détermine si un contrôle bouton de commande ou un bouton\) est activé.|  
|[CTaskDialog::IsRadioButtonEnabled](../Topic/CTaskDialog::IsRadioButtonEnabled.md)|Détermine si une case d'option est activée.|  
|[CTaskDialog::IsSupported](../Topic/CTaskDialog::IsSupported.md)|Détermine si l'ordinateur qui exécute l'application prend en charge `CTaskDialog`.|  
|[CTaskDialog::LoadCommandControls](../Topic/CTaskDialog::LoadCommandControls.md)|Ajoute des contrôles de bouton de commande à l'aide de les données de la table de chaînes.|  
|[CTaskDialog::LoadRadioButtons](../Topic/CTaskDialog::LoadRadioButtons.md)|Ajoute des cases d'option à l'aide de les données de la table de chaînes.|  
|[CTaskDialog::NavigateTo](../Topic/CTaskDialog::NavigateTo.md)|Transfère le focus vers un autre `CTaskDialog`.|  
|[CTaskDialog::OnCommandControlClick](../Topic/CTaskDialog::OnCommandControlClick.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur clique sur un contrôle bouton de commande.|  
|[CTaskDialog::OnCreate](../Topic/CTaskDialog::OnCreate.md)|l'infrastructure appelle cette méthode après qu'elle crée `CTaskDialog`.|  
|[CTaskDialog::OnDestroy](../Topic/CTaskDialog::OnDestroy.md)|L'infrastructure appelle cette méthode juste avant qu'elle perde `CTaskDialog`.|  
|[CTaskDialog::OnExpandButtonClick](../Topic/CTaskDialog::OnExpandButtonClick.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur clique sur le bouton de développement.|  
|[CTaskDialog::OnHelp](../Topic/CTaskDialog::OnHelp.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur aident.|  
|[CTaskDialog::OnHyperlinkClick](../Topic/CTaskDialog::OnHyperlinkClick.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur clique sur un lien hypertexte.|  
|[CTaskDialog::OnInit](../Topic/CTaskDialog::OnInit.md)|L'infrastructure appelle cette méthode lorsque `CTaskDialog` est initialisé.|  
|[CTaskDialog::OnNavigatePage](../Topic/CTaskDialog::OnNavigatePage.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur déplace le focus en ce qui concerne les contrôles sur `CTaskDialog`.|  
|[CTaskDialog::OnRadioButtonClick](../Topic/CTaskDialog::OnRadioButtonClick.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur sélectionne un contrôle de case d'option.|  
|[CTaskDialog::OnTimer](../Topic/CTaskDialog::OnTimer.md)|L'infrastructure appelle cette méthode lorsque le délai d'expiration s'achève.|  
|[CTaskDialog::OnVerificationCheckboxClick](../Topic/CTaskDialog::OnVerificationCheckboxClick.md)|L'infrastructure appelle cette méthode lorsque l'utilisateur clique sur la case à cocher de vérification.|  
|[CTaskDialog::RemoveAllCommandControls](../Topic/CTaskDialog::RemoveAllCommandControls.md)|Supprime tous les contrôles de commande des `CTaskDialog`.|  
|[CTaskDialog::RemoveAllRadioButtons](../Topic/CTaskDialog::RemoveAllRadioButtons.md)|Supprime toutes les cases d'option d' `CTaskDialog`.|  
|[CTaskDialog::SetCommandControlOptions](../Topic/CTaskDialog::SetCommandControlOptions.md)|Gère un contrôle bouton de commande dans `CTaskDialog`.|  
|[CTaskDialog::SetCommonButtonOptions](../Topic/CTaskDialog::SetCommonButtonOptions.md)|Met à jour un sous\-ensemble de boutons communs à activer et requiert élévation du contrôle de compte d'utilisateur.|  
|[CTaskDialog::SetCommonButtons](../Topic/CTaskDialog::SetCommonButtons.md)|Ajoute les boutons communs à `CTaskDialog`.|  
|[CTaskDialog::SetContent](../Topic/CTaskDialog::SetContent.md)|Met à jour le contenu d' `CTaskDialog`.|  
|[CTaskDialog::SetDefaultCommandControl](../Topic/CTaskDialog::SetDefaultCommandControl.md)|Spécifie le contrôle par défaut du bouton de commande.|  
|[CTaskDialog::SetDefaultRadioButton](../Topic/CTaskDialog::SetDefaultRadioButton.md)|Spécifie la case d'option par défaut.|  
|[CTaskDialog::SetDialogWidth](../Topic/CTaskDialog::SetDialogWidth.md)|Règle la largeur d' `CTaskDialog`.|  
|[CTaskDialog::SetExpansionArea](../Topic/CTaskDialog::SetExpansionArea.md)|Met à jour la zone d'expansion d' `CTaskDialog`.|  
|[CTaskDialog::SetFooterIcon](../Topic/CTaskDialog::SetFooterIcon.md)|Met à jour l'icône de pied de page pour `CTaskDialog`.|  
|[CTaskDialog::SetFooterText](../Topic/CTaskDialog::SetFooterText.md)|Met à jour le texte du pied de page d' `CTaskDialog`.|  
|[CTaskDialog::SetMainIcon](../Topic/CTaskDialog::SetMainIcon.md)|Met à jour l'icône principale d' `CTaskDialog`.|  
|[CTaskDialog::SetMainInstruction](../Topic/CTaskDialog::SetMainInstruction.md)|Met à jour l'instruction principale d' `CTaskDialog`.|  
|[CTaskDialog::SetOptions](../Topic/CTaskDialog::SetOptions.md)|Configure les options de `CTaskDialog`.|  
|[CTaskDialog::SetProgressBarMarquee](../Topic/CTaskDialog::SetProgressBarMarquee.md)|Configure une barre de bannière pour `CTaskDialog` et l'ajoute à la boîte de dialogue.|  
|[CTaskDialog::SetProgressBarPosition](../Topic/CTaskDialog::SetProgressBarPosition.md)|Règle la position de la barre de progression.|  
|[CTaskDialog::SetProgressBarRange](../Topic/CTaskDialog::SetProgressBarRange.md)|Règle la plage de la barre de progression.|  
|[CTaskDialog::SetProgressBarState](../Topic/CTaskDialog::SetProgressBarState.md)|Définit l'état de la barre de progression et l'affiche dans `CTaskDialog`.|  
|[CTaskDialog::SetRadioButtonOptions](../Topic/CTaskDialog::SetRadioButtonOptions.md)|Active ou désactive la case d'option.|  
|[CTaskDialog::SetVerificationCheckbox](../Topic/CTaskDialog::SetVerificationCheckbox.md)|Définit l'état activé de la case à cocher de vérification.|  
|[CTaskDialog::SetVerificationCheckboxText](../Topic/CTaskDialog::SetVerificationCheckboxText.md)|Définit le texte à droite de la case à cocher de vérification.|  
|[CTaskDialog::SetWindowTitle](../Topic/CTaskDialog::SetWindowTitle.md)|Définit le titre d' `CTaskDialog`.|  
|[CTaskDialog::ShowDialog](../Topic/CTaskDialog::ShowDialog.md)|Crée et affiche `CTaskDialog`.|  
|[CTaskDialog::TaskDialogCallback](../Topic/CTaskDialog::TaskDialogCallback.md)|L'infrastructure appelle cela en réponse à des messages windows.|  
  
### Membres de données  
  
|||  
|-|-|  
|`m_aButtons`|Le choix de contrôles bouton de commande pour `CTaskDialog`.|  
|`m_aRadioButtons`|Le choix de contrôles de case d'option pour `CTaskDialog`.|  
|`m_bVerified`|`TRUE` indique la case à cocher de vérification est activé ; `FALSE` l'indique n'est pas.|  
|`m_footerIcon`|L'icône dans le pied de page d' `CTaskDialog`.|  
|`m_hWnd`|Un handle vers la fenêtre pour `CTaskDialog`.|  
|`m_mainIcon`|l'icône principale d' `CTaskDialog`.|  
|`m_nButtonDisabled`|Un masque qui indique que des boutons courants sont désactivés.|  
|`m_nButtonElevation`|Un masque qui indique que des boutons communs requièrent élévation du contrôle de compte d'utilisateur.|  
|`m_nButtonId`|L'ID du contrôle sélectionné de bouton de commande.|  
|`m_nCommonButton`|Un masque qui indique que des boutons courants sont affichés sur `CTaskDialog`.|  
|`m_nDefaultCommandControl`|L'ID du contrôle bouton de commande qui est sélectionnée lorsque `CTaskDialog` s'affiche.|  
|`m_nDefaultRadioButton`|L'ID du contrôle de case d'option sélectionnée lorsque `CTaskDialog` s'affiche.|  
|`m_nFlags`|Un masque qui indique les options de `CTaskDialog`.|  
|`m_nProgressPos`|La position actuelle pour la barre de progression.  Cette valeur doit être comprise entre `m_nProgressRangeMin` et `m_nProgressRangeMax`.|  
|`m_nProgressRangeMax`|La valeur maximale de la barre de progression.|  
|`m_nProgressRangeMin`|La valeur minimale pour la barre de progression.|  
|`m_nProgressState`|l'état de la barre de progression.  Pour plus d'informations, consultez [CTaskDialog::SetProgressBarState](../Topic/CTaskDialog::SetProgressBarState.md).|  
|`m_nRadioId`|L'ID du contrôle sélectionné de case d'option.|  
|`m_nWidth`|Largeur du `CTaskDialog` en pixels.|  
|`m_strCollapse`|La chaîne qu' `CTaskDialog` affiche à droite de la zone d'expansion lorsque les informations développées sont masquées.|  
|`m_strContent`|La chaîne de contenu d' `CTaskDialog`.|  
|`m_strExpand`|La chaîne qu' `CTaskDialog` affiche à droite de la zone d'expansion lorsque les informations développées sont affichées.|  
|`m_strFooter`|Le pied de page d' `CTaskDialog`.|  
|`m_strInformation`|Les informations développées pour `CTaskDialog`.|  
|`m_strMainInstruction`|l'instruction principale d' `CTaskDialog`.|  
|`m_strTitle`|Titre de la `CTaskDialog`.|  
|`m_strVerification`|La chaîne qu' `CTaskDialog` affiche à droite de la case à cocher de vérification.|  
  
## Notes  
 La classe d' `CTaskDialog` remplace le message windows standard et des fonctionnalités supplémentaires telles que des contrôles pour rassembler des informations auprès de l'utilisateur.  Cette classe est à la bibliothèque MFC dans [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  `CTaskDialog` est disponible commencer par [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)].  Les versions antérieures de windows ne peuvent pas afficher l'objet d' `CTaskDialog` .  Utilisez `CTaskDialog::IsSupported` pour déterminer au moment de l'exécution si l'utilisateur actuel peut afficher la boîte de dialogue de tâche.  Le message windows standard est toujours pris en charge dans [!INCLUDE[vs_dev10_long](../../build/includes/vs_dev10_long_md.md)].  
  
 `CTaskDialog` est disponible uniquement lorsque vous générez votre application à l'aide de la bibliothèque Unicode.  
  
 `CTaskDialog` a deux fournisseurs différents.  Un constructeur permet de spécifier deux boutons de commande et un maximum de six contrôles bouton normal.  Vous pouvez ajouter des boutons de commande après avoir créé `CTaskDialog`.  Le deuxième constructeur ne prend pas bouton de commande, mais vous pouvez ajouter un nombre illimité de contrôles bouton normal.  Pour plus d'informations sur les constructeurs, consultez [CTaskDialog::CTaskDialog](../Topic/CTaskDialog::CTaskDialog.md).  
  
 L'image suivante montre un exemple `CTaskDialog` illustrait l'emplacement de certains contrôles.  
  
 ![Exemple de CTaskDialog](../../mfc/reference/media/ctaskdialogsample.png "CTaskDialogSample")  
Exemple de CTaskDialog  
  
## Configuration requise  
 **Système d'exploitation obligatoire minimum :** [!INCLUDE[wiprlhext](../../c-runtime-library/reference/includes/wiprlhext_md.md)]  
  
 **en\-tête :** afxtaskdialog.h  
  
## Voir aussi  
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CObject Class](../../mfc/reference/cobject-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Procédure pas à pas : ajout d'une classe CTaskDialog à une application](../../mfc/walkthrough-adding-a-ctaskdialog-to-an-application.md)