---
title: "TN062&#160;: r&#233;flexion de message pour les contr&#244;les Windows | Microsoft Docs"
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
  - "vc.controls.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "réflexion de message"
  - "messages de notification"
  - "ON_CONTROL_REFLECT (macro)"
  - "ON_CONTROL_REFLECT_EX (macro)"
  - "ON_NOTIFY (message)"
  - "ON_NOTIFY_REFLECT (message)"
  - "ON_NOTIFY_REFLECT_EX (message)"
  - "ON_UPDATE_COMMAND_UI_REFLECT (macro)"
  - "ON_WM_CHARTOITEM_REFLECT (macro)"
  - "ON_WM_COMPAREITEM_REFLECT (macro)"
  - "ON_WM_CTLCOLOR_REFLECT (macro)"
  - "ON_WM_DELETEITEM_REFLECT (macro)"
  - "ON_WM_DRAWITEM_REFLECT (macro)"
  - "ON_WM_HSCROLL_REFLECT (macro)"
  - "ON_WM_MEASUREITEM_REFLECT (macro)"
  - "ON_WM_PARENTNOTIFY_REFLECT (macro)"
  - "ON_WM_VKEYTOITEM_REFLECT (macro)"
  - "ON_WM_VSCROLL_REFLECT (macro)"
  - "TN062"
  - "WM_COMMAND"
  - "WM_CTLCOLOR (message)"
  - "WM_NOTIFY (message)"
ms.assetid: 53efb0ba-fcda-4fa0-a3c7-14e0b78fb494
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN062&#160;: r&#233;flexion de message pour les contr&#244;les Windows
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette note technique décrit le renvoi de message, une nouvelle fonctionnalité de MFC 4,0.  Elle contient également des instructions pour créer un contrôle réutilisable simple qui utilise le renvoi de message.  
  
 Cette note technique ne présente pas le renvoi de message à mesure qu'il applique aux contrôles ActiveX \(anciennement appelé les contrôles OLE\).  Consultez l'article [Contrôles ActiveX : Sous\-classement un contrôle Windows](../mfc/mfc-activex-controls-subclassing-a-windows-control.md).  
  
 **Quel est le message renvoyé ?**  
  
 Les contrôles Windows envoient fréquemment des messages de notification vers les fenêtres parentes.  Par exemple, de nombreuses commandes envoient un message de notification de couleur \(`WM_CTLCOLOR` ou une de ses variantes\) à leur parents pour leur fournir un pinceau pour peindre l'arrière\-plan de la commande.  
  
 Dans windows et dans MFC avant la version 4,0, la fenêtre parente, souvent une boîte de dialogue, est chargée de gérer les messages.  Cela signifie que le code pour la gestion du message doit être dans la classe parente de la fenêtre et qu'il doit être dupliqué dans chaque classe qui doit traiter ce message.  Dans le cas ci\-dessus, chaque boîte de dialogue que les commandes souhaitées d'arrière\-plan personnalisés doit traiter le message de notification de couleur.  Il est beaucoup plus facile de réutiliser le code s'il peut écrire une classe de contrôle qui gèrerait sa propre couleur d'arrière\-plan.  
  
 Dans MFC 4,0, l'ancien mécanisme fonctionne toujours — les fenêtres parentes peuvent traiter les messages de notification.  En outre, toutefois, MFC 4,0 facilite la réutilisation en fournissant une fonctionnalité appelée « renvoi de message » qui autorise les messages de notification à être gérés dans la fenêtre de commande enfant ou la fenêtre parente, ou dans les deux.  Dans l'exemple de couleur d'arrière\-plan, vous pouvez désormais écrire une classe de contrôle qui définit sa propre couleur d'arrière\-plan en gérant le message renvoyé `WM_CTLCOLOR` — tout ça sans compter sur l'objet parent. Notez que le renvoi de message est implémentée par MFC, et non par Wndows, la classe de la fenêtre parente doit être dérivée de `CWnd` pour que le renvoi de messages fonctionne.\)  
  
 Les versions antérieures de MFC faisaient quelque chose de semblable pour le renvoi de message en fournissant des fonctions virtuelles pour certains messages, tels que les messages des zones de liste owner\-drawn \(`WM_DRAWITEM`, etc.\).  Le nouveau mécanisme de renvoi de message est généralisé et cohérent.  
  
 Le renvoi de message est une compatibilité descendante complète avec le code écrit pour les versions de MFC avant 4,0.  
  
 Si vous avez fourni un gestionnaire d'un message spécifique, ou pour une série de messages, dans la classe parente de la fenêtre, cela remplacera les gestionnaires de messages renvoyés par le même message si vous n'appelez pas la fonction gestionnaire de classe de base dans votre propre gestionnaire.  Par exemple, si vous gérez `WM_CTLCOLOR` dans la classe de la boîte de dialogue, votre gestion remplace tous les gestionnaires de messages apparaissent.  
  
 Si, dans la classe fenêtre parente, vous devez fournir un gestionnaire d'un message spécifique de **WM\_NOTIFY** ou d'une chaîne de message **WM\_NOTIFY**, votre gestionnaire est appelé uniquement si le contrôle enfant de ces messages n'a pas de gestionnaire de messages en miroir par **ON\_NOTIFY\_REFLECT\(\)**.  Si vous utilisez **ON\_NOTIFY\_REFLECT\_EX\(\)** dans la table des messages, votre gestionnaire de messages peut autoriser ou ne pas autoriser la fenêtre parente pour traiter le message.  Si le gestionnaire renvoie **FALSE**, le message est également traité par le parent, tandis qu'un appel qui renvoie **TRUE** ne permet pas au parent de le gérer.  Notez que le message en miroir est traité avant le message de notification.  
  
 Lorsqu'un message de **WM\_NOTIFY** est envoyé, la commande se voit proposer la première occasion pour la gérer.  Si tout autre message en miroir est envoyé, la fenêtre parente a la première occasion de la gérer et la commande recevra le message en miroir.  Pour ce faire, il a besoin d'une fonction gestionnaire et une entrée appropriée dans la table des messages de la classe de la commande.  
  
 La macro table des messages pour les messages renvoyés est légèrement différente pour les notifications normales : elle a **\_REFLECT** ajouté à son nom habituel.  Par exemple, pour traiter un message **WM\_NOTIFY** du parent, utilisez la macro `ON_NOTIFY` dans la table des messages du parent.  Pour traiter le message en miroir dans le contrôle enfant, utilisez la macro **ON\_NOTIFY\_REFLECT** dans la table des messages du contrôle enfant.  Dans certains cas, les paramètres sont différents.  Notez que ClassWizard peut généralement ajouter des entrées de la table des messages pour vous et fournir des implémentations de squelettes de fonctions avec les paramètres corrects.  
  
 Consultez [TN061 : Messages d'ON\_NOTIFY et de WM\_NOTIFY](../mfc/tn061-on-notify-and-wm-notify-messages.md) pour plus d'informations sur le nouveau message de **WM\_NOTIFY**.  
  
 **Entrées de la table des messages et les prototypes de fonction gestionnaire des messages renvoyés**  
  
 Pour traiter un message de notification de contrôle en miroir, utilisez les macros table de messages et les prototypes de fonctions répertoriées dans le tableau ci\-dessous.  
  
 ClassWizard peut généralement ajouter ces entrées de la table des messages pour vous et fournir des implémentations de squelettes de fonctions.  Consultez [Définir un gestionnaire de messages d'un message en miroir](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md) pour plus d'informations sur la définition des gestionnaires des messages renvoyés.  
  
 Pour convertir à partir du message vers le nom de la macro en miroir, ajoutez **ON\_** et ajoutez **\_REFLECT**.  Par exemple, `WM_CTLCOLOR` devient **ON\_WM\_CTLCOLOR\_REFLECT**. \(Pour voir quels messages peuvent être renvoyés, effectuez une conversion inverse sur les macro entrées dans la table ci\-dessous.\)  
  
 Les trois exceptions à cette règle ci\-dessus sont les suivantes :  
  
-   La macro pour les notifications **WM\_COMMAND** est **ON\_CONTROL\_REFLECT**.  
  
-   La macro des réflexions **WM\_NOTIFY** est **ON\_NOTIFY\_REFLECT**.  
  
-   La macro des réflexions `ON_UPDATE_COMMAND_UI` est **ON\_UPDATE\_COMMAND\_UI\_REFLECT**.  
  
 Dans les cas individuels ci\-dessus, vous devez spécifier le nom de la fonction membre gestionnaire.  Dans les autres cas, vous devez utiliser le nom standard pour la fonction gestionnaire.  
  
 Les significations des paramètres et des valeurs de résultats des fonctions sont documentées soit dans le nom de fonction soit dans le nom de la fonction avec **On** ajouté.  Par exemple, **CtlColor** est documenté dans `OnCtlColor`.  Plusieurs gestionnaires de messages renvoyés requièrent moins de paramètres que les gestionnaires similaires dans une fenêtre parente.  Correspondance uniquement entre les noms dans le tableau ci\-dessous avec les noms des paramètres formels dans la documentation.  
  
|Entrée de mappage|Prototype de fonction|  
|-----------------------|---------------------------|  
|**ON\_CONTROL\_REFLECT\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( \);**|  
|**ON\_NOTIFY\_REFLECT\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( NMHDR \***  `pNotifyStruct` **, LRESULT\***  *résultat*  **\);**|  
|**ON\_UPDATE\_COMMAND\_UI\_REFLECT\(**  `memberFxn`  **\)**|**afx\_msg void**  `memberFxn`  **\( CCmdUI\***  `pCmdUI`  **\);**|  
|**ON\_WM\_CTLCOLOR\_REFLECT\( \)**|**afx\_msg HBRUSH CtlColor \( CDC\***  `pDC` **, UINT**  `nCtlColor`  **\);**|  
|**ON\_WM\_DRAWITEM\_REFLECT\( \)**|**afx\_msg void DrawItem \( LPDRAWITEMSTRUCT**  `lpDrawItemStruct`  **\);**|  
|**ON\_WM\_MEASUREITEM\_REFLECT\( \)**|**afx\_msg void MeasureItem \( LPMEASUREITEMSTRUCT**  `lpMeasureItemStruct`  **\);**|  
|**ON\_WM\_DELETEITEM\_REFLECT\( \)**|**afx\_msg void DeleteItem \( LPDELETEITEMSTRUCT**  `lpDeleteItemStruct`  **\);**|  
|**ON\_WM\_COMPAREITEM\_REFLECT\( \)**|**afx\_msg int CompareItem \( LPCOMPAREITEMSTRUCT**  `lpCompareItemStruct`  **\);**|  
|**ON\_WM\_CHARTOITEM\_REFLECT\( \)**|**afx\_msg int CharToItem \( UINT**  `nKey` **, UINT**  `nIndex`  **\);**|  
|**ON\_WM\_VKEYTOITEM\_REFLECT\( \)**|**afx\_msg int VKeyToItem \( UINT**  `nKey` **, UINT**  `nIndex`  **\);**|  
|**ON\_WM\_HSCROLL\_REFLECT\( \)**|**afx\_msg void HScroll \( UINT**  `nSBCode` **, UINT**  `nPos`  **\);**|  
|**ON\_WM\_VSCROLL\_REFLECT\( \)**|**afx\_msg void VScroll \( UINT**  `nSBCode` **, UINT**  `nPos`  **\);**|  
|**ON\_WM\_PARENTNOTIFY\_REFLECT \(\)**|**afx\_msg void ParentNotify \( UINT**  `message` **, LPARAM**  `lParam`  **\);**|  
  
 Les macros **ON\_NOTIFY\_REFLECT** et **ON\_CONTROL\_REFLECT** sont des variations qui permettent à plusieurs objets \(telles que la commande et son parent\) pour traiter un message donné.  
  
|Entrée de mappage|Prototype de fonction|  
|-----------------------|---------------------------|  
|**ON\_NOTIFY\_REFLECT\_EX\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg BOOL**  `memberFxn`  **\( NMHDR \***  `pNotifyStruct` **, LRESULT\***  *résultat*  **\);**|  
|**ON\_CONTROL\_REFLECT\_EX\(**  `wNotifyCode` **,**  `memberFxn`  **\)**|**afx\_msg BOOL**  `memberFxn`  **\( \);**|  
  
## Gérer les messages renvoyés : Un exemple de contrôle réutilisable  
 Cet exemple simple créé un contrôle réutilisable appelé `CYellowEdit`.  Le contrôle fonctionne pareil qu'un contrôle d'édition standard sauf qu'il affiche le texte noir sur un arrière\-plan jaune.  Il est facile d'ajouter des fonctions membres qui donneraient l'autorisation de commande `CYellowEdit` à des couleurs d'affichage.  
  
#### Pour essayer l'exemple qui créé une commande réutilisable  
  
1.  Créer une nouvelle boîte de dialogue dans une application existante.  Pour plus d'informations, consultez la rubrique [dialog editor](../mfc/dialog-editor.md).  
  
     Vous devez disposer d'une application dans laquelle développer la commande réutilisable.  Si vous ne possédez pas d'application existante à utiliser, créez une application basée sur les boîtes de dialogue utilisant AppWizard.  
  
2.  Le projet est chargé dans Visual C\+\+, utilisez ClassWizard pour créer une nouvelle classe appelée `CYellowEdit` fondée sur `CEdit`.  
  
3.  Ajoutez les variables composées des trois membres à votre classe `CYellowEdit`.  Les deux premiers sont des variables de **COLORREF** pour contenir la couleur du texte et de l'arrière\-plan.  La troisième est un objet `CBrush` qui contiendra le pinceau pour peindre l'arrière\-plan.  L'objet `CBrush` vous permet de créer le pinceau une fois, le référencer simplement après cela, et de détruire le pinceau automatiquement lorsque la commande `CYellowEdit` est détruite.  
  
4.  Initialisez les variables membres en entrant le constructeur comme suit :  
  
    ```  
    CYellowEdit::CYellowEdit()  
    {  
       m_clrText = RGB( 0, 0, 0 );  
       m_clrBkgnd = RGB( 255, 255, 0 );  
       m_brBkgnd.CreateSolidBrush( m_clrBkgnd );  
    }  
    ```  
  
5.  En utilisant ClassWizard, ajoutez un gestionnaire du message en miroir `WM_CTLCOLOR` à votre classe `CYellowEdit`.  Remarquez que le signe égal devant le nom de message dans la liste de messages que vous pouvez gérer indique que le message est mis en miroir.  Cela est décrit dans [Définir un gestionnaire de messages pour un message en miroir](../mfc/reference/defining-a-message-handler-for-a-reflected-message.md).  
  
     ClassWizard ajoute la macro suivante de la table des messages et la fonction squelette pour effectuer les opérations suivantes :  
  
    ```  
    ON_WM_CTLCOLOR_REFLECT()  
  
    // Note: other code will be in between....  
  
    HBRUSH CYellowEdit::CtlColor(CDC* pDC, UINT nCtlColor)   
    {  
       // TODO: Change any attributes of the DC here  
  
       // TODO: Return a non-NULL brush if the  
       //   parent's handler should not be called  
       return NULL;  
    }  
    ```  
  
6.  Remplacez le corops de la fonction par le code suivant.  Le code spécifie la couleur du texte, la couleur d'arrière\-plan de texte, la couleur d'arrière\-plan pour le reste de la commande.  
  
    ```  
    pDC->SetTextColor( m_clrText );   // text  
    pDC->SetBkColor( m_clrBkgnd );   // text bkgnd  
    return m_brBkgnd;            // ctl bkgnd  
    ```  
  
7.  Créez une commande d'édition dans la boîte de dialogue, puis joignez\- le à une variable membre en double\-cliquant sur le contrôle d'édition tout en conservant une clé d'ordre bas.  Dans la boîte de dialogue Ajouter une variable membre, terminez le nom de la variable et sélectionnez « contrôle » pour la catégorie, puis « CYellowEdit » pour le type de variable.  N'oubliez pas de définir l'ordre de tabulation dans la boîte de dialogue.  En outre, veillez à inclure le fichier d'en\-tête pour le contrôle `CYellowEdit` dans le fichier d'en\-tête de la boîte de dialogue.  
  
8.  Générez et exécutez votre application.  Le contrôle d'édition aura un arrière\-plan jaune.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)