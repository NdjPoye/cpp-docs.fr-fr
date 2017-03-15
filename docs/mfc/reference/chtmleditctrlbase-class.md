---
title: Classe de CHtmlEditCtrlBase | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: reference
f1_keywords:
- CHtmlEditCtrlBase
dev_langs:
- C++
helpviewer_keywords:
- CHtmlEditCtrlBase class
ms.assetid: e0cc74b4-8320-4570-b673-16c03d2ae266
caps.latest.revision: 21
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
ms.openlocfilehash: e5541025653cca908d5d0c7666a434aa3f81ab5b
ms.lasthandoff: 02/24/2017

---
# <a name="chtmleditctrlbase-class"></a>CHtmlEditCtrlBase (classe)
Représente un composant d'édition HTML.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
template <class T> class CHtmlEditCtrlBase  
```  
  
## <a name="members"></a>Membres  
  
### <a name="public-methods"></a>M&#233;thodes publiques  
  
|Nom|Description|  
|----------|-----------------|  
|[CHtmlEditCtrlBase::AddToGlyphTable](#addtoglyphtable)|Ajoute une entrée à la table de glyphe, qui spécifie les images à afficher des balises spécifiques en mode Création.|  
|[CHtmlEditCtrlBase::Bold](#bold)|Active ou désactive le gras au texte sélectionné.|  
|[CHtmlEditCtrlBase::Button](#button)|Remplace un contrôle de bouton sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::CheckBox](#checkbox)|Remplace un contrôle case à cocher sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::ClearSelection](#clearselection)|Efface la sélection actuelle.|  
|[CHtmlEditCtrlBase::Copy](#copy)|Copie la sélection actuelle dans le Presse-papiers.|  
|[CHtmlEditCtrlBase::Cut](#cut)|Copie la sélection actuelle dans le Presse-papiers et la supprime ensuite.|  
|[CHtmlEditCtrlBase::Delete](#delete)|Supprime la sélection actuelle.|  
|[CHtmlEditCtrlBase::DropDownBox](#dropdownbox)|Remplace un contrôle de liste déroulante sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::EmptyGlyphTable](#emptyglyphtable)|Supprime toutes les entrées de la table de glyphe qui masque toutes les images affichées pour les balises en mode Création.|  
|[CHtmlEditCtrlBase::ExecCommand](#execcommand)|Exécute une commande.|  
|[CHtmlEditCtrlBase::Font](#font)|Ouvre une boîte de dialogue Police pour permettre aux utilisateurs de modifier la couleur du texte, la police et la taille de police de la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetAbsolutePosition](#getabsoluteposition)|Indique si la propriété de position d’un élément est « absolute ».|  
|[CHtmlEditCtrlBase::GetBackColor](#getbackcolor)|Récupère la couleur d’arrière-plan de la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetBlockFormat](#getblockformat)|Récupère la balise de format bloc actuel.|  
|[CHtmlEditCtrlBase::GetBlockFormatNames](#getblockformatnames)|Récupère les chaînes correspondant aux balises format bloc disponible.|  
|[CHtmlEditCtrlBase::GetBookMark](#getbookmark)|Récupère le nom d’une ancre de signet.|  
|[CHtmlEditCtrlBase::GetDocument](#getdocument)|Récupère l’objet document.|  
|[CHtmlEditCtrlBase::GetDocumentHTML](#getdocumenthtml)|Récupère le code HTML du document actif.|  
|[CHtmlEditCtrlBase::GetDocumentTitle](#getdocumenttitle)|Récupère le titre du document.|  
|[CHtmlEditCtrlBase::GetEvent](#getevent)|Récupère un pointeur d’interface vers l’objet d’événement qui contient des informations relatives à l’événement le plus récent.|  
|[CHtmlEditCtrlBase::GetEventSrcElement](#geteventsrcelement)|Récupère l’objet qui a déclenché l’événement.|  
|[CHtmlEditCtrlBase::GetFontFace](#getfontface)|Récupère le nom de la police pour la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetFontSize](#getfontsize)|Récupère la taille de police pour la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetForeColor](#getforecolor)|Récupère la couleur de premier plan (texte) de la sélection actuelle.|  
|[CHtmlEditCtrlBase::GetFrameZone](#getframezone)|Renvoie la zone de sécurité de la page actuelle dans le navigateur web.|  
|[CHtmlEditCtrlBase::GetIsDirty](#getisdirty)|Indique si le document HTML a été modifiée.|  
|[CHtmlEditCtrlBase::GetShowAlignedSiteTags](#getshowalignedsitetags)|Retourne si un glyphe s’affiche pour tous les éléments qui ont un **styleFloat** propriété.|  
|[CHtmlEditCtrlBase::GetShowAllTags](#getshowalltags)|Retourne si le contrôle WebBrowser affiche des glyphes pour afficher l’emplacement de toutes les balises dans un document.|  
|[CHtmlEditCtrlBase::GetShowAreaTags](#getshowareatags)|Récupère si le contrôle WebBrowser affiche un glyphe pour les balises de la zone.|  
|[CHtmlEditCtrlBase::GetShowBRTags](#getshowbrtags)|Récupère si le contrôle WebBrowser affiche un glyphe de balises br.|  
|[CHtmlEditCtrlBase::GetShowCommentTags](#getshowcommenttags)|Récupère si le contrôle WebBrowser affiche un glyphe pour les balises de commentaire.|  
|[CHtmlEditCtrlBase::GetShowMiscTags](#getshowmisctags)|Récupère si le contrôle WebBrowser affiche toutes les balises affichées dans Microsoft Internet Explorer 4.0.|  
|[CHtmlEditCtrlBase::GetShowScriptTags](#getshowscripttags)|Récupère si le contrôle WebBrowser affiche un glyphe pour toutes les balises de script.|  
|[CHtmlEditCtrlBase::GetShowStyleTags](#getshowstyletags)|Récupère si le contrôle WebBrowser affiche un glyphe pour toutes les balises de style.|  
|[CHtmlEditCtrlBase::GetShowUnknownTags](#getshowunknowntags)|Récupère si le contrôle WebBrowser affiche un glyphe pour toutes les balises inconnus.|  
|[CHtmlEditCtrlBase::HorizontalLine](#horizontalline)|Remplace une ligne horizontale sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::HyperLink](#hyperlink)|Insère un lien hypertexte sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::IE50Paste](#ie50paste)|Effectue une opération de collage compatible avec Microsoft Internet Explorer 5.|  
|[CHtmlEditCtrlBase::Iframe](#iframe)|Remplace un cadre inséré sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Image](#image)|Remplace une image sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Indent](#indent)|Augmente le retrait du texte sélectionné par incrément d’une mise en retrait.|  
|[CHtmlEditCtrlBase::InsFieldSet](#insfieldset)|Remplace une zone sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputButton](#insinputbutton)|Remplace un contrôle de bouton sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputHidden](#insinputhidden)|Insère un contrôle masqué sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputImage](#insinputimage)|Remplace un contrôle image sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputPassword](#insinputpassword)|Remplace un contrôle de mot de passe sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputReset](#insinputreset)|Remplace un contrôle de réinitialisation sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputSubmit](#insinputsubmit)|Remplace un contrôle envoyer sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::InsInputUpload](#insinputupload)|Remplace un contrôle de téléchargement de fichiers sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Is1DElement](#is1delement)|Détermine si un élément est positionné de façon statique.|  
|[CHtmlEditCtrlBase::Is2DElement](#is2delement)|Détermine si un élément est positionné.|  
|[CHtmlEditCtrlBase::Italic](#italic)|Active ou désactive la sélection actuelle en italique.|  
|[CHtmlEditCtrlBase::JustifyCenter](#justifycenter)|Les centres du formater le bloc dans lequel se trouve la sélection actuelle.|  
|[CHtmlEditCtrlBase::JustifyLeft](#justifyleft)|Aligne à gauche le formater le bloc dans lequel se trouve la sélection actuelle.|  
|[CHtmlEditCtrlBase::JustifyRight](#justifyright)|Aligne à droite le formater le bloc dans lequel se trouve la sélection actuelle.|  
|[CHtmlEditCtrlBase::ListBox](#listbox)|Remplace le contrôle de sélection de zone de liste sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Marquee](#marquee)|Remplace un texte défilant vide sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::NewDocument](#newdocument)|Crée un nouveau document.|  
|[CHtmlEditCtrlBase::OrderList](#orderlist)|Active ou désactive la sélection actuelle entre une liste ordonnée et un bloc de format normal.|  
|[CHtmlEditCtrlBase::Outdent](#outdent)|Diminue d’un incrément le retrait du bloc de format dans lequel se trouve la sélection actuelle.|  
|[CHtmlEditCtrlBase::Paragraph](#paragraph)|Remplace un saut de ligne sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::Paste](#paste)|Remplace le contenu du Presse-papiers sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::PrintDocument](#printdocument)|Imprime le document actif.|  
|[CHtmlEditCtrlBase::PrintPreview](#printpreview)|Ouvre la fenêtre Aperçu avant impression du document actif à l’aide du modèle de l’aperçu avant impression par défaut ou un modèle personnalisé.|  
|[CHtmlEditCtrlBase::QueryStatus](#querystatus)|Appelez cette méthode pour demander l’état des commandes.|  
|[CHtmlEditCtrlBase::RadioButton](#radiobutton)|Remplace un contrôle de case d’option sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::RefreshDocument](#refreshdocument)|Actualise le document actif.|  
|[CHtmlEditCtrlBase::RemoveFormat](#removeformat)|Supprime les balises de mise en forme de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SaveAs](#saveas)|Enregistre la page Web actuelle dans un fichier.|  
|[CHtmlEditCtrlBase::SelectAll](#selectall)|Sélectionne tout le document.|  
|[CHtmlEditCtrlBase::Set2DPosition](#set2dposition)|Permet de déplacer en faisant glisser des éléments à positionnement absolu.|  
|[CHtmlEditCtrlBase::SetAbsolutePosition](#setabsoluteposition)|Définit la propriété de position d’un élément « absolute » ou « statique ».|  
|[CHtmlEditCtrlBase::SetAtomicSelection](#setatomicselection)|Définir le mode de sélection atomique.|  
|[CHtmlEditCtrlBase::SetAutoURLDetectMode](#setautourldetectmode)|Active la détection automatique des URL et désactive.|  
|[CHtmlEditCtrlBase::SetBackColor](#setbackcolor)|Définit la couleur d’arrière-plan de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetBlockFormat](#setblockformat)|Définit la balise de format bloc actuel.|  
|[CHtmlEditCtrlBase::SetBookMark](#setbookmark)|Crée une ancre de signet pour le point d’insertion ou de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetCSSEditingLevel](#setcsseditinglevel)|Sélectionne le niveau CSS (CSS1 ou CSS2) l’éditeur prendra en charge, le cas échéant.|  
|[CHtmlEditCtrlBase::SetDefaultComposeSettings](#setdefaultcomposesettings)|Appel de cette méthode pour définir la valeur par défaut des paramètres de composition.|  
|[CHtmlEditCtrlBase::SetDesignMode](#setdesignmode)|Définir le mode Création.|  
|[CHtmlEditCtrlBase::SetDisableEditFocusUI](#setdisableeditfocusui)|Désactive la bordure hachurée et gère autour d’un élément qui a le focus de la modifier.|  
|[CHtmlEditCtrlBase::SetDocumentHTML](#setdocumenthtml)|Définit le code HTML du document actif.|  
|[CHtmlEditCtrlBase::SetFontFace](#setfontface)|Définit la police pour la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetFontSize](#setfontsize)|Définit la taille de police pour la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetForeColor](#setforecolor)|Définit la couleur de premier plan (texte) de la sélection actuelle.|  
|[CHtmlEditCtrlBase::SetIE5PasteMode](#setie5pastemode)|Définit l’opération de collage pour être compatible avec Microsoft Internet Explorer 5.|  
|[CHtmlEditCtrlBase::SetLiveResize](#setliveresize)|Provoque le contrôle WebBrowser à jour l’apparence d’un élément en permanence pendant une opération de redimensionnement ou le déplacement.|  
|[CHtmlEditCtrlBase::SetMultiSelect](#setmultiselect)|Permet la sélection multiple.|  
|[CHtmlEditCtrlBase::SetOverrideCursor](#setoverridecursor)|Commandes WebBrowser jamais à modifier le pointeur de la souris.|  
|[CHtmlEditCtrlBase::SetOverwriteMode](#setoverwritemode)|Active/désactive le mode de saisie de texte entre les insérer, remplacer.|  
|[CHtmlEditCtrlBase::SetRespectVisInDesign](#setrespectvisindesign)|Masque les éléments invisibles dans ce mode.|  
|[CHtmlEditCtrlBase::SetShowAlignedSiteTags](#setshowalignedsitetags)|Affiche un glyphe pour tous les éléments qui ont un **styleFloat** propriété.|  
|[CHtmlEditCtrlBase::SetShowAllTags](#setshowalltags)|Afficher des glyphes pour afficher l’emplacement de toutes les balises dans un document.|  
|[CHtmlEditCtrlBase::SetShowAreaTags](#setshowareatags)|Affiche un glyphe pour toutes les balises de la zone.|  
|[CHtmlEditCtrlBase::SetShowBRTags](#setshowbrtags)|Affiche un glyphe pour toutes les balises br.|  
|[CHtmlEditCtrlBase::SetShowCommentTags](#setshowcommenttags)|Affiche un glyphe pour toutes les balises de commentaire.|  
|[CHtmlEditCtrlBase::SetShowMiscTags](#setshowmisctags)|Affiche toutes les balises affichées dans Microsoft Internet Explorer 4.0.|  
|[CHtmlEditCtrlBase::SetShowScriptTags](#setshowscripttags)|Affiche un glyphe pour toutes les balises de script.|  
|[CHtmlEditCtrlBase::SetShowStyleTags](#setshowstyletags)|Affiche un glyphe pour toutes les balises de style.|  
|[CHtmlEditCtrlBase::SetShowUnknownTags](#setshowunknowntags)|Affiche un glyphe pour toutes les balises inconnus.|  
|[CHtmlEditCtrlBase::TextArea](#textarea)|Remplace un contrôle d’entrée de texte multiligne sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::TextBox](#textbox)|Remplace un contrôle de texte sur la sélection actuelle.|  
|[CHtmlEditCtrlBase::UnBookmark](#unbookmark)|Supprime les signets dans la sélection actuelle.|  
|[CHtmlEditCtrlBase::Underline](#underline)|Active ou désactive la sélection actuelle entre souligné et non souligné.|  
|[CHtmlEditCtrlBase::Unlink](#unlink)|Supprime un lien hypertexte de la sélection actuelle.|  
|[CHtmlEditCtrlBase::UnorderList](#unorderlist)|Active ou désactive la sélection actuelle entre une liste ordonnée et un bloc de format normal.|  
  
#### <a name="parameters"></a>Paramètres  
 `T`  
 Nom de la classe dérivée.  
  
## <a name="remarks"></a>Notes  
 **CHtmlEditCtrlBase** fournit des fonctions membres pour HTML de WebBrowser la modification des commandes, telles que [gras](#bold). (Vous pouvez également appeler [ExecCommand](#execcommand) pour exécuter le **IDM_BOLD** commande.)  
  
 **CHtmlEditCtrlBase** n’est pas censé fonctionner de manière autonome. Il est conçu pour être une classe de base pour les classes dérivées qui exposent la fonctionnalité de WebBrowser d’édition HTML (voir [CHtmlEditCtrl](../../mfc/reference/chtmleditctrl-class.md) et [CHtmlEditView](../../mfc/reference/chtmleditview-class.md)).  
  
## <a name="inheritance-hierarchy"></a>Hiérarchie d’héritage  
 `CHtmlEditCtrlBase`  
  
## <a name="requirements"></a>Spécifications  
 **En-tête :** afxhtml.h  
  
##  <a name="a-nameaddtoglyphtablea--chtmleditctrlbaseaddtoglyphtable"></a><a name="addtoglyphtable"></a>CHtmlEditCtrlBase::AddToGlyphTable  
 Ajoute une entrée à la table de glyphe, qui spécifie les images à afficher des balises spécifiques en mode Création.  
  
```  
HRESULT AddToGlyphTable(
    LPCTSTR szTag,  
    LPCTSTR szImgUrl,  
    unsigned short nTagType,  
    unsigned short nAlignment,  
    unsigned short nPosInfo,  
    unsigned short nDirection,  
    unsigned int nImgWidth,  
    unsigned int nImgHeight) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szTag`  
 Nom de balise (par exemple, « P » ou « table »).  
  
 *szImgUrl*  
 L’URL de l’image.  
  
 *nTagType*  
 Type de balise : 0 signifie que l’image est à la balise d’ouverture. 1 signifie que l’image concerne uniquement la balise de fermeture. 2 signifie l’image pour l’ouverture et la fermeture des balises. Balises uniques comme br et commentaire doivent être ajoutés avec la valeur 0 du type de balise.  
  
 *nAlignment*  
 Alignement (éléments rectangulaires uniquement) : ce paramètre indique que l’image est un élément avec un attribut d’alignement. Gauche = 0, centre = 1, droite = 2 et non défini = 3. Gauche, droite ou centre attributs doivent être définie explicitement sur l’élément.  
  
 *nPosInfo*  
 Des informations de positionnement. Détermine la valeur de positionnement (CSS) le glyphe s’applique, où statiques des feuilles de style en cascade positionnement = 0, le positionnement absolu = 1, positionnement relatif = 2 et tous les = 3. Ce champ vous permet de spécifier un glyphe pour une balise lorsqu’il n’est pas placé et un autre glyphes pour afficher un point d’ancrage lorsque la balise est positionnée.  
  
 *nDirection*  
 La direction. Ce paramètre spécifie l’image d’une balise en fonction de l’ordre de lecture de la langue actuelle. la valeur 0 spécifie de gauche à droite, 1 indique de droite à gauche, 2 spécifie de haut en bas, 3 spécifie de bas en haut et 4 spécifie tous les. Normalement, vous définissez ce champ sur 4.  
  
 *nImgWidth*  
 La largeur de l’image en pixels.  
  
 *nImgHeight*  
 La hauteur de l’image en pixels.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations sur les paramètres, consultez « Format de chaîne glyphe Table » dans [à l’aide de glyphes modification](https://msdn.microsoft.com/library/aa969614.aspx).  
  
 Cette méthode envoie le [IDM_ADDTOGLYPHTABLE l’ID de commande](https://msdn.microsoft.com/library/aa769891.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namebolda--chtmleditctrlbasebold"></a><a name="bold"></a>CHtmlEditCtrlBase::Bold  
 Active ou désactive le gras au texte sélectionné.  
  
```  
HRESULT Bold() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_BOLD l’ID de commande](https://msdn.microsoft.com/library/aa769861.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namebuttona--chtmleditctrlbasebutton"></a><a name="button"></a>CHtmlEditCtrlBase::Button  
 Remplace un contrôle de bouton sur la sélection actuelle.  
  
```  
HRESULT Button(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle de bouton.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_BUTTON l’ID de commande](https://msdn.microsoft.com/library/aa769966.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namecheckboxa--chtmleditctrlbasecheckbox"></a><a name="checkbox"></a>CHtmlEditCtrlBase::CheckBox  
 Remplace un contrôle case à cocher sur la sélection actuelle.  
  
```  
HRESULT CheckBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle de case à cocher.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_CHECKBOX l’ID de commande](https://msdn.microsoft.com/library/aa769972.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameclearselectiona--chtmleditctrlbaseclearselection"></a><a name="clearselection"></a>CHtmlEditCtrlBase::ClearSelection  
 Efface la sélection actuelle.  
  
```  
HRESULT ClearSelection() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_CLEARSELECTION l’ID de commande](https://msdn.microsoft.com/library/aa770038.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namecopya--chtmleditctrlbasecopy"></a><a name="copy"></a>CHtmlEditCtrlBase::Copy  
 Copie la sélection actuelle dans le Presse-papiers.  
  
```  
HRESULT Copy() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_COPY l’ID de commande](https://msdn.microsoft.com/library/aa769872.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namecuta--chtmleditctrlbasecut"></a><a name="cut"></a>CHtmlEditCtrlBase::Cut  
 Copie la sélection actuelle dans le Presse-papiers et la supprime ensuite.  
  
```  
HRESULT Cut() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_CUT l’ID de commande](https://msdn.microsoft.com/library/aa769875.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namedeletea--chtmleditctrlbasedelete"></a><a name="delete"></a>CHtmlEditCtrlBase::Delete  
 Supprime la sélection actuelle.  
  
```  
HRESULT Delete() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_DELETE l’ID de commande](https://msdn.microsoft.com/library/aa769876.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namedropdownboxa--chtmleditctrlbasedropdownbox"></a><a name="dropdownbox"></a>CHtmlEditCtrlBase::DropDownBox  
 Remplace un contrôle de liste déroulante sur la sélection actuelle.  
  
```  
HRESULT DropDownBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle de liste déroulante.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_DROPDOWNBOX l’ID de commande](https://msdn.microsoft.com/library/aa769984.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameemptyglyphtablea--chtmleditctrlbaseemptyglyphtable"></a><a name="emptyglyphtable"></a>CHtmlEditCtrlBase::EmptyGlyphTable  
 Supprime toutes les entrées de la table de glyphe qui masque toutes les images affichées pour les balises en mode Création.  
  
```  
HRESULT EmptyGlyphTable() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_EMPTYGLYPHTABLE l’ID de commande](https://msdn.microsoft.com/library/aa769907.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameexeccommanda--chtmleditctrlbaseexeccommand"></a><a name="execcommand"></a>CHtmlEditCtrlBase::ExecCommand  
 Exécute une commande.  
  
```  
HRESULT ExecCommand(
    long cmdID,  
    long cmdExecOpt,  
    VARIANT* pInVar = NULL,  
    VARIANT* pOutVar = NULL) const;  
  
HRESULT ExecCommand(
    const GUID* pGuid,  
    long cmdID,  
    long cmdExecOpt,  
    VARIANT* pInVar = NULL,  
    VARIANT* pOutVar = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `cmdID`  
 L’ID de commande à exécuter. Pour obtenir la liste, consultez [MSHTML les identificateurs de commande](https://msdn.microsoft.com/library/aa741315.aspx).  
  
 `cmdExecOpt`  
 Valeurs extraites à partir de la [OLECMDEXECOPT](http://msdn.microsoft.com/library/windows/desktop/ms683930) énumération décrivant comment l’objet doit exécuter la commande.  
  
 *pInVar*  
 Les arguments d’entrée.  
  
 *pOutVar*  
 La sortie de commande.  
  
 *pGuid*  
 Le GUID du groupe de commandes.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode fournit les fonctionnalités de [IOleCommandTarget::Exec](http://msdn.microsoft.com/library/windows/desktop/ms690300).  
  
##  <a name="a-namefonta--chtmleditctrlbasefont"></a><a name="font"></a>CHtmlEditCtrlBase::Font  
 Ouvre une boîte de dialogue Police pour permettre aux utilisateurs de modifier la couleur du texte, la police et la taille de police de la sélection actuelle.  
  
```  
HRESULT Font() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_FONT l’ID de commande](https://msdn.microsoft.com/library/aa769913.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namegetabsolutepositiona--chtmleditctrlbasegetabsoluteposition"></a><a name="getabsoluteposition"></a>CHtmlEditCtrlBase::GetAbsolutePosition  
 Indique si la propriété de position d’un élément est « absolute ».  
  
```  
HRESULT GetAbsolutePosition(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si la propriété de position de l’élément est définie sur « absolute ».  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [IDM_ABSOLUTE_POSITION l’ID de commande](https://msdn.microsoft.com/library/aa769889.aspx).  
  
##  <a name="a-namegetbackcolora--chtmleditctrlbasegetbackcolor"></a><a name="getbackcolor"></a>CHtmlEditCtrlBase::GetBackColor  
 Récupère la couleur d’arrière-plan de la sélection actuelle.  
  
```  
HRESULT GetBackColor(int& nColor) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nColor`  
 Couleur d'arrière-plan.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_BACKCOLOR l’ID de commande](https://msdn.microsoft.com/library/aa769858.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namegetblockformata--chtmleditctrlbasegetblockformat"></a><a name="getblockformat"></a>CHtmlEditCtrlBase::GetBlockFormat  
 Récupère la balise de format bloc actuel.  
  
```  
HRESULT GetBlockFormat(CString& strFormat) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *strFormat*  
 La balise de format bloc actuel.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_BLOCKFMT l’ID de commande](https://msdn.microsoft.com/library/aa769883.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namegetblockformatnamesa--chtmleditctrlbasegetblockformatnames"></a><a name="getblockformatnames"></a>CHtmlEditCtrlBase::GetBlockFormatNames  
 Récupère les chaînes correspondant aux balises format bloc disponible.  
  
```  
HRESULT GetBlockFormatNames(CStringArray& sa) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *association de sécurité*  
 Les balises de format bloc disponible, comme un tableau de chaînes.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_GETBLOCKFMTS ID de commande](https://msdn.microsoft.com/library/aa769884.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namegetbookmarka--chtmleditctrlbasegetbookmark"></a><a name="getbookmark"></a>CHtmlEditCtrlBase::GetBookMark  
 Récupère le nom d’une ancre de signet.  
  
```  
HRESULT GetBookMark(CString& strAnchor) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *strAnchor*  
 Le nom d’une ancre de signet.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [IDM_BOOKMARK l’ID de commande](https://msdn.microsoft.com/library/aa769873.aspx).  
  
##  <a name="a-namegetdocumenta--chtmleditctrlbasegetdocument"></a><a name="getdocument"></a>CHtmlEditCtrlBase::GetDocument  
 Récupère l’objet document.  
  
```  
HRESULT GetDocument(IHTMLDocument2** ppDoc) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `ppDoc`  
 L’objet document.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-namegetdocumenthtmla--chtmleditctrlbasegetdocumenthtml"></a><a name="getdocumenthtml"></a>CHtmlEditCtrlBase::GetDocumentHTML  
 Récupère le code HTML du document actif.  
  
```  
HRESULT GetDocumentHTML(CString& szHTML) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szHTML`  
 Le code HTML.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-namegetdocumenttitlea--chtmleditctrlbasegetdocumenttitle"></a><a name="getdocumenttitle"></a>CHtmlEditCtrlBase::GetDocumentTitle  
 Récupère le titre du document.  
  
```  
HRESULT GetDocumentTitle(CString& szTitle) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *szTitle*  
 Le titre du document.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-namegeteventa--chtmleditctrlbasegetevent"></a><a name="getevent"></a>CHtmlEditCtrlBase::GetEvent  
 Récupère un pointeur d’interface vers l’objet d’événement qui contient des informations relatives à l’événement le plus récent.  
  
```  
HRESULT GetEvent(IHTMLEventObj** ppEventObj) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `ppEventObj`  
 Objet événement.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-namegeteventsrcelementa--chtmleditctrlbasegeteventsrcelement"></a><a name="geteventsrcelement"></a>CHtmlEditCtrlBase::GetEventSrcElement  
 Récupère l’objet qui a déclenché l’événement.  
  
```  
HRESULT GetEventSrcElement(IHTMLElement** ppSrcElement) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *ppSrcElement*  
 L’élément qui a déclenché l’événement.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-namegetfontfacea--chtmleditctrlbasegetfontface"></a><a name="getfontface"></a>CHtmlEditCtrlBase::GetFontFace  
 Récupère le nom de la police pour la sélection actuelle.  
  
```  
HRESULT GetFontFace(CString& strFace) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `strFace`  
 Le nom de la police.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Si la sélection actuelle utilise plusieurs polices, `strFace` sera une chaîne vide.  
  
 Cette méthode envoie le [IDM_FONTNAME l’ID de commande](https://msdn.microsoft.com/library/aa769880.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namegetfontsizea--chtmleditctrlbasegetfontsize"></a><a name="getfontsize"></a>CHtmlEditCtrlBase::GetFontSize  
 Récupère la taille de police pour la sélection actuelle.  
  
```  
HRESULT GetFontSize(short& nSize) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nSize`  
 La taille de police.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la taille de police HTML (1-7). Retourne 0 si la sélection contient plusieurs tailles de police.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_FONTSIZE l’ID de commande](https://msdn.microsoft.com/library/aa769881.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namegetforecolora--chtmleditctrlbasegetforecolor"></a><a name="getforecolor"></a>CHtmlEditCtrlBase::GetForeColor  
 Récupère la couleur de premier plan (texte) de la sélection actuelle.  
  
```  
HRESULT GetForeColor(int& nColor);
```  
  
### <a name="parameters"></a>Paramètres  
 `nColor`  
 La couleur de premier plan.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_FORECOLOR l’ID de commande](https://msdn.microsoft.com/library/aa769882.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namegetframezonea--chtmleditctrlbasegetframezone"></a><a name="getframezone"></a>CHtmlEditCtrlBase::GetFrameZone  
 Renvoie la zone de sécurité de la page actuelle dans le navigateur web.  
  
```  
HRESULT GetFrameZone(short& nZone) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *nZone*  
 La zone de sécurité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_GETFRAMEZONE l’ID de commande](https://msdn.microsoft.com/library/aa769916.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namegetisdirtya--chtmleditctrlbasegetisdirty"></a><a name="getisdirty"></a>CHtmlEditCtrlBase::GetIsDirty  
 Indique si le document HTML a été modifiée.  
  
```  
HRESULT GetIsDirty() const;  
```  
  
### <a name="remarks"></a>Notes  
 Indique si le document a changé. `GetIsDirty`Retourne un `HRESULT` de [IPersistStorage::IsDirty](http://msdn.microsoft.com/library/windows/desktop/ms683910).  
  
##  <a name="a-namegetshowalignedsitetagsa--chtmleditctrlbasegetshowalignedsitetags"></a><a name="getshowalignedsitetags"></a>CHtmlEditCtrlBase::GetShowAlignedSiteTags  
 Retourne si un glyphe s’affiche pour tous les éléments qui ont un **styleFloat** propriété.  
  
```  
HRESULT GetShowAlignedSiteTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si un glyphe s’affiche pour tous les éléments qui ont un **styleFloat** propriété ; false si aucun glyphe ne s’affiche.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [IDM_SHOWALIGNEDSITETAGS l’ID de commande](https://msdn.microsoft.com/library/aa769947.aspx).  
  
##  <a name="a-namegetshowalltagsa--chtmleditctrlbasegetshowalltags"></a><a name="getshowalltags"></a>CHtmlEditCtrlBase::GetShowAllTags  
 Retourne si le contrôle WebBrowser affiche des glyphes pour afficher l’emplacement de toutes les balises dans un document.  
  
```  
HRESULT GetShowAllTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si le contrôle WebBrowser affiche des glyphes pour afficher l’emplacement de toutes les balises dans un document ; False si ce n’est pas le cas.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [IDM_SHOWALLTAGS l’ID de commande](https://msdn.microsoft.com/library/aa769948.aspx).  
  
##  <a name="a-namegetshowareatagsa--chtmleditctrlbasegetshowareatags"></a><a name="getshowareatags"></a>CHtmlEditCtrlBase::GetShowAreaTags  
 Récupère si le contrôle WebBrowser affiche un glyphe pour les balises de la zone.  
  
```  
HRESULT GetShowAreaTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si le contrôle WebBrowser affiche un glyphe pour les balises de zone, false si elle n’est pas le cas.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [IDM_SHOWAREATAGS l’ID de commande](https://msdn.microsoft.com/library/aa769949.aspx).  
  
##  <a name="a-namegetshowbrtagsa--chtmleditctrlbasegetshowbrtags"></a><a name="getshowbrtags"></a>CHtmlEditCtrlBase::GetShowBRTags  
 Récupère si le contrôle WebBrowser affiche un glyphe de balises br.  
  
```  
HRESULT GetShowBRTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si le contrôle WebBrowser affiche un glyphe de balises br, false si ce n’est pas.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [IDM_SHOWWBRTAGS l’ID de commande](https://msdn.microsoft.com/library/aa769956.aspx).  
  
##  <a name="a-namegetshowcommenttagsa--chtmleditctrlbasegetshowcommenttags"></a><a name="getshowcommenttags"></a>CHtmlEditCtrlBase::GetShowCommentTags  
 Récupère si le contrôle WebBrowser affiche un glyphe pour les balises de commentaire.  
  
```  
HRESULT GetShowCommentTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si le contrôle WebBrowser affiche un glyphe pour les balises de commentaire, false si ce n’est pas.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [IDM_SHOWCOMMENTTAGS l’ID de commande](https://msdn.microsoft.com/library/aa769950.aspx).  
  
##  <a name="a-namegetshowmisctagsa--chtmleditctrlbasegetshowmisctags"></a><a name="getshowmisctags"></a>CHtmlEditCtrlBase::GetShowMiscTags  
 Récupère si le contrôle WebBrowser affiche toutes les balises affichées dans Microsoft Internet Explorer 4.0.  
  
```  
HRESULT GetShowMiscTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si le contrôle WebBrowser affiche toutes les balises affichées dans Microsoft Internet Explorer 4.0, la valeur false si ce n’est pas le cas.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [IDM_SHOWMISCTAGS l’ID de commande](https://msdn.microsoft.com/library/aa769952.aspx).  
  
##  <a name="a-namegetshowscripttagsa--chtmleditctrlbasegetshowscripttags"></a><a name="getshowscripttags"></a>CHtmlEditCtrlBase::GetShowScriptTags  
 Récupère si le contrôle WebBrowser affiche un glyphe pour toutes les balises de script.  
  
```  
HRESULT GetShowScriptTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si le contrôle WebBrowser affiche un glyphe pour toutes les balises de script, false si elle n’est pas le cas.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [IDM_SHOWSCRIPTTAGS l’ID de commande](https://msdn.microsoft.com/library/aa769953.aspx).  
  
##  <a name="a-namegetshowstyletagsa--chtmleditctrlbasegetshowstyletags"></a><a name="getshowstyletags"></a>CHtmlEditCtrlBase::GetShowStyleTags  
 Récupère si le contrôle WebBrowser affiche un glyphe pour toutes les balises de style.  
  
```  
HRESULT GetShowStyleTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si le contrôle WebBrowser affiche un glyphe pour toutes les balises de style, false s’il n’existe pas  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Pour plus d’informations, consultez [IDM_SHOWSTYLETAGS l’ID de commande](https://msdn.microsoft.com/library/aa769954.aspx).  
  
##  <a name="a-namegetshowunknowntagsa--chtmleditctrlbasegetshowunknowntags"></a><a name="getshowunknowntags"></a>CHtmlEditCtrlBase::GetShowUnknownTags  
 Récupère si le contrôle WebBrowser affiche un glyphe pour toutes les balises inconnus.  
  
```  
HRESULT GetShowUnknownTags(bool& bCurValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bCurValue`  
 True si le contrôle WebBrowser affiche un glyphe pour toutes les balises inconnus, false si elle n’est pas le cas.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Pour plus d’informations, consultez [IDM_SHOWUNKNOWNTAGS l’ID de commande](https://msdn.microsoft.com/library/aa769955.aspx).  
  
##  <a name="a-namehorizontallinea--chtmleditctrlbasehorizontalline"></a><a name="horizontalline"></a>CHtmlEditCtrlBase::HorizontalLine  
 Remplace une ligne horizontale sur la sélection actuelle.  
  
```  
HRESULT HorizontalLine(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *szID*  
 L’ID de la ligne horizontale.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_HORIZONTALLINE l’ID de commande](https://msdn.microsoft.com/library/aa769968.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namehyperlinka--chtmleditctrlbasehyperlink"></a><a name="hyperlink"></a>CHtmlEditCtrlBase::HyperLink  
 Insère un lien hypertexte sur la sélection actuelle.  
  
```  
HRESULT HyperLink(LPCTSTR szUrl = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szUrl`  
 L’URL du lien hypertexte.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_HYPERLINK l’ID de commande](https://msdn.microsoft.com/library/aa769874.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameie50pastea--chtmleditctrlbaseie50paste"></a><a name="ie50paste"></a>CHtmlEditCtrlBase::IE50Paste  
 Effectue une opération de collage est compatible avec Internet Explorer 5.  
  
```  
HRESULT IE50Paste(LPCTSTR szData) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szData`  
 Chaîne à coller.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_IE50_PASTE l’ID de commande](https://msdn.microsoft.com/library/aa769922.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameiframea--chtmleditctrlbaseiframe"></a><a name="iframe"></a>CHtmlEditCtrlBase::Iframe  
 Remplace un cadre inséré sur la sélection actuelle.  
  
```  
HRESULT Iframe(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 ID du cadre inséré.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_IFRAME l’ID de commande](https://msdn.microsoft.com/library/aa769969.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameimagea--chtmleditctrlbaseimage"></a><a name="image"></a>CHtmlEditCtrlBase::Image  
 Remplace une image sur la sélection actuelle.  
  
```  
HRESULT Image(LPCTSTR szUrl = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szUrl`  
 Le chemin et le nom de l’image à insérer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_IMAGE l’ID de commande](https://msdn.microsoft.com/library/aa769970.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameindenta--chtmleditctrlbaseindent"></a><a name="indent"></a>CHtmlEditCtrlBase::Indent  
 Augmente le retrait du texte sélectionné par incrément d’une mise en retrait.  
  
```  
HRESULT Indent() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_INDENT l’ID de commande](https://msdn.microsoft.com/library/aa769963.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameinsfieldseta--chtmleditctrlbaseinsfieldset"></a><a name="insfieldset"></a>CHtmlEditCtrlBase::InsFieldSet  
 Remplace une zone sur la sélection actuelle.  
  
```  
HRESULT InsFieldSet(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID de la zone.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_INSFIELDSET l’ID de commande](https://msdn.microsoft.com/library/aa769967.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameinsinputbuttona--chtmleditctrlbaseinsinputbutton"></a><a name="insinputbutton"></a>CHtmlEditCtrlBase::InsInputButton  
 Remplace un contrôle de bouton sur la sélection actuelle.  
  
```  
HRESULT InsInputButton(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle button.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_INSINPUTBUTTON l’ID de commande](https://msdn.microsoft.com/library/aa769971.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameinsinputhiddena--chtmleditctrlbaseinsinputhidden"></a><a name="insinputhidden"></a>CHtmlEditCtrlBase::InsInputHidden  
 Insère un contrôle masqué sur la sélection actuelle.  
  
```  
HRESULT InsInputHidden(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID pour le contrôle masqué.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_INSINPUTHIDDEN l’ID de commande](https://msdn.microsoft.com/library/aa769974.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameinsinputimagea--chtmleditctrlbaseinsinputimage"></a><a name="insinputimage"></a>CHtmlEditCtrlBase::InsInputImage  
 Remplace un contrôle image sur la sélection actuelle.  
  
```  
HRESULT InsInputImage(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle d’image.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_INSINPUTIMAGE l’ID de commande](https://msdn.microsoft.com/library/aa769975.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameinsinputpassworda--chtmleditctrlbaseinsinputpassword"></a><a name="insinputpassword"></a>CHtmlEditCtrlBase::InsInputPassword  
 Remplace un contrôle de mot de passe sur la sélection actuelle.  
  
```  
HRESULT InsInputPassword(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle de mot de passe.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_INSINPUTPASSWORD l’ID de commande](https://msdn.microsoft.com/library/aa769976.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameinsinputreseta--chtmleditctrlbaseinsinputreset"></a><a name="insinputreset"></a>CHtmlEditCtrlBase::InsInputReset  
 Remplace un contrôle de réinitialisation sur la sélection actuelle.  
  
```  
HRESULT InsInputReset(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle de réinitialisation.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_INSINPUTRESET l’ID de commande](https://msdn.microsoft.com/library/aa769978.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameinsinputsubmita--chtmleditctrlbaseinsinputsubmit"></a><a name="insinputsubmit"></a>CHtmlEditCtrlBase::InsInputSubmit  
 Remplace un contrôle envoyer sur la sélection actuelle.  
  
```  
HRESULT InsInputSubmit(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle à envoyer.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_INSINPUTSUBMIT l’ID de commande](https://msdn.microsoft.com/library/aa769979.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameinsinputuploada--chtmleditctrlbaseinsinputupload"></a><a name="insinputupload"></a>CHtmlEditCtrlBase::InsInputUpload  
 Remplace un contrôle de téléchargement de fichiers sur la sélection actuelle.  
  
```  
HRESULT InsInputUpload(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID pour le contrôle de téléchargement de fichier.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_INSINPUTUPLOAD l’ID de commande](https://msdn.microsoft.com/library/aa769973.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameis1delementa--chtmleditctrlbaseis1delement"></a><a name="is1delement"></a>CHtmlEditCtrlBase::Is1DElement  
 Détermine si un élément est positionné de façon statique.  
  
```  
HRESULT Is1DElement(bool& bValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bValue`  
 True si l’élément est positionné de façon statique.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_1D_ELEMENT l’ID de commande](https://msdn.microsoft.com/library/aa769885.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameis2delementa--chtmleditctrlbaseis2delement"></a><a name="is2delement"></a>CHtmlEditCtrlBase::Is2DElement  
 Détermine si un élément est positionné.  
  
```  
HRESULT Is2DElement(bool& bValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bValue`  
 True si l’élément est positionné.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_2D_ELEMENT l’ID de commande](https://msdn.microsoft.com/library/aa769886.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameitalica--chtmleditctrlbaseitalic"></a><a name="italic"></a>CHtmlEditCtrlBase::Italic  
 Active ou désactive la sélection actuelle en italique.  
  
```  
HRESULT Italic() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_ITALIC l’ID de commande](https://msdn.microsoft.com/library/aa769988.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namejustifycentera--chtmleditctrlbasejustifycenter"></a><a name="justifycenter"></a>CHtmlEditCtrlBase::JustifyCenter  
 Les centres du formater le bloc dans lequel se trouve la sélection actuelle.  
  
```  
HRESULT JustifyCenter() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_JUSTIFYCENTER l’ID de commande](https://msdn.microsoft.com/library/aa769989.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namejustifylefta--chtmleditctrlbasejustifyleft"></a><a name="justifyleft"></a>CHtmlEditCtrlBase::JustifyLeft  
 Aligne à gauche le formater le bloc dans lequel se trouve la sélection actuelle.  
  
```  
HRESULT JustifyLeft() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_JUSTIFYLEFT l’ID de commande](https://msdn.microsoft.com/library/aa770011.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namejustifyrighta--chtmleditctrlbasejustifyright"></a><a name="justifyright"></a>CHtmlEditCtrlBase::JustifyRight  
 Aligne à droite le formater le bloc dans lequel se trouve la sélection actuelle.  
  
```  
HRESULT JustifyRight() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_JUSTIFYRIGHT l’ID de commande](https://msdn.microsoft.com/library/aa770013.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namelistboxa--chtmleditctrlbaselistbox"></a><a name="listbox"></a>CHtmlEditCtrlBase::ListBox  
 Remplace le contrôle de sélection de zone de liste sur la sélection actuelle.  
  
```  
HRESULT ListBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID pour le contrôle de zone de liste.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_LISTBOX l’ID de commande](https://msdn.microsoft.com/library/aa769985.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namemarqueea--chtmleditctrlbasemarquee"></a><a name="marquee"></a>CHtmlEditCtrlBase::Marquee  
 Remplace un texte défilant vide sur la sélection actuelle.  
  
```  
HRESULT Marquee(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID pour le texte défilant.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_MARQUEE l’ID de commande](https://msdn.microsoft.com/library/aa769981.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namenewdocumenta--chtmleditctrlbasenewdocument"></a><a name="newdocument"></a>CHtmlEditCtrlBase::NewDocument  
 Crée un nouveau document.  
  
```  
HRESULT NewDocument() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-nameorderlista--chtmleditctrlbaseorderlist"></a><a name="orderlist"></a>CHtmlEditCtrlBase::OrderList  
 Active ou désactive la sélection actuelle entre une liste ordonnée et un bloc de format normal.  
  
```  
HRESULT OrderList(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID de la liste ordonnée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_ORDERLIST l’ID de commande](https://msdn.microsoft.com/library/aa769982.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameoutdenta--chtmleditctrlbaseoutdent"></a><a name="outdent"></a>CHtmlEditCtrlBase::Outdent  
 Diminue d’un incrément le retrait du bloc de format dans lequel se trouve la sélection actuelle.  
  
```  
HRESULT Outdent() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_OUTDENT l’ID de commande](https://msdn.microsoft.com/library/aa770015.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameparagrapha--chtmleditctrlbaseparagraph"></a><a name="paragraph"></a>CHtmlEditCtrlBase::Paragraph  
 Remplace un saut de ligne sur la sélection actuelle.  
  
```  
HRESULT Paragraph(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 ID du paragraphe.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_PARAGRAPH l’ID de commande](https://msdn.microsoft.com/library/aa769983.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namepastea--chtmleditctrlbasepaste"></a><a name="paste"></a>CHtmlEditCtrlBase::Paste  
 Remplace le contenu du Presse-papiers sur la sélection actuelle.  
  
```  
HRESULT Paste() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_PASTE l’ID de commande](https://msdn.microsoft.com/library/aa770017.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameprintdocumenta--chtmleditctrlbaseprintdocument"></a><a name="printdocument"></a>CHtmlEditCtrlBase::PrintDocument  
 Imprime le document actif.  
  
```  
HRESULT PrintDocument() const;  
HRESULT PrintDocument(LPCTSTR szPrintTemplate) const;  
HRESULT PrintDocument(bool bShowPrintDialog) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szPrintTemplate`  
 Chemin d’accès à un modèle d’impression ; Si aucun n’est spécifié, le modèle d’impression par défaut est utilisé.  
  
 *bShowPrintDialog*  
 Si la valeur est true, affiche la boîte de dialogue d’impression.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_PRINT l’ID de commande](https://msdn.microsoft.com/library/aa769937.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameprintpreviewa--chtmleditctrlbaseprintpreview"></a><a name="printpreview"></a>CHtmlEditCtrlBase::PrintPreview  
 Ouvre la fenêtre Aperçu avant impression du document actif à l’aide du modèle de l’aperçu avant impression par défaut ou un modèle personnalisé.  
  
```  
HRESULT PrintPreview() const;  
HRESULT PrintPreview(LPCTSTR szPrintTemplate) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szPrintTemplate`  
 Chemin d’accès à un modèle d’impression.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_PRINTPREVIEW l’ID de commande](https://msdn.microsoft.com/library/aa769938.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namequerystatusa--chtmleditctrlbasequerystatus"></a><a name="querystatus"></a>CHtmlEditCtrlBase::QueryStatus  
 Appelez cette méthode pour demander l’état des commandes.  
  
```  
long QueryStatus(long cmdID) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `cmdID`  
 ID de la commande. Identificateurs de commande sont effectuées à partir de la `CGID_MSHTML`de groupe de commandes. Ces commandes sont définies dans Mshtmcid.h. Vous trouverez également la liste en ligne en [MSHTML les identificateurs de commande](http://go.microsoft.com/fwlink/linkid=149220).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne un [OLECMDF](http://msdn.microsoft.com/library/windows/desktop/ms695237) indiquant l’état de `cmdID`, ou 0 en cas d’échec.  
  
##  <a name="a-nameradiobuttona--chtmleditctrlbaseradiobutton"></a><a name="radiobutton"></a>CHtmlEditCtrlBase::RadioButton  
 Remplace un contrôle de case d’option sur la sélection actuelle.  
  
```  
HRESULT RadioButton(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 ID de la case d’option.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_RADIOBUTTON l’ID de commande](https://msdn.microsoft.com/library/aa769977.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namerefreshdocumenta--chtmleditctrlbaserefreshdocument"></a><a name="refreshdocument"></a>CHtmlEditCtrlBase::RefreshDocument  
 Actualise le document actif.  
  
```  
HRESULT RefreshDocument() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_REFRESH l’ID de commande](https://msdn.microsoft.com/library/aa770020.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameremoveformata--chtmleditctrlbaseremoveformat"></a><a name="removeformat"></a>CHtmlEditCtrlBase::RemoveFormat  
 Supprime les balises de mise en forme de la sélection actuelle.  
  
```  
HRESULT RemoveFormat() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_REMOVEFORMAT l’ID de commande](https://msdn.microsoft.com/library/aa770021.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesaveasa--chtmleditctrlbasesaveas"></a><a name="saveas"></a>CHtmlEditCtrlBase::SaveAs  
 Enregistre la page Web actuelle dans un fichier.  
  
```  
HRESULT SaveAs(LPCTSTR szPath = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szPath`  
 Le chemin d’accès et le nom d’enregistrement de la page Web.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_SAVEAS ID de commande](https://msdn.microsoft.com/library/aa770024.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameselectalla--chtmleditctrlbaseselectall"></a><a name="selectall"></a>CHtmlEditCtrlBase::SelectAll  
 Sélectionne tout le document.  
  
```  
HRESULT SelectAll() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_SELECTALL l’ID de commande](https://msdn.microsoft.com/library/aa770025.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameset2dpositiona--chtmleditctrlbaseset2dposition"></a><a name="set2dposition"></a>CHtmlEditCtrlBase::Set2DPosition  
 Permet de déplacer en faisant glisser des éléments à positionnement absolu.  
  
```  
HRESULT Set2DPosition(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, les éléments à positionnement absolu peuvent être déplacés en faisant glisser.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_2D_POSITION l’ID de commande](https://msdn.microsoft.com/library/aa769887.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetabsolutepositiona--chtmleditctrlbasesetabsoluteposition"></a><a name="setabsoluteposition"></a>CHtmlEditCtrlBase::SetAbsolutePosition  
 Définit la propriété de position d’un élément « absolute » ou « statique ».  
  
```  
HRESULT SetAbsolutePosition(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, propriété de position de l’élément est « absolue » ; Si la valeur est false, il est « statique ».  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_ABSOLUTE_POSITION l’ID de commande](https://msdn.microsoft.com/library/aa769889.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetatomicselectiona--chtmleditctrlbasesetatomicselection"></a><a name="setatomicselection"></a>CHtmlEditCtrlBase::SetAtomicSelection  
 Définir le mode de sélection atomique.  
  
```  
HRESULT SetAtomicSelection(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, tout élément ayant un attribut ATOMICSELECTION défini sur TRUE est accessibles uniquement en tant qu’unité.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_ATOMICSELECTION l’ID de commande](https://msdn.microsoft.com/library/aa769892.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetautourldetectmodea--chtmleditctrlbasesetautourldetectmode"></a><a name="setautourldetectmode"></a>CHtmlEditCtrlBase::SetAutoURLDetectMode  
 Active la détection automatique des URL et désactive.  
  
```  
HRESULT SetAutoURLDetectMode(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, la détection automatique des URL est activée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_AUTOURLDETECT_MODE l’ID de commande](https://msdn.microsoft.com/library/aa769893.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetbackcolora--chtmleditctrlbasesetbackcolor"></a><a name="setbackcolor"></a>CHtmlEditCtrlBase::SetBackColor  
 Définit la couleur d’arrière-plan de la sélection actuelle.  
  
```  
HRESULT SetBackColor(int nColor) const;  
HRESULT SetBackColor(LPCTSTR szColor) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nColor`  
 La couleur. Consultez la page `pvaIn` dans [IDM_BACKCOLOR l’ID de commande](https://msdn.microsoft.com/library/aa769858.aspx).  
  
 `szColor`  
 La couleur. Consultez la page `pvaIn` dans [IDM_BACKCOLOR l’ID de commande](https://msdn.microsoft.com/library/aa769858.aspx).  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_BACKCOLOR_ l’ID de commande](https://msdn.microsoft.com/library/aa769858.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetblockformata--chtmleditctrlbasesetblockformat"></a><a name="setblockformat"></a>CHtmlEditCtrlBase::SetBlockFormat  
 Définit la balise de format bloc actuel.  
  
```  
HRESULT SetBlockFormat(LPCTSTR szFormat) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szFormat`  
 La balise de format.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_BLOCKFMT_command ID](https://msdn.microsoft.com/library/aa769883.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetbookmarka--chtmleditctrlbasesetbookmark"></a><a name="setbookmark"></a>CHtmlEditCtrlBase::SetBookMark  
 Crée une ancre de signet pour le point d’insertion ou de la sélection actuelle.  
  
```  
HRESULT SetBookMark(LPCTSTR szAnchorName) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *szAnchorName*  
 Le nom de l’ancre.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_BOOKMARK l’ID de commande](https://msdn.microsoft.com/library/aa769873.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetcsseditinglevela--chtmleditctrlbasesetcsseditinglevel"></a><a name="setcsseditinglevel"></a>CHtmlEditCtrlBase::SetCSSEditingLevel  
 Sélectionne le niveau CSS (CSS1 ou CSS2) l’éditeur prendra en charge, le cas échéant.  
  
```  
HRESULT SetCSSEditingLevel(short nLevel) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `nLevel`  
 Le niveau de CSS. Passer 0 si vous ne souhaitez pas de prise en charge CSS.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_CSSEDITING_LEVEL l’ID de commande](https://msdn.microsoft.com/library/aa769903.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetdefaultcomposesettingsa--chtmleditctrlbasesetdefaultcomposesettings"></a><a name="setdefaultcomposesettings"></a>CHtmlEditCtrlBase::SetDefaultComposeSettings  
 Appel de cette méthode pour définir la valeur par défaut des paramètres de composition.  
  
```  
HRESULT SetDefaultComposeSettings(
    LPCSTR szFontName = NULL,  
    unsigned short nFontSize = 3,  
    COLORREF crFontColor = 0xFF000000,  
    COLORREF crFontBgColor = 0xFF000000,  
    bool bBold = false,  
    bool bItalic = false,  
    bool bUnderline = false) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 *szFontName*  
 Le nom de la police.  
  
 *nFontSize*  
 La taille de police.  
  
 *crFontColor*  
 La couleur de police.  
  
 *crFontBgColor*  
 La couleur d’arrière-plan de police.  
  
 *bgras*  
 Passez true pour le texte en gras.  
  
 `bItalic`  
 Transmettez la valeur true pour le texte en italique.  
  
 `bUnderline`  
 Passez true pour le texte souligné.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM_COMPOSESETTINGS ID de commande](https://msdn.microsoft.com/library/aa769901.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetdesignmodea--chtmleditctrlbasesetdesignmode"></a><a name="setdesignmode"></a>CHtmlEditCtrlBase::SetDesignMode  
 Définir le mode Création.  
  
```  
BOOL SetDesignMode(BOOL bMode) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bMode`  
 Si la valeur est true, Active le mode conception.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne la valeur TRUE en cas de réussite, FALSE en cas d’échec.  
  
##  <a name="a-namesetdisableeditfocusuia--chtmleditctrlbasesetdisableeditfocusui"></a><a name="setdisableeditfocusui"></a>CHtmlEditCtrlBase::SetDisableEditFocusUI  
 Désactive la bordure hachurée et gère autour d’un élément qui a le focus de la modifier.  
  
```  
HRESULT SetDisableEditFocusUI(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, désactive la bordure hachurée et handles autour d’un élément sélectionnable site lorsque l’élément a « modifier le focus » en mode Création ; Autrement dit, lorsque le texte ou le contenu de l’élément peut être modifiée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM_DISABLE_EDITFOCUS_UI l’ID de commande](https://msdn.microsoft.com/library/aa769905.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetdocumenthtmla--chtmleditctrlbasesetdocumenthtml"></a><a name="setdocumenthtml"></a>CHtmlEditCtrlBase::SetDocumentHTML  
 Définit le code HTML du document actif.  
  
```  
HRESULT SetDocumentHTML(LPCTSTR szHTML) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szHTML`  
 Le code HTML.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
##  <a name="a-namesetfontfacea--chtmleditctrlbasesetfontface"></a><a name="setfontface"></a>CHtmlEditCtrlBase::SetFontFace  
 Définit la police pour la sélection actuelle.  
  
```  
HRESULT SetFontFace(LPCTSTR szFace) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szFace`  
 Le nom de la police.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM FONTNAME](https://msdn.microsoft.com/library/aa769880.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetfontsizea--chtmleditctrlbasesetfontsize"></a><a name="setfontsize"></a>CHtmlEditCtrlBase::SetFontSize  
 Définit la taille de police pour la sélection actuelle.  
  
```  
HRESULT SetFontSize(unsigned short size) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `size`  
 La taille de police HTML (1-7). La valeur 0 définit la taille de police sur 1.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM FONTSIZE](https://msdn.microsoft.com/library/aa769881.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetforecolora--chtmleditctrlbasesetforecolor"></a><a name="setforecolor"></a>CHtmlEditCtrlBase::SetForeColor  
 Définit la couleur de premier plan (texte) de la sélection actuelle.  
  
```  
HRESULT SetForeColor(LPCTSTR szColor) const;  
HRESULT SetForeColor(int nColor) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szColor`  
 La couleur.  
  
 `nColor`  
 La couleur.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM FORECOLOR](https://msdn.microsoft.com/library/aa769882.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetie5pastemodea--chtmleditctrlbasesetie5pastemode"></a><a name="setie5pastemode"></a>CHtmlEditCtrlBase::SetIE5PasteMode  
 Définit l’opération de collage pour être compatible avec Microsoft Internet Explorer 5.  
  
```  
HRESULT SetIE5PasteMode(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, toutes les opérations de collage sont compatibles avec Internet Explorer 5 ; Si la valeur est false, les opérations de collage sont compatibles avec Internet Explorer 5.5.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM IE50_PASTE_MODE](https://msdn.microsoft.com/library/aa769923.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetliveresizea--chtmleditctrlbasesetliveresize"></a><a name="setliveresize"></a>CHtmlEditCtrlBase::SetLiveResize  
 Provoque le contrôle WebBrowser mettre à jour d’apparence d’un élément en permanence pendant une opération de redimensionnement ou déplacement, au lieu de mettre à jour uniquement à la fin du déplacement ou redimensionner.  
  
```  
HRESULT SetLiveResize(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, entraîne le contrôle WebBrowser à jour l’apparence d’un élément en permanence pendant une opération de redimensionnement ou déplacement ; Si la valeur est false, elle met à jour uniquement à la fin de la déplacer ou redimensionner.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM LIVERESIZE](https://msdn.microsoft.com/library/aa769928.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetmultiselecta--chtmleditctrlbasesetmultiselect"></a><a name="setmultiselect"></a>CHtmlEditCtrlBase::SetMultiSelect  
 Permet la sélection multiple.  
  
```  
HRESULT SetMultiSelect(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, permet la sélection de plusieurs éléments sélectionnables de site à la fois lorsque l’utilisateur maintient enfoncée la touche MAJ ou CTRL.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM MULTIPLESELECTION](https://msdn.microsoft.com/library/aa769929.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetoverridecursora--chtmleditctrlbasesetoverridecursor"></a><a name="setoverridecursor"></a>CHtmlEditCtrlBase::SetOverrideCursor  
 Commandes WebBrowser jamais à modifier le pointeur de la souris.  
  
```  
HRESULT SetOverrideCursor(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, le contrôle WebBrowser ne changera pas le pointeur de la souris.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM OVERRIDE_CURSOR](https://msdn.microsoft.com/library/aa769932.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetoverwritemodea--chtmleditctrlbasesetoverwritemode"></a><a name="setoverwritemode"></a>CHtmlEditCtrlBase::SetOverwriteMode  
 Active/désactive le mode de saisie de texte entre les insérer, remplacer.  
  
```  
HRESULT SetOverwriteMode(bool bMode) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bMode`  
 Si la valeur est true, le mode de saisie est remplacer ; Si la valeur est false, le mode de saisie est insert.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM remplacer l’ID de commande](https://msdn.microsoft.com/library/aa770016.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetrespectvisindesigna--chtmleditctrlbasesetrespectvisindesign"></a><a name="setrespectvisindesign"></a>CHtmlEditCtrlBase::SetRespectVisInDesign  
 Masque les éléments invisibles dans ce mode.  
  
```  
HRESULT SetRespectVisInDesign(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, tous les éléments qui ont une visibilité définir « Hidden » ou afficher la propriété est définie sur « none » seront affichera pas en mode design et en mode Parcourir ; Si la valeur est false, ces éléments seront affichera uniquement en mode de navigation.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM RESPECTVISIBILITY_INDESIGN](https://msdn.microsoft.com/library/aa770023.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowalignedsitetagsa--chtmleditctrlbasesetshowalignedsitetags"></a><a name="setshowalignedsitetags"></a>CHtmlEditCtrlBase::SetShowAlignedSiteTags  
 Affiche un glyphe pour tous les éléments qui ont un **styleFloat** propriété.  
  
```  
HRESULT SetShowAlignedSiteTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche un glyphe pour tous les éléments qui ont un **styleFloat** propriété.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM SHOWALIGNEDSITETAGS](https://msdn.microsoft.com/library/aa769947.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowalltagsa--chtmleditctrlbasesetshowalltags"></a><a name="setshowalltags"></a>CHtmlEditCtrlBase::SetShowAllTags  
 Afficher des glyphes pour afficher l’emplacement de toutes les balises dans un document.  
  
```  
HRESULT SetShowAllTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche des glyphes pour afficher l’emplacement de toutes les balises dans un document.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM SHOWALLTAGS](https://msdn.microsoft.com/library/aa769948.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowareatagsa--chtmleditctrlbasesetshowareatags"></a><a name="setshowareatags"></a>CHtmlEditCtrlBase::SetShowAreaTags  
 Affiche un glyphe pour toutes les balises de la zone.  
  
```  
HRESULT SetShowAreaTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche un glyphe pour toutes les balises de la zone.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM SHOWAREATAGS](https://msdn.microsoft.com/library/aa769949.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowbrtagsa--chtmleditctrlbasesetshowbrtags"></a><a name="setshowbrtags"></a>CHtmlEditCtrlBase::SetShowBRTags  
 Affiche un glyphe pour toutes les balises br.  
  
```  
HRESULT SetShowBRTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche un glyphe pour toutes les balises br.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM SHOWWBRTAGS](https://msdn.microsoft.com/library/aa769956.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowcommenttagsa--chtmleditctrlbasesetshowcommenttags"></a><a name="setshowcommenttags"></a>CHtmlEditCtrlBase::SetShowCommentTags  
 Affiche un glyphe pour toutes les balises de commentaire.  
  
```  
HRESULT SetShowCommentTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche un glyphe pour toutes les balises de commentaire.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM SHOWCOMMENTTAGS](https://msdn.microsoft.com/library/aa769950.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowmisctagsa--chtmleditctrlbasesetshowmisctags"></a><a name="setshowmisctags"></a>CHtmlEditCtrlBase::SetShowMiscTags  
 Affiche toutes les balises affichées dans Microsoft Internet Explorer 4.0.  
  
```  
HRESULT SetShowMiscTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche toutes les balises affichées dans Microsoft Internet Explorer 4.0.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM SHOWMISCTAGS](https://msdn.microsoft.com/library/aa769952.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowscripttagsa--chtmleditctrlbasesetshowscripttags"></a><a name="setshowscripttags"></a>CHtmlEditCtrlBase::SetShowScriptTags  
 Affiche un glyphe pour toutes les balises de script.  
  
```  
HRESULT SetShowScriptTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche un glyphe pour toutes les balises de script.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM SHOWSCRIPTTAGS](https://msdn.microsoft.com/library/aa769953.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowstyletagsa--chtmleditctrlbasesetshowstyletags"></a><a name="setshowstyletags"></a>CHtmlEditCtrlBase::SetShowStyleTags  
 Affiche un glyphe pour toutes les balises de style.  
  
```  
HRESULT SetShowStyleTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche un glyphe pour toutes les balises de style.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM SHOWSTYLETAGS](https://msdn.microsoft.com/library/aa769954.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-namesetshowunknowntagsa--chtmleditctrlbasesetshowunknowntags"></a><a name="setshowunknowntags"></a>CHtmlEditCtrlBase::SetShowUnknownTags  
 Affiche un glyphe pour toutes les balises inconnus.  
  
```  
HRESULT SetShowUnknownTags(bool bNewValue) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `bNewValue`  
 Si la valeur est true, affiche un glyphe pour toutes les balises inconnus.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM SHOWUNKNOWNTAGS](https://msdn.microsoft.com/library/aa769955.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nametextareaa--chtmleditctrlbasetextarea"></a><a name="textarea"></a>CHtmlEditCtrlBase::TextArea  
 Remplace un contrôle d’entrée de texte multiligne sur la sélection actuelle.  
  
```  
HRESULT TextArea(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle d’entrée de texte multiligne.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM TEXTAREA](https://msdn.microsoft.com/library/aa769986.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nametextboxa--chtmleditctrlbasetextbox"></a><a name="textbox"></a>CHtmlEditCtrlBase::TextBox  
 Remplace un contrôle de texte sur la sélection actuelle.  
  
```  
HRESULT TextBox(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 L’ID du contrôle de texte.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [ID de commande IDM TEXTBOX](https://msdn.microsoft.com/library/aa769980.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameunbookmarka--chtmleditctrlbaseunbookmark"></a><a name="unbookmark"></a>CHtmlEditCtrlBase::UnBookmark  
 Supprime les signets dans la sélection actuelle.  
  
```  
HRESULT UnBookmark() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [UNBOOKMARK IDM l’ID de commande](https://msdn.microsoft.com/library/aa770034.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameunderlinea--chtmleditctrlbaseunderline"></a><a name="underline"></a>CHtmlEditCtrlBase::Underline  
 Active ou désactive la sélection actuelle entre souligné et non souligné.  
  
```  
HRESULT Underline() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [IDM SOULIGNER les ID de commande](https://msdn.microsoft.com/library/aa770035.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameunlinka--chtmleditctrlbaseunlink"></a><a name="unlink"></a>CHtmlEditCtrlBase::Unlink  
 Supprime un lien hypertexte de la sélection actuelle.  
  
```  
HRESULT Unlink() const;  
```  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Notes  
 Cette méthode envoie le [IDM dissocier l’ID de commande](https://msdn.microsoft.com/library/aa770037.aspx) pour le contrôle WebBrowser.  
  
##  <a name="a-nameunorderlista--chtmleditctrlbaseunorderlist"></a><a name="unorderlist"></a>CHtmlEditCtrlBase::UnorderList  
 Active ou désactive la sélection actuelle entre une liste ordonnée et un bloc de format normal.  
  
```  
HRESULT UnorderList(LPCTSTR szId = NULL) const;  
```  
  
### <a name="parameters"></a>Paramètres  
 `szId`  
 ID de la liste non triée.  
  
### <a name="return-value"></a>Valeur de retour  
 Retourne S_OK en cas de réussite, ou une erreur HRESULT d’échec.  
  
### <a name="remarks"></a>Remarques  
 Cette méthode envoie le [ID de commande IDM UNORDERLIST](https://msdn.microsoft.com/library/aa769987.aspx) pour le contrôle WebBrowser.  
  
## <a name="see-also"></a>Voir aussi  
 [Graphique de la hiérarchie](../../mfc/hierarchy-chart.md)   
 [HTMLEdit, exemple](../../visual-cpp-samples.md)


