---
title: "CComboBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CComboBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CComboBox (classe)"
  - "zones de liste déroulante, CComboBox objects"
ms.assetid: 4e73b5df-0d2e-4658-9706-38133fb10513
caps.latest.revision: 25
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 26
---
# CComboBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'une zone de liste déroulante windows.  
  
## Syntaxe  
  
```  
class CComboBox : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CComboBox::CComboBox](../Topic/CComboBox::CComboBox.md)|Construit un objet `CComboBox`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CComboBox::AddString](../Topic/CComboBox::AddString.md)|Ajoute une chaîne à la fin de la liste dans la zone de liste d'une zone de liste déroulante, ou à la position triée pour les zones de liste avec le style de **CBS\_SORT** .|  
|[CComboBox::Clear](../Topic/CComboBox::Clear.md)|Supprime \(espaces inscription\) la sélection actuelle, le cas échéant, dans le contrôle d'édition.|  
|[CComboBox::CompareItem](../Topic/CComboBox::CompareItem.md)|Appelé par l'infrastructure pour déterminer la position relative d'un élément de liste dans une zone de liste déroulante owner\-drawn triée.|  
|[CComboBox::Copy](../Topic/CComboBox::Copy.md)|Copie la sélection actuelle, le cas échéant, dans le presse\-papiers dans le format de **CF\_TEXT** .|  
|[CComboBox::Create](../Topic/CComboBox::Create.md)|Crée la zone de liste déroulante et la attaché à l'objet d' `CComboBox` .|  
|[CComboBox::Cut](../Topic/CComboBox::Cut.md)|Supprime coupes \(\) la sélection actuelle, le cas échéant, dans le contrôle d'édition et les copie le texte supprimé dans le presse\-papiers dans le format de **CF\_TEXT** .|  
|[CComboBox::DeleteItem](../Topic/CComboBox::DeleteItem.md)|Appelé par l'infrastructure lorsqu'un élément de liste est supprimé d'une zone de liste déroulante owner\-drawn.|  
|[CComboBox::DeleteString](../Topic/CComboBox::DeleteString.md)|Supprime une chaîne dans la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::Dir](../Topic/CComboBox::Dir.md)|Ajoute une liste de noms de fichier à la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::DrawItem](../Topic/CComboBox::DrawItem.md)|Appelé par l'infrastructure lorsqu'un aspect visuel d'une zone de liste déroulante owner\-drawn change.|  
|[CComboBox::FindString](../Topic/CComboBox::FindString.md)|Recherche la première chaîne qui contient le préfixe spécifié dans la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::FindStringExact](../Topic/CComboBox::FindStringExact.md)|Recherche la première chaîne de zone de liste \(dans une zone de liste déroulante\) qui correspond à la chaîne spécifiée.|  
|[CComboBox::GetComboBoxInfo](../Topic/CComboBox::GetComboBoxInfo.md)|Récupère des informations sur l'objet d' `CComboBox` .|  
|[CComboBox::GetCount](../Topic/CComboBox::GetCount.md)|Récupère le nombre d'éléments dans la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::GetCueBanner](../Topic/CComboBox::GetCueBanner.md)|Obtient le texte de caractère indicateur restitué pour un contrôle zone de liste déroulante.|  
|[CComboBox::GetCurSel](../Topic/CComboBox::GetCurSel.md)|Récupère l'index actuel de l'élément sélectionné, le cas échéant, dans la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::GetDroppedControlRect](../Topic/CComboBox::GetDroppedControlRect.md)|Récupère les coordonnées d'écran \(déplacé vers le bas\) de la zone de liste visible d'une zone de liste déroulante fixe.|  
|[CComboBox::GetDroppedState](../Topic/CComboBox::GetDroppedState.md)|Détermine si la zone de liste d'une zone de liste déroulante fixe est visible \(déplacé vers le bas\).|  
|[CComboBox::GetDroppedWidth](../Topic/CComboBox::GetDroppedWidth.md)|Extrait la largeur minimum autorisée pour la zone de liste déroulante d'une zone de liste déroulante.|  
|[CComboBox::GetEditSel](../Topic/CComboBox::GetEditSel.md)|Obtient les positions des caractères de début et de fin de la sélection actuelle dans le contrôle d'édition d'une zone de liste déroulante.|  
|[CComboBox::GetExtendedUI](../Topic/CComboBox::GetExtendedUI.md)|Détermine si une zone de liste déroulante a l'interface utilisateur par défaut ou l'interface utilisateur étendue.|  
|[CComboBox::GetHorizontalExtent](../Topic/CComboBox::GetHorizontalExtent.md)|Retourne la largeur en pixels que la partie zone de liste de la zone de liste déroulante peut être horizontale vous faites.|  
|[CComboBox::GetItemData](../Topic/CComboBox::GetItemData.md)|Extrait la valeur 32 bits fournie par l'application associée à l'élément spécifié de zone de liste déroulante.|  
|[CComboBox::GetItemDataPtr](../Topic/CComboBox::GetItemDataPtr.md)|Récupère le pointeur 32 bits fourni par l'application qui est associé à l'élément spécifié de zone de liste déroulante.|  
|[CComboBox::GetItemHeight](../Topic/CComboBox::GetItemHeight.md)|Extrait la hauteur d'éléments de liste dans une zone de liste déroulante.|  
|[CComboBox::GetLBText](../Topic/CComboBox::GetLBText.md)|Obtient une chaîne dans la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::GetLBTextLen](../Topic/CComboBox::GetLBTextLen.md)|Obtient la longueur d'une chaîne dans la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::GetLocale](../Topic/CComboBox::GetLocale.md)|Récupère l'identificateur de paramètres régionaux pour une zone de liste déroulante.|  
|[CComboBox::GetMinVisible](../Topic/CComboBox::GetMinVisible.md)|Obtient le nombre minimal d'éléments visibles dans la liste déroulante de la zone de liste déroulante actuelle.|  
|[CComboBox::GetTopIndex](../Topic/CComboBox::GetTopIndex.md)|Retourne l'index du premier élément visible dans la partie zone de liste de la zone de liste déroulante.|  
|[CComboBox::InitStorage](../Topic/CComboBox::InitStorage.md)|Préaffecte les blocs de mémoire pour des éléments et des chaînes dans la partie zone de liste de la zone de liste déroulante.|  
|[CComboBox::InsertString](../Topic/CComboBox::InsertString.md)|Insère une chaîne dans la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::LimitText](../Topic/CComboBox::LimitText.md)|Limite la longueur du texte que l'utilisateur peut entrer dans le contrôle d'édition d'une zone de liste déroulante.|  
|[CComboBox::MeasureItem](../Topic/CComboBox::MeasureItem.md)|Appelé par l'infrastructure pour déterminer les dimensions zone de liste déroulante lorsqu'une zone de liste déroulante owner\-drawn est créée.|  
|[CComboBox::Paste](../Topic/CComboBox::Paste.md)|Insère les données du presse\-papiers dans le contrôle d'édition à la position du curseur actuelle.  Les données sont insérées que si le presse\-papiers contient des données au format de **CF\_TEXT** .|  
|[CComboBox::ResetContent](../Topic/CComboBox::ResetContent.md)|Supprime tous les éléments de la zone de liste et du contrôle d'édition d'une zone de liste déroulante.|  
|[CComboBox::SelectString](../Topic/CComboBox::SelectString.md)|Le recherche une chaîne dans la zone de liste d'une zone de liste déroulante et, si la chaîne est trouvée, sélectionne la chaîne dans la zone de liste et copie la chaîne au contrôle d'édition.|  
|[CComboBox::SetCueBanner](../Topic/CComboBox::SetCueBanner.md)|Définit le texte de caractère indicateur restitué pour un contrôle zone de liste déroulante.|  
|[CComboBox::SetCurSel](../Topic/CComboBox::SetCurSel.md)|Sélectionne une chaîne dans la zone de liste d'une zone de liste déroulante.|  
|[CComboBox::SetDroppedWidth](../Topic/CComboBox::SetDroppedWidth.md)|Définit la largeur minimum autorisée pour la zone de liste déroulante d'une zone de liste déroulante.|  
|[CComboBox::SetEditSel](../Topic/CComboBox::SetEditSel.md)|Sélectionne des caractères du contrôle d'édition d'une zone de liste déroulante.|  
|[CComboBox::SetExtendedUI](../Topic/CComboBox::SetExtendedUI.md)|Sélectionne l'interface utilisateur par défaut ou l'interface utilisateur étendue pour une zone de liste déroulante qui a le style de **CBS\_DROPDOWN** ou de **CBS\_DROPDOWNLIST** .|  
|[CComboBox::SetHorizontalExtent](../Topic/CComboBox::SetHorizontalExtent.md)|Définit la largeur en pixels que la partie zone de liste de la zone de liste déroulante peut être horizontale vous faites.|  
|[CComboBox::SetItemData](../Topic/CComboBox::SetItemData.md)|Définit la valeur 32 bits associé à l'élément spécifié dans une zone de liste déroulante.|  
|[CComboBox::SetItemDataPtr](../Topic/CComboBox::SetItemDataPtr.md)|Place le pointeur 32 bits associé à l'élément spécifié dans une zone de liste déroulante.|  
|[CComboBox::SetItemHeight](../Topic/CComboBox::SetItemHeight.md)|Définit la hauteur d'éléments de liste dans une zone de liste déroulante ou la hauteur de la partie de contrôle edit \(ou charge\- texte\) d'une zone de liste déroulante.|  
|[CComboBox::SetLocale](../Topic/CComboBox::SetLocale.md)|Définit l'identificateur de paramètres régionaux pour une zone de liste déroulante.|  
|[CComboBox::SetMinVisibleItems](../Topic/CComboBox::SetMinVisibleItems.md)|Définit le nombre minimal d'éléments visibles dans la liste déroulante de la zone de liste déroulante actuelle.|  
|[CComboBox::SetTopIndex](../Topic/CComboBox::SetTopIndex.md)|Indique la partie zone de liste de la zone de liste déroulante pour afficher l'élément de l'index spécifié en haut.|  
|[CComboBox::ShowDropDown](../Topic/CComboBox::ShowDropDown.md)|Affiche ou masque la zone de liste d'une zone de liste déroulante qui a le style de **CBS\_DROPDOWN** ou de **CBS\_DROPDOWNLIST** .|  
  
## Notes  
 Une zone de liste déroulante se compose d'une zone de liste combinée avec un contrôle statique ou le contrôle d'édition.  La partie zone de liste du contrôle peut être affichée à tout moment ou peut uniquement déroulante lorsque l'utilisateur sélectionne la flèche de déroulement en regard de le contrôle.  
  
 Actuellement l'élément sélectionné \(le cas échéant\) dans la zone de liste s'affiche dans la ou statique le contrôle d'édition.  En outre, si la zone de liste déroulante a le style de liste déroulante, l'utilisateur peut entrer le caractère initial d'un des éléments dans la liste, et la zone de liste, si visible, met en surbrillance l'élément avec ce caractère initial.  
  
 Le tableau suivant compare trois la zone de liste déroulante [styles](../../mfc/reference/combo-box-styles.md).  
  
|Style|Lorsque la zone de liste est visible ?|Statique ou contrôle d'édition ?|  
|-----------|--------------------------------------------|--------------------------------------|  
|Simple|Toujours|Modifier|  
|Zone déroulante|Une fois supprimés vers le bas|Modifier|  
|Liste déroulante|Une fois supprimés vers le bas|Static|  
  
 Vous pouvez créer un objet d' `CComboBox` d'un modèle de boîte de dialogue ou directement dans votre code.  Dans les deux cas, abord appeler le constructeur `CComboBox` pour construire l'objet d' `CComboBox` ; appelez la fonction membre de [Create](../Topic/CComboBox::Create.md) pour créer le contrôle et le lier à l'objet d' `CComboBox` .  
  
 Si vous souhaitez gérer des messages de notification de fenêtres envoyés par une zone de liste déroulante à son parent \(généralement une classe dérivée d' `CDialog`\), ajoutez une entrée de la table des messages et une fonction membre gestionnaire de messages à la classe parente pour chaque message.  
  
 Chaque entrée de la table des messages prend la forme suivante :  
  
 Notification**\(**`id`**,**`memberFxn`**\)**d'**ON\_**  
  
 où `id` spécifie l'ID de fenêtre enfant du contrôle zone de liste déroulante envoyant la notification et `memberFxn` est le nom de la fonction membre parente que vous avez écrit pour traiter la notification.  
  
 Le prototype de fonction du parent est la suivante :  
  
 **afx\_msg** `void` `memberFxn` **\(**\);  
  
 L'ordre dans lequel certaines notifications sont envoyées ne peut pas être prévu.  En particulier, une notification de **CBN\_SELCHANGE** peut se produire soit avant ou après une notification de **CBN\_CLOSEUP** .  
  
 Les entrées de la table des messages potentielles sont les suivantes :  
  
-   **ON\_CBN\_CLOSEUP** \(Windows 3.1 et ultérieure.\) La zone de liste d'une zone de liste déroulante est fermée.  Ce message de notification n'est pas envoyé pour une zone de liste déroulante qui a le style de [CBS\_SIMPLE](../../mfc/reference/combo-box-styles.md) .  
  
-   **ON\_CBN\_DBLCLK** l'utilisateur double\-clique sur une chaîne dans la zone de liste d'une zone de liste déroulante.  Ce message de notification est envoyé uniquement pour une zone de liste déroulante avec le style de **CBS\_SIMPLE** .  Pour une zone de liste déroulante avec le style de [CBS\_DROPDOWN](../../mfc/reference/combo-box-styles.md) ou de [CBS\_DROPDOWNLIST](../../mfc/reference/combo-box-styles.md) , un double\-clic ne peut pas se produire parce qu'un clic masque la zone de liste.  
  
-   **ON\_CBN\_DROPDOWN** la zone de liste d'une zone de liste déroulante est sur le point de déroulante \(être rendu visible\).  Ce message de notification peut se produire pour une zone de liste déroulante avec le style de **CBS\_DROPDOWN** ou de **CBS\_DROPDOWNLIST** .  
  
-   **ON\_CBN\_EDITCHANGE** l'utilisateur a pris une action qui peut avoir modifié le texte dans la partie de contrôle d'édition d'une zone de liste déroulante.  Contrairement au message de **CBN\_EDITUPDATE** , ce message est envoyé après les mises à jour Windows l'écran.  Il n'est pas envoyé si la zone de liste déroulante a le style de **CBS\_DROPDOWNLIST** .  
  
-   **ON\_CBN\_EDITUPDATE** la partie du contrôle d'édition d'une zone de liste déroulante est autour de le texte modifié par affichage.  Ce message de notification est envoyé fois que le contrôle a mis en forme du texte mais avant qu'il affiche le texte.  Il n'est pas envoyé si la zone de liste déroulante a le style de **CBS\_DROPDOWNLIST** .  
  
-   **ON\_CBN\_ERRSPACE** la zone de liste déroulante ne peut pas allouer suffisamment de mémoire pour accepter une demande spécifique.  
  
-   **ON\_CBN\_SELENDCANCEL** \(Windows 3.1 et ultérieure.\) Indique la sélection de l'utilisateur doit être annulé.  L'utilisateur clique sur un élément puis clique sur une fenêtre ou un contrôle différent pour masquer la zone de liste d'une zone de liste déroulante.  Ce message de notification est envoyé avant le message de notification de **CBN\_CLOSEUP** pour indiquer que la sélection de l'utilisateur doit être ignorée.  Le message de notification de **CBN\_SELENDCANCEL** ou de **CBN\_SELENDOK** est envoyé même si le message de notification de **CBN\_CLOSEUP** n'est pas envoyé \(comme dans le cas d'une zone de liste déroulante avec le style de **CBS\_SIMPLE** \).  
  
-   **ON\_CBN\_SELENDOK** l'utilisateur sélectionne un élément puis appuie sur la touche ENTRÉE ou clique sur la touche de direction BAS pour masquer la zone de liste d'une zone de liste déroulante.  Ce message de notification est envoyé avant le message de **CBN\_CLOSEUP** pour indiquer que la sélection de l'utilisateur doit être considéré comme valide.  Le message de notification de **CBN\_SELENDCANCEL** ou de **CBN\_SELENDOK** est envoyé même si le message de notification de **CBN\_CLOSEUP** n'est pas envoyé \(comme dans le cas d'une zone de liste déroulante avec le style de **CBS\_SIMPLE** \).  
  
-   **ON\_CBN\_KILLFOCUS** la zone de liste déroulante perd le focus d'entrée.  
  
-   **ON\_CBN\_SELCHANGE** la sélection dans la zone de liste d'une zone de liste déroulante est sur le point d'être modifié suite à l'utilisateur clique sur dans la zone de liste ou la modification de la sélection à l'aide de les touches de direction.  Lors de ce message, le texte du contrôle d'édition de la zone de liste déroulante peut être récupéré via un `GetLBText` ou d'une fonction similaire différente.  `GetWindowText` ne peut pas être utilisée.  
  
-   **ON\_CBN\_SETFOCUS** la zone de liste déroulante reçoit le focus d'entrée.  
  
 Si vous créez un objet d' `CComboBox` dans une boîte de dialogue \(via une ressource de boîte de dialogue\), l'objet d' `CComboBox` est automatiquement détruit lorsque l'utilisateur ferme la boîte de dialogue.  
  
 Si vous incluez un objet d' `CComboBox` dans un autre objet window, vous n'avez pas besoin de le détruire.  Si vous créez l'objet d' `CComboBox` sur la pile, elle est perdue automatiquement.  Si vous créez l'objet d' `CComboBox` sur le tas à l'aide de la fonction de **nouveau** , vous devez appeler **supprimer** sur l'objet pour le détruire lorsque la zone de liste déroulante windows est perdue.  
  
 **Note** si vous souhaitez gérer `WM_KEYDOWN` et des messages d' `WM_CHAR` , vous devez sous\-classe la modification et les contrôles de zone de liste déroulante de la zone de liste déroulante, dériver des classes d' `CEdit` et d' `CListBox`, et ajouter des gestionnaires pour ces messages aux classes dérivées.  Pour plus d'informations, consultez [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;Q174667](http://support.microsoft.com/default.aspx?scid=kb;en-us;Q174667) et [CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md).  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CComboBox`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [CTRLBARS exemple MFC](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CListBox Class](../../mfc/reference/clistbox-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)   
 [CDialog Class](../../mfc/reference/cdialog-class.md)