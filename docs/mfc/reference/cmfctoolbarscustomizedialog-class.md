---
title: "CMFCToolBarsCustomizeDialog Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CMFCToolBarsCustomizeDialog"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CMFCToolBarsCustomizeDialog class"
ms.assetid: 78e2cddd-4f13-4097-afc3-1ad646a113f1
caps.latest.revision: 28
caps.handback.revision: 16
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CMFCToolBarsCustomizeDialog Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Une boîte de dialogue non modale d'onglet \([CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)\) qui permet à l'utilisateur de personnaliser les barres d'outils, des menus, les raccourcis clavier, les outils définis par l'utilisateur, et le style visuel dans une application.  En général, l'utilisateur accède cette boîte de dialogue en sélectionnant **Personnaliser** le menu **Outils** .  
  
 La boîte de dialogue **Personnaliser** a six onglets : **Commandes**, **Barres d'outils**, **Outils**, **Clavier**, **Menu**, et **Options**.  
  
## Syntaxe  
  
```  
class CMFCToolBarsCustomizeDialog : public CPropertySheet  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog](../Topic/CMFCToolBarsCustomizeDialog::CMFCToolBarsCustomizeDialog.md)|Construit un objet `CMFCToolBarsCustomizeDialog`.|  
|`CMFCToolBarsCustomizeDialog::~CMFCToolBarsCustomizeDialog`|Destructor.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md)|Insère un bouton de barre d'outils dans la liste des commandes dans la page **Commandes**|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenu](../Topic/CMFCToolBarsCustomizeDialog::AddMenu.md)|Charge un menu de ressources et appelle [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) pour ajouter de menu à la liste des commandes dans la page **Commandes** .|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md)|Charge un menu de ressources et appelle [CMFCToolBarsCustomizeDialog::AddMenuCommands](../Topic/CMFCToolBarsCustomizeDialog::AddMenuCommands.md) pour ajouter de menu à la liste des commandes dans la page **Commandes** .|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::AddToolBar](../Topic/CMFCToolBarsCustomizeDialog::AddToolBar.md)|Charge une barre d'outils des ressources.  Ensuite, car chaque commande dans le menu appelle la méthode d' [CMFCToolBarsCustomizeDialog::AddButton](../Topic/CMFCToolBarsCustomizeDialog::AddButton.md) pour insérer un bouton dans la liste des commandes dans la page **Commandes** dans la catégorie spécifiée.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md)|Affiche la boîte de dialogue **Personnalisation** .|  
|`CMFCToolBarsCustomizeDialog::EnableTools`|Réservé pour un usage futur.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars](../Topic/CMFCToolBarsCustomizeDialog::EnableUserDefinedToolbars.md)|Active ou désactive la création de nouvelles barres d'outils à l'aide de la boîte de dialogue **Personnaliser** .|  
|[CMFCToolBarsCustomizeDialog::FillAllCommandsList](../Topic/CMFCToolBarsCustomizeDialog::FillAllCommandsList.md)|Remplit l'objet fourni d' `CListBox` avec les commandes dans la catégorie **Toutes les commandes** .|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesComboBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesComboBox.md)|Remplit l'objet fourni d' `CComboBox` avec le nom de chaque catégorie de commande dans la boîte de dialogue **Personnaliser** .|  
|[CMFCToolBarsCustomizeDialog::FillCategoriesListBox](../Topic/CMFCToolBarsCustomizeDialog::FillCategoriesListBox.md)|Remplit l'objet fourni d' `CListBox` avec le nom de chaque catégorie de commande dans la boîte de dialogue **Personnaliser** .|  
|[CMFCToolBarsCustomizeDialog::GetCommandName](../Topic/CMFCToolBarsCustomizeDialog::GetCommandName.md)|Extrait le nom associé à l'ID donnée de commande|  
|[CMFCToolBarsCustomizeDialog::GetCountInCategory](../Topic/CMFCToolBarsCustomizeDialog::GetCountInCategory.md)|Récupère le nombre d'éléments dans la liste fournie qui ont une étiquette de texte donnée.|  
|[CMFCToolBarsCustomizeDialog::GetFlags](../Topic/CMFCToolBarsCustomizeDialog::GetFlags.md)|Extrait l'ensemble des balises qui affectent le comportement de la boîte de dialogue.|  
|`CMFCToolBarsCustomizeDialog::GetThisClass`|Utilisé par l'infrastructure pour obtenir un pointeur vers l'objet de [CRuntimeClass](../../mfc/reference/cruntimeclass-structure.md) associé à ce type de classe.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage](../Topic/CMFCToolBarsCustomizeDialog::OnEditToolbarMenuImage.md)|Commence un éditeur d'images pour qu'un utilisateur puisse personnaliser une icône de bouton de barre d'outils ou d'élément de menu.|  
|[CMFCToolBarsCustomizeDialog::OnInitDialog](../Topic/CMFCToolBarsCustomizeDialog::OnInitDialog.md)|Substitutions pour augmenter l'initialisation de feuille de propriétés.  \(Substitutions [CPropertySheet::OnInitDialog](../Topic/CPropertySheet::OnInitDialog.md).\)|  
|[CMFCToolBarsCustomizeDialog::PostNcDestroy](../Topic/CMFCToolBarsCustomizeDialog::PostNcDestroy.md)|Appelé par l'infrastructure après la fenêtre a été perdue.  \(Substitutions `CPropertySheet::PostNcDestroy`.\)|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RemoveButton](../Topic/CMFCToolBarsCustomizeDialog::RemoveButton.md)|Supprime le bouton avec l'ID de commande spécifié de la catégorie spécifiée, ou de toutes les catégories.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::RenameCategory](../Topic/CMFCToolBarsCustomizeDialog::RenameCategory.md)|Renomme une catégorie dans la zone de liste de catégories sur **Commandes** tableau.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::ReplaceButton](../Topic/CMFCToolBarsCustomizeDialog::ReplaceButton.md)|Remplace un bouton dans la liste des commandes sur l'onglet **Commandes** par un objet de bouton de la barre d'outils.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::SetUserCategory](../Topic/CMFCToolBarsCustomizeDialog::SetUserCategory.md)|Ajoute une catégorie à la liste de catégories qui seront affichées sur **Commandes** tableau.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::CheckToolsValidity](../Topic/CMFCToolBarsCustomizeDialog::CheckToolsValidity.md)|Appelé par l'infrastructure pour déterminer si la liste d'outils définis par l'utilisateur est valide.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAfterChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnAfterChangeTool.md)|Appelé par l'infrastructure lorsque les propriétés d'une modification définie par l'utilisateur de l'outil.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnAssignKey](../Topic/CMFCToolBarsCustomizeDialog::OnAssignKey.md)|Détermine si un raccourci clavier spécifié peut être assigné à une action.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnBeforeChangeTool](../Topic/CMFCToolBarsCustomizeDialog::OnBeforeChangeTool.md)|Détermine si un outil défini par l'utilisateur peut être modifié.|  
|`CMFCToolBarsCustomizeDialog::` [CMFCToolBarsCustomizeDialog::OnInitToolsPage](../Topic/CMFCToolBarsCustomizeDialog::OnInitToolsPage.md)|Appelé par l'infrastructure lorsque l'utilisateur choisit l'onglet **Outils** est demandé.|  
  
## Notes  
 Pour afficher la boîte de dialogue **Personnaliser** , créez un objet d' `CMFCToolBarsCustomizeDialog` et appelez la méthode de [CMFCToolBarsCustomizeDialog::Create](../Topic/CMFCToolBarsCustomizeDialog::Create.md) .  
  
 Lorsque la boîte de dialogue **Personnaliser** est actif, l'application s'exécute dans un mode spécial qui limite l'utilisateur aux tâches de personnalisation.  
  
## Exemple  
 L'exemple suivant montre comment utiliser différentes méthodes dans la classe d' `CMFCToolBarsCustomizeDialog` .  L'exemple montre comment substituer un bouton de barre d'outils dans la zone de liste de commandes dans la page **Commandes** , activer la création de nouvelles barres d'outils à l'aide de la boîte de dialogue **Personnaliser** , et afficher la boîte de dialogue **Personnalisation** .  Cet extrait de code fait partie d' [Exemple de démonstration d'IE](../../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_IEDemo#4](../../mfc/reference/codesnippet/CPP/cmfctoolbarscustomizedialog-class_1.cpp)]  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 [CPropertySheet](../../mfc/reference/cpropertysheet-class.md)  
  
 [CMFCToolBarsCustomizeDialog](../../mfc/reference/cmfctoolbarscustomizedialog-class.md)  
  
## Configuration requise  
 **en\-tête :** afxToolBarsCustomizeDialog.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Classes](../../mfc/reference/mfc-classes.md)   
 [CPropertySheet Class](../../mfc/reference/cpropertysheet-class.md)