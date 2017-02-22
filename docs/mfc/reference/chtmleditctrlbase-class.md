---
title: "CHtmlEditCtrlBase Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CHtmlEditCtrlBase"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CHtmlEditCtrlBase class"
ms.assetid: e0cc74b4-8320-4570-b673-16c03d2ae266
caps.latest.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 23
---
# CHtmlEditCtrlBase Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Représente un composant d'édition HTML.  
  
## Syntaxe  
  
```  
  
template < class   
T  
 > class CHtmlEditCtrlBase  
  
```  
  
## Membres  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CHtmlEditCtrlBase::AddToGlyphTable](../Topic/CHtmlEditCtrlBase::AddToGlyphTable.md)|Ajoute une entrée au tableau de glyphe, qui spécifie des images pour afficher des balises spécifiques en mode Design.|  
|[CHtmlEditCtrlBase::Bold](../Topic/CHtmlEditCtrlBase::Bold.md)|Active\/désactive l'état Gras du texte sélectionné.|  
|[CHtmlEditCtrlBase::Button](../Topic/CHtmlEditCtrlBase::Button.md)|Remplace un contrôle bouton dans la sélection actuelle.|  
|[CHtmlEditCtrlBase::CheckBox](../Topic/CHtmlEditCtrlBase::CheckBox.md)|Remplace un contrôle de case à cocher sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::ClearSelection](../Topic/CHtmlEditCtrlBase::ClearSelection.md)|Efface la sélection actuelle.|  
|[CHtmlEditCtrlBase::Copy](../Topic/CHtmlEditCtrlBase::Copy.md)|Copie la sélection actuelle dans le presse\-papiers.|  
|[CHtmlEditCtrlBase::Cut](../Topic/CHtmlEditCtrlBase::Cut.md)|Copie la sélection actuelle dans le presse\-papiers et la supprime.|  
|[CHtmlEditCtrlBase::Delete](../Topic/CHtmlEditCtrlBase::Delete.md)|Supprime la sélection actuelle.|  
|[CHtmlEditCtrlBase::DropDownBox](../Topic/CHtmlEditCtrlBase::DropDownBox.md)|Remplace un contrôle de sélection déroulante de la sélection actuelle.|  
|[CHtmlEditCtrlBase::EmptyGlyphTable](../Topic/CHtmlEditCtrlBase::EmptyGlyphTable.md)|Supprime toutes les entrées du tableau de glyphe, qui masque toutes les images restituées pour les balises en mode Design.|  
|[CHtmlEditCtrlBase::ExecCommand](../Topic/CHtmlEditCtrlBase::ExecCommand.md)|Exécute une commande.|  
|[CHtmlEditCtrlBase::Font](../Topic/CHtmlEditCtrlBase::Font.md)|Ouvre une boîte de dialogue Police pour permettre à l'utilisateur de modifier la couleur de texte, la police, et la taille de police de la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetAbsolutePosition](../Topic/CHtmlEditCtrlBase::GetAbsolutePosition.md)|Retourne si la propriété de la position d'un élément est « absolu. »|  
|[CHtmlEditCtrlBase::GetBackColor](../Topic/CHtmlEditCtrlBase::GetBackColor.md)|Extrait la couleur d'arrière\-plan de la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetBlockFormat](../Topic/CHtmlEditCtrlBase::GetBlockFormat.md)|Extrait la balise active de format du bloc.|  
|[CHtmlEditCtrlBase::GetBlockFormatNames](../Topic/CHtmlEditCtrlBase::GetBlockFormatNames.md)|Récupère les chaînes qui correspondent aux balises disponibles de format du bloc.|  
|[CHtmlEditCtrlBase::GetBookMark](../Topic/CHtmlEditCtrlBase::GetBookMark.md)|Extrait le nom d'un point d'ancrage de signet.|  
|[CHtmlEditCtrlBase::GetDocument](../Topic/CHtmlEditCtrlBase::GetDocument.md)|Récupère l'objet.|  
|[CHtmlEditCtrlBase::GetDocumentHTML](../Topic/CHtmlEditCtrlBase::GetDocumentHTML.md)|Récupère le HTML du document actif.|  
|[CHtmlEditCtrlBase::GetDocumentTitle](../Topic/CHtmlEditCtrlBase::GetDocumentTitle.md)|Récupère le titre du document.|  
|[CHtmlEditCtrlBase::GetEvent](../Topic/CHtmlEditCtrlBase::GetEvent.md)|Extrait un pointeur d'interface vers l'objet événement contenant les informations pertinentes l'événement le plus récent.|  
|[CHtmlEditCtrlBase::GetEventSrcElement](../Topic/CHtmlEditCtrlBase::GetEventSrcElement.md)|Récupère l'objet qui a déclenché l'événement.|  
|[CHtmlEditCtrlBase::GetFontFace](../Topic/CHtmlEditCtrlBase::GetFontFace.md)|Extrait le nom de police de la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetFontSize](../Topic/CHtmlEditCtrlBase::GetFontSize.md)|Extrait la taille de police de la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetForeColor](../Topic/CHtmlEditCtrlBase::GetForeColor.md)|Extrait la couleur de premier plan \(texte\) de la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetFrameZone](../Topic/CHtmlEditCtrlBase::GetFrameZone.md)|Retourne la zone de sécurité de la page actuelle dans le navigateur web.|  
|[CHtmlEditCtrlBase::GetIsDirty](../Topic/CHtmlEditCtrlBase::GetIsDirty.md)|Indique si le document HTML a changé.|  
|[CHtmlEditCtrlBase::GetShowAlignedSiteTags](../Topic/CHtmlEditCtrlBase::GetShowAlignedSiteTags.md)|Retourne si un glyphe s'affiche pour tous les éléments qui ont une propriété de **styleFloat** .|  
|[CHtmlEditCtrlBase::GetShowAllTags](../Topic/CHtmlEditCtrlBase::GetShowAllTags.md)|Retourne si le WebBrowser affiche des glyphes pour afficher l'emplacement de toutes les balises d'un document.|  
|[CHtmlEditCtrlBase::GetShowAreaTags](../Topic/CHtmlEditCtrlBase::GetShowAreaTags.md)|Récupère si le WebBrowser affiche un glyphe pour les balises de zone.|  
|[CHtmlEditCtrlBase::GetShowBRTags](../Topic/CHtmlEditCtrlBase::GetShowBRTags.md)|Récupère si le WebBrowser affiche un glyphe pour les balises de Br.|  
|[CHtmlEditCtrlBase::GetShowCommentTags](../Topic/CHtmlEditCtrlBase::GetShowCommentTags.md)|Récupère si le WebBrowser affiche un glyphe pour les balises de commentaire.|  
|[CHtmlEditCtrlBase::GetShowMiscTags](../Topic/CHtmlEditCtrlBase::GetShowMiscTags.md)|Récupère si le WebBrowser affiche toutes les balises affichées dans Microsoft Internet Explorer 4,0.|  
|[CHtmlEditCtrlBase::GetShowScriptTags](../Topic/CHtmlEditCtrlBase::GetShowScriptTags.md)|Récupère si le WebBrowser affiche un glyphe pour toutes les balises de script.|  
|[CHtmlEditCtrlBase::GetShowStyleTags](../Topic/CHtmlEditCtrlBase::GetShowStyleTags.md)|Récupère si le WebBrowser affiche un glyphe pour toutes les balises de style.|  
|[CHtmlEditCtrlBase::GetShowUnknownTags](../Topic/CHtmlEditCtrlBase::GetShowUnknownTags.md)|Récupère si le WebBrowser affiche un glyphe pour toutes les balises inconnues.|  
|[CHtmlEditCtrlBase::HorizontalLine](../Topic/CHtmlEditCtrlBase::HorizontalLine.md)|Remplace une ligne horizontale sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::HyperLink](../Topic/CHtmlEditCtrlBase::HyperLink.md)|Insère un lien hypertexte sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::IE50Paste](../Topic/CHtmlEditCtrlBase::IE50Paste.md)|Effectue une opération de collage compatible avec Microsoft Internet Explorer 5.|  
|[CHtmlEditCtrlBase::Iframe](../Topic/CHtmlEditCtrlBase::Iframe.md)|Remplace un frame intégré sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Image](../Topic/CHtmlEditCtrlBase::Image.md)|Remplace une image sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Indent](../Topic/CHtmlEditCtrlBase::Indent.md)|Augmente le retrait du texte sélectionné par un index de mise en retrait.|  
|[CHtmlEditCtrlBase::InsFieldSet](../Topic/CHtmlEditCtrlBase::InsFieldSet.md)|Remplace une zone sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputButton](../Topic/CHtmlEditCtrlBase::InsInputButton.md)|Remplace un contrôle bouton dans la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputHidden](../Topic/CHtmlEditCtrlBase::InsInputHidden.md)|Insère un contrôle masqué dans la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputImage](../Topic/CHtmlEditCtrlBase::InsInputImage.md)|Remplace un contrôle image sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputPassword](../Topic/CHtmlEditCtrlBase::InsInputPassword.md)|Remplace un contrôle de mot de passe sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputReset](../Topic/CHtmlEditCtrlBase::InsInputReset.md)|Remplace un contrôle de réinitialisation sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputSubmit](../Topic/CHtmlEditCtrlBase::InsInputSubmit.md)|Remplace un contrôle de soumettre sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputUpload](../Topic/CHtmlEditCtrlBase::InsInputUpload.md)|Remplace un contrôle de téléchargement de fichiers sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Is1DElement](../Topic/CHtmlEditCtrlBase::Is1DElement.md)|Détermine si un élément est statiquement positionné.|  
|[CHtmlEditCtrlBase::Is2DElement](../Topic/CHtmlEditCtrlBase::Is2DElement.md)|Détermine si un élément est absolument positionné.|  
|[CHtmlEditCtrlBase::Italic](../Topic/CHtmlEditCtrlBase::Italic.md)|Bascule la sélection actuelle entre italique et nonitalic.|  
|[CHtmlEditCtrlBase::JustifyCenter](../Topic/CHtmlEditCtrlBase::JustifyCenter.md)|Centre le bloc de format dans lequel la sélection actuelle est localisée.|  
|[CHtmlEditCtrlBase::JustifyLeft](../Topic/CHtmlEditCtrlBase::JustifyLeft.md)|Cliquez justifie le bloc de format dans lequel la sélection actuelle est localisée.|  
|[CHtmlEditCtrlBase::JustifyRight](../Topic/CHtmlEditCtrlBase::JustifyRight.md)|Justifie à droite le bloc de format dans lequel la sélection actuelle est localisée.|  
|[CHtmlEditCtrlBase::ListBox](../Topic/CHtmlEditCtrlBase::ListBox.md)|Remplace un contrôle de sélection de zone de liste sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Marquee](../Topic/CHtmlEditCtrlBase::Marquee.md)|Remplace une bannière vide de la sélection actuelle.|  
|[CHtmlEditCtrlBase::NewDocument](../Topic/CHtmlEditCtrlBase::NewDocument.md)|Crée un document.|  
|[CHtmlEditCtrlBase::OrderList](../Topic/CHtmlEditCtrlBase::OrderList.md)|Bascule la sélection actuelle entre une liste triée et un bloc de format normal.|  
|[CHtmlEditCtrlBase::Outdent](../Topic/CHtmlEditCtrlBase::Outdent.md)|Par un index diminue la mise en retrait du bloc de format dans lequel la sélection actuelle est localisée.|  
|[CHtmlEditCtrlBase::Paragraph](../Topic/CHtmlEditCtrlBase::Paragraph.md)|Remplace un saut de ligne dans la sélection actuelle.|  
|[CHtmlEditCtrlBase::Paste](../Topic/CHtmlEditCtrlBase::Paste.md)|Remplace le contenu du presse\-papiers dans la sélection actuelle.|  
|[CHtmlEditCtrlBase::PrintDocument](../Topic/CHtmlEditCtrlBase::PrintDocument.md)|Imprime le document actif.|  
|[CHtmlEditCtrlBase::PrintPreview](../Topic/CHtmlEditCtrlBase::PrintPreview.md)|Ouvre la fenêtre d'aperçu avant impression du document actif à l'aide de le modèle par défaut d'aperçu avant impression ou un modèle personnalisé.|  
|[CHtmlEditCtrlBase::QueryStatus](../Topic/CHtmlEditCtrlBase::QueryStatus.md)|Appelez cette méthode pour interroger l'état de commandes.|  
|[CHtmlEditCtrlBase::RadioButton](../Topic/CHtmlEditCtrlBase::RadioButton.md)|Remplace un contrôle par cases d'option sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::RefreshDocument](../Topic/CHtmlEditCtrlBase::RefreshDocument.md)|Actualise le document actif.|  
|[CHtmlEditCtrlBase::RemoveFormat](../Topic/CHtmlEditCtrlBase::RemoveFormat.md)|Supprime les balises de mise en forme de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SaveAs](../Topic/CHtmlEditCtrlBase::SaveAs.md)|Enregistre la page Web active dans un fichier.|  
|[CHtmlEditCtrlBase::SelectAll](../Topic/CHtmlEditCtrlBase::SelectAll.md)|Sélectionne tout le document.|  
|[CHtmlEditCtrlBase::Set2DPosition](../Topic/CHtmlEditCtrlBase::Set2DPosition.md)|Permet les éléments positionnés à déplacer en la faisant glisser.|  
|[CHtmlEditCtrlBase::SetAbsolutePosition](../Topic/CHtmlEditCtrlBase::SetAbsolutePosition.md)|Définit la propriété de la position d'un élément à « absolute » ou à la « static ».|  
|[CHtmlEditCtrlBase::SetAtomicSelection](../Topic/CHtmlEditCtrlBase::SetAtomicSelection.md)|Définissez le mode de sélection atomique.|  
|[CHtmlEditCtrlBase::SetAutoURLDetectMode](../Topic/CHtmlEditCtrlBase::SetAutoURLDetectMode.md)|Active ou désactive la détection automatique de l'URL de démarrage et l'arrêt.|  
|[CHtmlEditCtrlBase::SetBackColor](../Topic/CHtmlEditCtrlBase::SetBackColor.md)|Définit la couleur d'arrière\-plan de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetBlockFormat](../Topic/CHtmlEditCtrlBase::SetBlockFormat.md)|Définit la balise active de format du bloc.|  
|[CHtmlEditCtrlBase::SetBookMark](../Topic/CHtmlEditCtrlBase::SetBookMark.md)|Crée un point d'ancrage de signet pour la sélection ou le point d'insertion actuel.|  
|[CHtmlEditCtrlBase::SetCSSEditingLevel](../Topic/CHtmlEditCtrlBase::SetCSSEditingLevel.md)|Sélectionne que CSS en auditent \(CSS1 ou CSS2\) l'éditeur prend en charge, le cas échéant.|  
|[CHtmlEditCtrlBase::SetDefaultComposeSettings](../Topic/CHtmlEditCtrlBase::SetDefaultComposeSettings.md)|Appelez cette méthode pour définir la valeur par défaut composent des paramètres.|  
|[CHtmlEditCtrlBase::SetDesignMode](../Topic/CHtmlEditCtrlBase::SetDesignMode.md)|Mode de scénographie.|  
|[CHtmlEditCtrlBase::SetDisableEditFocusUI](../Topic/CHtmlEditCtrlBase::SetDisableEditFocusUI.md)|Désactive la bordure et les handles hachés autour d'un élément qui a le focus de modification.|  
|[CHtmlEditCtrlBase::SetDocumentHTML](../Topic/CHtmlEditCtrlBase::SetDocumentHTML.md)|Définit le HTML du document actif.|  
|[CHtmlEditCtrlBase::SetFontFace](../Topic/CHtmlEditCtrlBase::SetFontFace.md)|Définit la police de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetFontSize](../Topic/CHtmlEditCtrlBase::SetFontSize.md)|Définit la taille de police de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetForeColor](../Topic/CHtmlEditCtrlBase::SetForeColor.md)|Définit la couleur de premier plan \(texte\) de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetIE5PasteMode](../Topic/CHtmlEditCtrlBase::SetIE5PasteMode.md)|Définit l'opération de collage pour être compatible avec Microsoft Internet Explorer 5.|  
|[CHtmlEditCtrlBase::SetLiveResize](../Topic/CHtmlEditCtrlBase::SetLiveResize.md)|Pour mettre à jour le WebBrowser l'apparence d'un élément continuellement pendant un redimensionnement ou une opération mobile.|  
|[CHtmlEditCtrlBase::SetMultiSelect](../Topic/CHtmlEditCtrlBase::SetMultiSelect.md)|Active la sélection multiple.|  
|[CHtmlEditCtrlBase::SetOverrideCursor](../Topic/CHtmlEditCtrlBase::SetOverrideCursor.md)|Ne jamais le contrôle WebBrowser pour modifier le pointeur de la souris.|  
|[CHtmlEditCtrlBase::SetOverwriteMode](../Topic/CHtmlEditCtrlBase::SetOverwriteMode.md)|Basculer le mode de saisie de texte entre l'insertion et la remplacer.|  
|[CHtmlEditCtrlBase::SetRespectVisInDesign](../Topic/CHtmlEditCtrlBase::SetRespectVisInDesign.md)|Masque les éléments invisibles en mode Design.|  
|[CHtmlEditCtrlBase::SetShowAlignedSiteTags](../Topic/CHtmlEditCtrlBase::SetShowAlignedSiteTags.md)|Affiche un glyphe pour tous les éléments qui ont une propriété de **styleFloat** .|  
|[CHtmlEditCtrlBase::SetShowAllTags](../Topic/CHtmlEditCtrlBase::SetShowAllTags.md)|Affiche des glyphes pour afficher l'emplacement de toutes les balises d'un document.|  
|[CHtmlEditCtrlBase::SetShowAreaTags](../Topic/CHtmlEditCtrlBase::SetShowAreaTags.md)|Affiche un glyphe pour toutes les balises de zone.|  
|[CHtmlEditCtrlBase::SetShowBRTags](../Topic/CHtmlEditCtrlBase::SetShowBRTags.md)|Affiche un glyphe pour toutes les balises de Br.|  
|[CHtmlEditCtrlBase::SetShowCommentTags](../Topic/CHtmlEditCtrlBase::SetShowCommentTags.md)|Affiche un glyphe pour toutes les balises de commentaire.|  
|[CHtmlEditCtrlBase::SetShowMiscTags](../Topic/CHtmlEditCtrlBase::SetShowMiscTags.md)|Affiche toutes les balises affichées dans Microsoft Internet Explorer 4,0.|  
|[CHtmlEditCtrlBase::SetShowScriptTags](../Topic/CHtmlEditCtrlBase::SetShowScriptTags.md)|Affiche un glyphe pour toutes les balises de script.|  
|[CHtmlEditCtrlBase::SetShowStyleTags](../Topic/CHtmlEditCtrlBase::SetShowStyleTags.md)|Affiche un glyphe pour toutes les balises de style.|  
|[CHtmlEditCtrlBase::SetShowUnknownTags](../Topic/CHtmlEditCtrlBase::SetShowUnknownTags.md)|Affiche un glyphe pour toutes les balises inconnues.|  
|[CHtmlEditCtrlBase::TextArea](../Topic/CHtmlEditCtrlBase::TextArea.md)|Remplace un contrôle d'entrée sur plusieurs lignes de texte dans la sélection actuelle.|  
|[CHtmlEditCtrlBase::TextBox](../Topic/CHtmlEditCtrlBase::TextBox.md)|Remplace un contrôle de texte dans la sélection actuelle.|  
|[CHtmlEditCtrlBase::UnBookmark](../Topic/CHtmlEditCtrlBase::UnBookmark.md)|Supprime tout signet de la sélection actuelle.|  
|[CHtmlEditCtrlBase::Underline](../Topic/CHtmlEditCtrlBase::Underline.md)|Bascule la sélection actuelle entre souligné et non souligné.|  
|[CHtmlEditCtrlBase::Unlink](../Topic/CHtmlEditCtrlBase::Unlink.md)|Supprime un lien hypertexte de la sélection actuelle.|  
|[CHtmlEditCtrlBase::UnorderList](../Topic/CHtmlEditCtrlBase::UnorderList.md)|Bascule la sélection actuelle entre une liste triée et un bloc de format normal.|  
  
#### Paramètres  
 `T`  
 Nom de la classe dérivée.  
  
## Notes  
 **CHtmlEditCtrlBase** fournit les fonctions membres pour les commandes de l'édition HTML du WebBrowser, telles que [Bold](../Topic/CHtmlEditCtrlBase::Bold.md).  \(Sinon, vous pouvez appeler [ExecCommand](../Topic/CHtmlEditCtrlBase::ExecCommand.md) pour exécuter la commande d' **IDM\_BOLD** .\)  
  
 **CHtmlEditCtrlBase** n'est pas prévu pour vous permettre seule.  Il est conçu pour être une classe de base pour les classes dérivées qui exposent des fonctionnalités d'édition HTML du WebBrowser \(voir [CHtmlEditCtrl](../../mfc/reference/chtmleditctrl-class.md) et le [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)\).  
  
## Hiérarchie d'héritage  
 `CHtmlEditCtrlBase`  
  
## Configuration requise  
 **Header:** afxhtml.h  
  
## Voir aussi  
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [Exemple HTMLEdit](../../top/visual-cpp-samples.md)