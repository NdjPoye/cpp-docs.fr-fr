---
title: "CListBox Class | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CListBox"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CListBox (classe)"
  - "zones de liste"
ms.assetid: 7ba3c699-c286-4cd9-9066-532c41ec05d1
caps.latest.revision: 26
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 28
---
# CListBox Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'une zone de liste windows.  
  
## Syntaxe  
  
```  
class CListBox : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CListBox::CListBox](../Topic/CListBox::CListBox.md)|Construit un objet `CListBox`.|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CListBox::AddString](../Topic/CListBox::AddString.md)|Ajoute une chaîne à une zone de liste.|  
|[CListBox::CharToItem](../Topic/CListBox::CharToItem.md)|Substitution pour fournir `WM_CHAR` personnalisé gestion pour les zones de liste owner\-draw qui n'ont pas de chaînes.|  
|[CListBox::CompareItem](../Topic/CListBox::CompareItem.md)|Appelé par l'infrastructure pour déterminer la position d'un nouvel élément dans une zone de liste triée owner\-draw.|  
|[CListBox::Create](../Topic/CListBox::Create.md)|Crée la zone de liste windows et l'attache à l'objet d' `CListBox` .|  
|[CListBox::DeleteItem](../Topic/CListBox::DeleteItem.md)|Appelé par l'infrastructure lorsque l'utilisateur supprime un élément d'une zone de liste owner\-draw.|  
|[CListBox::DeleteString](../Topic/CListBox::DeleteString.md)|Supprime une chaîne d'une zone de liste.|  
|[CListBox::Dir](../Topic/CListBox::Dir.md)|Ajoute des noms de fichiers, les lecteurs, ou les deux à partir de le répertoire actif à une zone de liste.|  
|[CListBox::DrawItem](../Topic/CListBox::DrawItem.md)|Appelé par l'infrastructure lorsqu'un aspect visuel d'une zone de liste owner\-draw change.|  
|[CListBox::FindString](../Topic/CListBox::FindString.md)|Recherche une chaîne dans une zone de liste.|  
|[CListBox::FindStringExact](../Topic/CListBox::FindStringExact.md)|Recherche la première chaîne de zone de liste qui correspond à une chaîne spécifiée.|  
|[CListBox::GetAnchorIndex](../Topic/CListBox::GetAnchorIndex.md)|Extrait l'index de base zéro de l'élément actuel d'ancrage dans une zone de liste.|  
|[CListBox::GetCaretIndex](../Topic/CListBox::GetCaretIndex.md)|Détermine l'index de l'élément qui a le rectangle de focus dans une zone de liste à sélection multiple.|  
|[CListBox::GetCount](../Topic/CListBox::GetCount.md)|Retourne le nombre de chaînes dans une zone de liste.|  
|[CListBox::GetCurSel](../Topic/CListBox::GetCurSel.md)|Retourne l'index de base zéro de la chaîne sélectionnée dans une zone de liste.|  
|[CListBox::GetHorizontalExtent](../Topic/CListBox::GetHorizontalExtent.md)|Retourne la largeur en pixels qu'une zone de liste peut être horizontale vous faites.|  
|[CListBox::GetItemData](../Topic/CListBox::GetItemData.md)|Retourne la valeur 32 bits associé à l'élément de zone de liste.|  
|[CListBox::GetItemDataPtr](../Topic/CListBox::GetItemDataPtr.md)|Retourne un pointeur vers un élément de zone de liste.|  
|[CListBox::GetItemHeight](../Topic/CListBox::GetItemHeight.md)|Détermine la hauteur d'éléments dans une zone de liste.|  
|[CListBox::GetItemRect](../Topic/CListBox::GetItemRect.md)|Retourne le rectangle englobant de l'élément de zone de liste à mesure qu'il est actuellement affiché.|  
|[CListBox::GetListBoxInfo](../Topic/CListBox::GetListBoxInfo.md)|Récupère le nombre d'éléments par colonne.|  
|[CListBox::GetLocale](../Topic/CListBox::GetLocale.md)|Récupère l'identificateur de paramètres régionaux pour une zone de liste.|  
|[CListBox::GetSel](../Topic/CListBox::GetSel.md)|Retourne l'état de sélection d'un élément de zone de liste.|  
|[CListBox::GetSelCount](../Topic/CListBox::GetSelCount.md)|Retourne le nombre de chaînes actuellement sélectionnées dans une zone de liste à sélection multiple.|  
|[CListBox::GetSelItems](../Topic/CListBox::GetSelItems.md)|Retourne les index des chaînes actuellement sélectionnées dans une zone de liste.|  
|[CListBox::GetText](../Topic/CListBox::GetText.md)|Copier un élément de zone de liste dans une mémoire tampon.|  
|[CListBox::GetTextLen](../Topic/CListBox::GetTextLen.md)|Retourne la longueur en octets d'un élément de zone de liste.|  
|[CListBox::GetTopIndex](../Topic/CListBox::GetTopIndex.md)|Retourne l'index de la première chaîne visible dans une zone de liste.|  
|[CListBox::InitStorage](../Topic/CListBox::InitStorage.md)|Préaffecte les blocs de mémoire pour les éléments et les chaînes de zone de liste.|  
|[CListBox::InsertString](../Topic/CListBox::InsertString.md)|Insère une chaîne à un emplacement spécifique dans une zone de liste.|  
|[CListBox::ItemFromPoint](../Topic/CListBox::ItemFromPoint.md)|Retourne l'index de l'élément de zone de liste le plus près un point.|  
|[CListBox::MeasureItem](../Topic/CListBox::MeasureItem.md)|Appelé par l'infrastructure lorsqu'une zone de liste owner\-draw est créée pour déterminer les dimensions zone de liste.|  
|[CListBox::ResetContent](../Topic/CListBox::ResetContent.md)|Efface toutes les entrées d'une zone de liste.|  
|[CListBox::SelectString](../Topic/CListBox::SelectString.md)|Recherche et sélectionne une chaîne dans une zone de liste à sélection unique.|  
|[CListBox::SelItemRange](../Topic/CListBox::SelItemRange.md)|Active ou désélectionne une plage des chaînes dans une zone de liste à sélection multiple.|  
|[CListBox::SetAnchorIndex](../Topic/CListBox::SetAnchorIndex.md)|Définit le point d'ancrage dans une zone de liste à sélection multiple pour démarrer une sélection étendue.|  
|[CListBox::SetCaretIndex](../Topic/CListBox::SetCaretIndex.md)|Définit le rectangle de focus à l'élément à l'index spécifié dans une zone de liste à sélection multiple.|  
|[CListBox::SetColumnWidth](../Topic/CListBox::SetColumnWidth.md)|Définit la largeur de colonne d'une zone de liste multicolonne.|  
|[CListBox::SetCurSel](../Topic/CListBox::SetCurSel.md)|Sélectionne une chaîne de zone de liste.|  
|[CListBox::SetHorizontalExtent](../Topic/CListBox::SetHorizontalExtent.md)|Définit la largeur en pixels qu'une zone de liste peut être horizontale vous faites.|  
|[CListBox::SetItemData](../Topic/CListBox::SetItemData.md)|Définit la valeur 32 bits associé à l'élément de zone de liste.|  
|[CListBox::SetItemDataPtr](../Topic/CListBox::SetItemDataPtr.md)|Définit un pointeur vers l'élément de zone de liste.|  
|[CListBox::SetItemHeight](../Topic/CListBox::SetItemHeight.md)|Définit la hauteur d'éléments dans une zone de liste.|  
|[CListBox::SetLocale](../Topic/CListBox::SetLocale.md)|Définit l'identificateur de paramètres régionaux pour une zone de liste.|  
|[CListBox::SetSel](../Topic/CListBox::SetSel.md)|Active ou désélectionne un élément de zone de liste dans une zone de liste à sélection multiple.|  
|[CListBox::SetTabStops](../Topic/CListBox::SetTabStops.md)|Définit les positions de tabulation dans une zone de liste.|  
|[CListBox::SetTopIndex](../Topic/CListBox::SetTopIndex.md)|Définit l'index de base zéro de la première chaîne visible dans une zone de liste.|  
|[CListBox::VKeyToItem](../Topic/CListBox::VKeyToItem.md)|Substitution pour fournir `WM_KEYDOWN` personnalisé gestion pour les zones de liste avec le jeu de styles de **LBS\_WANTKEYBOARDINPUT** .|  
  
## Notes  
 Une zone de liste affiche une liste d'éléments, tels que les noms du fichier, que l'utilisateur peut afficher et sélectionnez.  
  
 Dans une zone de liste à sélection unique, l'utilisateur peut sélectionner un seul élément.  Dans une zone de liste à sélection multiple, une plage d'éléments peuvent être sélectionnés.  Lorsque l'utilisateur sélectionne un élément, il est mis en surbrillance et la zone de liste envoie un message de notification à la fenêtre parente.  
  
 Vous pouvez créer une zone de liste à partir d'un modèle de boîte de dialogue ou directement dans votre code.  Pour créer directement, construisez l'objet d' `CListBox` , puis appelez la fonction membre de [Create](../Topic/CListBox::Create.md) pour créer le contrôle zone de liste déroulante windows et le lier à l'objet d' `CListBox` .  Pour utiliser une zone de liste dans un modèle de boîte de dialogue, déclarer une variable de zone de liste dans votre classe de boîte de dialogue, pour utiliser ensuite `DDX_Control` dans la fonction d' `DoDataExchange` de votre classe de boîte de dialogue pour connecter la variable membre dans le contrôle.  \(cela se fait automatiquement lorsque vous ajoutez une variable de contrôle à votre classe de boîte de dialogue.\)  
  
 La construction peut être un processus à une étape dans une classe dérivée d' `CListBox`.  Entrez un constructeur pour la classe dérivée et appelez **Créer** du constructeur.  
  
 Si vous souhaitez gérer des messages de notification de fenêtres envoyés par une zone de liste à son parent \(généralement une classe dérivée de [CDialog](../../mfc/reference/cdialog-class.md)\), ajoutez une entrée de la table des messages et une fonction membre gestionnaire de messages à la classe parente pour chaque message.  
  
 Chaque entrée de la table des messages prend la forme suivante :  
  
 `ON_Notification( id, memberFxn )`  
  
 où `id` spécifie l'ID de fenêtre enfant du contrôle zone de liste déroulante envoyant la notification et `memberFxn` est le nom de la fonction membre parente que vous avez écrit pour traiter la notification.  
  
 Le prototype de fonction du parent est la suivante :  
  
 `afx_msg void memberFxn( );`  
  
 Voici une liste d'entrées de la table des messages potentiels et une description des cas où elle est envoyée au parent :  
  
-   **ON\_LBN\_DBLCLK** l'utilisateur double\-clique sur une chaîne dans une zone de liste.  Une seule zone de liste comportant le style de [LBS\_NOTIFY](../../mfc/reference/list-box-styles.md) envoie le message de notification.  
  
-   **ON\_LBN\_ERRSPACE** la zone de liste ne peut pas allouer suffisamment de mémoire pour accepter la demande.  
  
-   **ON\_LBN\_KILLFOCUS** la zone de liste perd le focus d'entrée.  
  
-   **ON\_LBN\_SELCANCEL** la sélection actuelle de la zone de liste est annulé.  Ce message n'est envoyé lorsqu'une zone de liste a le style de **LBS\_NOTIFY** .  
  
-   **ON\_LBN\_SELCHANGE** que la sélection dans la zone de liste a changé.  Cette notification n'est pas envoyée si la sélection est modifiée par la fonction membre de [CListBox::SetCurSel](../Topic/CListBox::SetCurSel.md) .  Cette notification s'applique uniquement à une zone de liste comportant le style de **LBS\_NOTIFY** .  Le message de notification de **LBN\_SELCHANGE** est envoyé pour une zone de liste à sélection multiple lorsque l'utilisateur appuie sur une touche de direction, même si la sélection ne change pas.  
  
-   **ON\_LBN\_SETFOCUS** la zone de liste reçoit le focus d'entrée.  
  
-   **ON\_WM\_CHARTOITEM** une zone de liste owner\-draw qui n'a pas de chaînes reçoit un message d' `WM_CHAR` .  
  
-   La zone de liste d'**ON\_WM\_VKEYTOITEM** Un avec le style de **LBS\_WANTKEYBOARDINPUT** reçoit un message d' `WM_KEYDOWN` .  
  
 Si vous créez un objet d' `CListBox` dans une boîte de dialogue \(via une ressource de boîte de dialogue\), l'objet d' `CListBox` est automatiquement détruit lorsque l'utilisateur ferme la boîte de dialogue.  
  
 Si vous créez un objet d' `CListBox` dans une fenêtre, vous pouvez devoir destruction de l'objet d' `CListBox` .  Si vous créez l'objet d' `CListBox` sur la pile, elle est perdue automatiquement.  Si vous créez l'objet d' `CListBox` sur le tas à l'aide de la fonction de **nouveau** , vous devez appeler **supprimer** sur l'objet pour le détruire lorsque l'utilisateur ferme la fenêtre parente.  
  
 Si vous allouez une mémoire de l'objet d' `CListBox` , remplacez le destructeur d' `CListBox` pour que l'allocation.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CListBox`  
  
## Configuration requise  
 **En\-tête :** afxwin.h  
  
## Voir aussi  
 [Exemple CTRLTEST MFC](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [CButton Class](../../mfc/reference/cbutton-class.md)   
 [CComboBox Class](../../mfc/reference/ccombobox-class.md)   
 [CEdit Class](../../mfc/reference/cedit-class.md)   
 [CScrollBar Class](../../mfc/reference/cscrollbar-class.md)   
 [CStatic Class](../../mfc/reference/cstatic-class.md)