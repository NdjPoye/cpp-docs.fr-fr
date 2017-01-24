---
title: "TN014&#160;: contr&#244;les personnalis&#233;s | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "contrôles personnalisés (MFC)"
  - "TN014"
ms.assetid: 1917a498-f643-457c-b570-9a0af7dbf7bb
caps.latest.revision: 21
caps.handback.revision: 17
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN014&#160;: contr&#244;les personnalis&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit la prise en charge MFC pour les contrôles personnalisés et de dessin automatique.  Elle explique également le sous\-classement dynamique, et décrit la relation entre les objets [CWnd](../mfc/reference/cwnd-class.md) et `HWND`.  
  
 L'exemple d'application CTRLTEST de MFC montre comment utiliser de nombreux contrôles personnalisés.  Consultez le code source de l'exemple de [CTRLTEST](../top/visual-cpp-samples.md) de MFC et l'aide en ligne.  
  
## Contrôles \/ Menus Owner Draw  
 Windows prend en charge les contrôles et les menus Owner Draw en utilisant des messages Windows.  La fenêtre parente de n'importe quel contrôle ou menu reçoit ces messages et appelle des fonctions en réponse.  Vous pouvez remplacer ces fonctions pour personnaliser l'aspect visuel et le comportement du contrôle ou du menu Owner Draw.  
  
 MFC gère directement Owner Draw avec les fonctions suivantes :  
  
-   [CWnd::OnDrawItem](../Topic/CWnd::OnDrawItem.md)  
  
-   [CWnd::OnMeasureItem](../Topic/CWnd::OnMeasureItem.md)  
  
-   [CWnd::OnCompareItem](../Topic/CWnd::OnCompareItem.md)  
  
-   [CWnd::OnDeleteItem](../Topic/CWnd::OnDeleteItem.md)  
  
 Il vous est possible de remplacer ces fonctions dans votre classe dérivée `CWnd` pour implémenter le comportement de draw personnalisé.  
  
 Cette approche ne mène pas à du code réutilisable.  Si vous avez deux contrôles similaires dans deux différentes classes `CWnd`, vous devez implémenter le comportement du contrôle personnalisé dans deux emplacements.  L'architecture MFC\-compatible du contrôle de dessin automatique résoud ce problème.  
  
## Contrôles et menus de dessin automatique  
 MFC fournit une implémentation par défaut \(dans les classes `CWnd` et [CMenu](../mfc/reference/cmenu-class.md) \) pour les messages standard de Owner Draw.  Cette implémentation par défaut décodera les paramètres Owner Draw et délèguera et les messages Owner Draw aux contrôles ou menus.  On parle dessin automatique car le code de dessin est dans la classe de contrôle ou dans le menu, et non dans la fenêtre propriétaire.  
  
 En utilisant les contrôles de dessin automatique vous pouvez générer des classes de contrôle réutilisables qui utilisent la sémantique Owner Draw pour afficher le contrôle.  Le code pour dessiner le contrôle est dans la classe de contrôle, et non son parent.  Il s'agit d'une approche orienté objet de programmation de contrôle personnalisé.  Ajoutez la liste suivante de fonctions à vos classes de dessin automatique :  
  
-   Pour les boutons de dessin automatique :  
  
    ```  
    CButton:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw this button  
    ```  
  
-   Pour les champs de dessin automatique :  
  
    ```  
    CMenu:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this menu  
    CMenu:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this menu  
    ```  
  
-   Pour les zones de liste de dessin automatique :  
  
    ```  
    CListBox:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this list box  
    CListBox:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this list box  
  
    CListBox:CompareItem(LPCOMPAREITEMSTRUCT);  
            // insert code to compare two items in this list box if LBS_SORT  
    CListBox:DeleteItem(LPDELETEITEMSTRUCT);  
            // insert code to delete an item from this list box  
    ```  
  
-   Pour les zones de liste déroulante de dessin automatique :  
  
    ```  
    CComboBox:MeasureItem(LPMEASUREITEMSTRUCT);  
            // insert code to measure the size of an item in this combo box  
    CComboBox:DrawItem(LPDRAWITEMSTRUCT);  
            // insert code to draw an item in this combo box  
  
    CComboBox:CompareItem(LPCOMPAREITEMSTRUCT);  
            // insert code to compare two items in this combo box if CBS_SORT  
    CComboBox:DeleteItem(LPDELETEITEMSTRUCT);  
            // insert code to delete an item from this combo box  
    ```  
  
 Pour plus d'informations sur les structures Owner Draw \([DRAWITEMSTRUCT](../mfc/reference/drawitemstruct-structure.md), [MEASUREITEMSTRUCT](../mfc/reference/measureitemstruct-structure.md), [COMPAREITEMSTRUCT](../mfc/reference/compareitemstruct-structure.md), et [DELETEITEMSTRUCT](../mfc/reference/deleteitemstruct-structure.md)\) consultez la documentation de MFC pour `CWnd::OnDrawItem`, `CWnd::OnMeasureItem`, `CWnd::OnCompareItem`, et `CWnd::OnDeleteItem`.  
  
## Utilisation des contrôles et menus de dessin automatique  
 Pour les champs de dessin automatique, vous devez substituer les méthodes `OnMeasureItem` et `OnDrawItem`.  
  
 Pour les zones de liste et des zones de liste déroulante de dessin automatique, vous devez remplacer `OnMeasureItem` et `OnDrawItem`.  Vous devez spécifier le style `LBS_OWNERDRAWVARIABLE` pour les zones de liste ou le style `CBS_OWNERDRAWVARIABLE` pour les zones de liste déroulante du modèle de la boîte de dialogue.  Le style `OWNERDRAWFIXED` ne fonctionne pas avec les éléments de dessin automatique car la hauteur fixe d'élément est définie avant que les commandes de dessin automatique soient joints vers la zone de liste. \(Vous pouvez utiliser les méthodes [CListBox::SetItemHeight](../Topic/CListBox::SetItemHeight.md) et [CComboBox::SetItemHeight](../Topic/CComboBox::SetItemHeight.md) pour surmonter cette limitation\).  
  
 Le basculement vers un style `OWNERDRAWVARIABLE` force le système à appliquer le style `NOINTEGRALHEIGHT` au contrôle.  Étant donné que le contrôle ne peut pas calculer une hauteur intégrale avec des éléments de taille variable, le style par défaut `INTEGRALHEIGHT` est ignoré et le contrôle est toujours `NOINTEGRALHEIGHT`.  Si les éléments sont à altitude fixe, vous pouvez empêcher les éléments partiels d'être dessinés en spécifiant la taille de contrôle soit un multiplicateur entier de la taille d'élément.  
  
 Pour les zones de liste et des zones de liste déroulante de dessin automatique avec le style `LBS_SORT` ou `CBS_SORT`, vous devez substituer la méthode `OnCompareItem`.  
  
 Pour les zones de liste et des zones de liste déroulante de dessin automatique, `OnDeleteItem` n'est généralement pas remplacée.  Vous pouvez remplacer `OnDeleteItem` si vous souhaitez effectuer le traitement spécial.  Un cas où cela s'appliquerait lorsque la mémoire ou d'autres ressources sont stockées avec chaque élément de la zone de liste ou de la zone de liste déroulante.  
  
## Exemples de contrôles et de menus de dessin automatique  
 L'exemple général [CTRLTEST](../top/visual-cpp-samples.md) de MFC fournit des exemples d'un menu de dessin automatique et une zone de liste de dessin automatique.  
  
 L'exemple le plus typique d'un bouton de dessin automatique est un bitmap bouton.  Un bouton bitmap est un bouton qui affiche une, deux, trois ou images bitmap pour les différents états.  Un exemple de cette opération est fourni dans la classe [CBitmapButton](../mfc/reference/cbitmapbutton-class.md)de MFC.  
  
## Sous\-classement dynamique  
 Occasionnellement vous souhaiterez modifier la fonctionnalité d'objet qui existe déjà.  Les exemples précédents requièrent que vous personnalisiez les contrôles avant qu'ils soient créés.  Le sous\-classement dynamique permet de personnaliser un contrôle qui a déjà été créé.  
  
 Le sous\-classement est le terme Windows pour remplacer le [WndProc](http://msdn.microsoft.com/fr-fr/94ba8ffa-3c36-46d4-ac74-9bd10b1ffd26) d'une fenêtre avec `WndProc` personnalisé et appeler l'ancien`WndProc` pour les fonctionnalités par défaut.  
  
 Cela ne doit pas être confondu avec la dérivation de classe C\+\+.  Pour une clarification, les termes C\+\+ *la classe de base* et *la classe dérivée* sont analogues *à la superclasse* et *sous\-classe* dans le modèle objet windows.  La dérivation C\+\+ MFC et avec le sous\-classement windows sont fonctionnellement similaires, à moins que C\+\+ ne prenne pas en charge le sous\-classement dynamique.  
  
 La classe `CWnd` fournit la connexion entre l'objet du actuel C\+\+ \(dérivé de `CWnd`\) et un objet fenêtre windows \(appelé `HWND`\).  
  
 Il existe trois façons courantes que pour lier ceux\-ci :  
  
-   `CWnd` crée le `HWND`.  Vous pouvez modifier le comportement dans une classe dérivée en créant une classe dérivée de`CWnd`.  Le `HWND` est créé lorsque l'application appelle [CWnd::Create](../Topic/CWnd::Create.md).  
  
-   L'application `CWnd` joint à un `HWND`existant.  Le comportement de la fenêtre existante n'est pas modifié.  Il s'agit d'un cas de délégation qui est rendu possible en appelant [CWnd::Attach](../Topic/CWnd::Attach.md) pour allier un `HWND` existant à un objet `CWnd`.  
  
-   `CWnd` est attaché à un `HWND` existant et il vous est possible de modifier le comportement dans une classe dérivée.  On parle sous\-classement dynamique car nous modifions le comportement, par conséquent la classe, de l'objet Windows au moment de l'exécution.  
  
 Vous pouvez obtenir le sous\-classement dynamique à l'aide de les méthodes [CWnd::SubclassWindow](../Topic/CWnd::SubclassWindow.md) et `` [CWnd::SubclassDlgItem](../Topic/CWnd::SubclassDlgItem.md).  
  
 Les deux routines joignent un objet `CWnd` à `HWND` existant.  `SubclassWindow` prend le `HWND` directement.  `SubclassDlgItem` est une fonction d'assistance qui accepte un ID de contrôle et la fenêtre parente.  `SubclassDlgItem` est conçu pour joindre des objets C\+\+ aux contrôles de la boîte de dialogue créée d'un modèle de boîte de dialogue.  
  
 Consultez l'exemple [CTRLTEST](../top/visual-cpp-samples.md) pour afficher plusieurs exemples de situations où utiliser `SubclassWindow` et `SubclassDlgItem`.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)