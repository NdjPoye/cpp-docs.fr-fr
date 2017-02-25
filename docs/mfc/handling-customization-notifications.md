---
title: "Gestion des notifications de personnalisation | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "TBN_CUSTHELP"
  - "TBN_QUERYINSERT"
  - "TBNOTIFY"
  - "NMHDR"
  - "TBN_TOOLBARCHANGE"
  - "TBN_ENDDRAG"
  - "NM_SETFOCUS"
  - "TBN_RESET"
  - "NM_RETURN"
  - "NM_ENDWAIT"
  - "NM_STARTWAIT"
  - "TBN_BEGINDRAG"
  - "NM_OUTOFMEMORY"
  - "TBN_QUERYDELETE"
  - "NM_DBLCLK"
  - "TBN_ENDADJUST"
  - "NM_KILLFOCUS"
  - "NM_RCLICK"
  - "TBN_BEGINADJUST"
  - "NM_CLICK"
  - "NM_RDBLCLK::"
  - "TBN_GETBUTTONINFO"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "TBN_ENDADJUST (notification)"
  - "TBNOTIFY (notification)"
  - "TBN_BEGINDRAG (notification)"
  - "TBN_TOOLBARCHANGE (notification)"
  - "NM_CLICK (notification)"
  - "NM_RETURN (notification)"
  - "NM_RCLICK (notification)"
  - "TBN_ENDDRAG (notification)"
  - "TBN_BEGINADJUST (notification)"
  - "NM_ENDWAIT (notification)"
  - "NM_KILLFOCUS (notification)"
  - "NM_SETFOCUS (notification)"
  - "NM_OUTOFMEMORY (notification)"
  - "TBN_QUERYINSERT (notification)"
  - "NMHDR"
  - "NM_STARTWAIT (notification)"
  - "CToolBarCtrl (classe), traiter les notifications"
  - "TBN_CUSTHELP (notification)"
  - "TBN_RESET (notification)"
  - "NM_DBLCLK (notification)"
  - "TBN_QUERYDELETE (notification)"
  - "NM_RDBLCLK (notification)"
  - "TBN_GETBUTTONINFO (notification)"
ms.assetid: 219ea08e-7515-4b98-85cb-47120f08c0a2
caps.latest.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Gestion des notifications de personnalisation
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un contrôle commun de barre d’outils Windows a des fonctionnalités de personnalisation intégrées, notamment une boîte de dialogue de personnalisation définie par le système, qui permettent à l’utilisateur d’insérer, de supprimer ou de réorganiser les boutons de barre d’outils. L’application détermine si les fonctionnalités de personnalisation sont disponibles et contrôle l’étendue selon laquelle l’utilisateur peut personnaliser la barre d’outils.  
  
 Vous pouvez rendre ces fonctionnalités de personnalisation disponible pour l’utilisateur en donnant à la barre d’outils le style `CCS_ADJUSTABLE`. Les fonctionnalités de personnalisation permettent à l’utilisateur de faire glisser un bouton à un nouvel emplacement ou de supprimer un bouton en le faisant glisser en dehors de la barre d’outils. En outre, l’utilisateur peut double\-cliquer sur la barre d’outils pour afficher la boîte de dialogue **Personnaliser la barre d’outils**, qui lui permet d’ajouter, de supprimer et de réorganiser les boutons de barre d’outils. L’application peut afficher la boîte de dialogue en utilisant la fonction membre [Customize](../Topic/CToolBarCtrl::Customize.md).  
  
 Le contrôle de barre d’outils envoie des messages de notification à la fenêtre parente à chaque étape du processus de personnalisation. Si l’utilisateur maintient enfoncée la touche Maj et commence à faire glisser un bouton, la barre d’outils gère automatiquement l’opération glisser. La barre d’outils envoie le message de notification **TBN\_QUERYDELETE** à la fenêtre parente pour déterminer si le bouton peut être supprimé. L’opération glisser se termine si la fenêtre parente retourne **FALSE**. Dans le cas contraire, la barre d’outils capture l’entrée de la souris et attend que l’utilisateur relâche le bouton de la souris.  
  
 Quand l’utilisateur relâche le bouton de la souris, le contrôle de barre d’outils détermine l’emplacement du curseur de la souris. Si le curseur se trouve en dehors de la barre d’outils, le bouton est supprimé. Si le curseur se trouve sur un autre bouton de barre d’outils, la barre d’outils envoie le message de notification **TBN\_QUERYINSERT** à la fenêtre parente pour déterminer si un bouton peut être inséré à gauche du bouton concerné. Le bouton est inséré si la fenêtre parente retourne **TRUE** ; sinon, il n’est pas inséré. La barre d’outils envoie le message de notification **TBN\_TOOLBARCHANGE** pour signaler la fin de l’opération glisser.  
  
 Si l’utilisateur commence une opération glisser sans maintenir la touche Maj enfoncée, le contrôle de barre d’outils envoie le message de notification **TBN\_BEGINDRAG** à la fenêtre propriétaire. Une application qui implémente son propre code de déplacement des boutons peut utiliser ce message comme signal pour commencer une opération glisser. La barre d’outils envoie le message de notification **TBN\_ENDDRAG** pour signaler la fin de l’opération glisser.  
  
 Un contrôle de barre d’outils envoie des messages de notification quand l’utilisateur personnalise une barre d’outils en utilisant la boîte de dialogue **Personnaliser la barre d’outils**. La barre d’outils envoie le message de notification **TBN\_BEGINADJUST** une fois que l’utilisateur a double\-cliqué sur la barre d’outils, mais avant la création de la boîte de dialogue. Ensuite, la barre d’outils commence à envoyer une série de messages de notification **TBN\_QUERYINSERT** pour déterminer si la barre d’outils autorise l’insertion de boutons. Quand la fenêtre parente retourne **TRUE**, la barre d’outils cesse d’envoyer des messages de notification **TBN\_QUERYINSERT**. Si la fenêtre parente ne retourne pas **TRUE** pour un bouton, la barre d’outils détruit la boîte de dialogue.  
  
 Ensuite, le contrôle de barre d’outils détermine si des boutons peuvent être supprimés de la barre d’outils en envoyant un message de notification **TBN\_QUERYDELETE** pour chaque bouton de la barre d’outils. La fenêtre parente retourne **TRUE** pour indiquer qu’un bouton peut être supprimé ; sinon, elle retourne **FALSE**. La barre d’outils ajoute tous les boutons de barre d’outils à la boîte de dialogue, mais affiche en grisé ceux qui ne peuvent pas être supprimés.  
  
 Chaque fois que le contrôle de barre d’outils a besoin d’informations sur un bouton dans la boîte de dialogue Personnaliser la barre d’outils, il envoie le message de notification **TBN\_GETBUTTONINFO**, en spécifiant l’index du bouton pour lequel il a besoin d’informations et l’adresse d’une structure **TBNOTIFY**. La fenêtre parente doit remplir la structure avec les informations appropriées.  
  
 La boîte de dialogue **Personnaliser la barre d’outils** comprend un bouton Aide et un bouton Réinitialiser. Quand l’utilisateur choisit le bouton Aide, le contrôle de barre d’outils envoie le message de notification **TBN\_CUSTHELP**. La fenêtre parente doit répondre en affichant des informations d’aide. La boîte de dialogue envoie le message de notification **TBN\_RESET** quand l’utilisateur sélectionne le bouton Réinitialiser. Ce message signale que la barre d’outils va réinitialiser la boîte de dialogue.  
  
 Ces messages sont tous des messages **WM\_NOTIFY**, et ils peuvent être gérés dans votre fenêtre propriétaire en ajoutant des entrées de table des messages sous la forme suivante à la table des messages de votre fenêtre propriétaire :  
  
 `ON_NOTIFY( wNotifyCode, idControl, memberFxn )`  
  
 `wNotifyCode`  
 Code identificateur du message de notification, comme **TBN\_BEGINADJUST**.  
  
 `idControl`  
 L’identificateur du contrôle qui envoie la notification.  
  
 `memberFxn`  
 La fonction membre à appeler quand cette notification est reçue.  
  
 Votre fonction membre doit être déclarée avec le prototype suivant :  
  
 `afx_msg void memberFxn( NMHDR * pNotifyStruct, LRESULT * result );`  
  
 Si le gestionnaire de messages de notification retourne une valeur, elle doit être placée dans le **LRESULT** vers lequel pointe *result*.  
  
 Pour chaque message, `pNotifyStruct` pointe vers une structure **NMHDR** ou vers une structure **TBNOTIFY**. Ces structures sont décrites ci\-dessous :  
  
 La structure **NMHDR** contient les membres suivants :  
  
 `typedef struct tagNMHDR {`  
  
 `HWND hwndFrom;  // handle of control sending message`  
  
 `UINT idFrom;// identifier of control sending message`  
  
 `UINT code;  // notification code; see below`  
  
 `} NMHDR;`  
  
 **hwndFrom**  
 Handle de fenêtre du contrôle qui envoie la notification. Pour convertir ce handle en un pointeur `CWnd`, utilisez [CWnd::FromHandle](../Topic/CWnd::FromHandle.md).  
  
 **idFrom**  
 Identificateur du contrôle qui envoie la notification.  
  
 **code**  
 Code de la notification. Ce membre peut être une valeur spécifique à un type de contrôle, comme **TBN\_BEGINADJUST** ou **TTN\_NEEDTEXT**, ou il peut être une des valeurs de notification courantes répertoriées ci\-dessous :  
  
-   **NM\_CLICK** L’utilisateur a cliqué dans le contrôle avec le bouton gauche de la souris.  
  
-   **NM\_DBLCLK** L’utilisateur a double\-cliqué dans le contrôle avec le bouton gauche de la souris.  
  
-   **NM\_KILLFOCUS** Le contrôle n’a plus le focus d’entrée.  
  
-   **NM\_OUTOFMEMORY** Le contrôle n’a pas pu terminer une opération, car la mémoire disponible n’est pas suffisante.  
  
-   **NM\_RCLICK** L’utilisateur a cliqué dans le contrôle avec le bouton droit de la souris.  
  
-   **NM\_RDBLCLK** L’utilisateur a double\-cliqué dans le contrôle avec le bouton droit de la souris.  
  
-   **NM\_RETURN** Le contrôle a le focus d’entrée et l’utilisateur a appuyé sur la touche Entrée.  
  
-   **NM\_SETFOCUS** Le contrôle a reçu le focus d’entrée.  
  
 La structure **TBNOTIFY** contient les membres suivants :  
  
 `typedef struct {`  
  
 `NMHDR hdr; // information common to all WM_NOTIFY messages`  
  
 `int iItem; // index of button associated with notification`  
  
 `TBBUTTON tbButton; // info about button associated withnotification`  
  
 `int cchText;   // count of characters in button text`  
  
 `LPSTR lpszText;// address of button text`  
  
 `} TBNOTIFY, FAR* LPTBNOTIFY;`  
  
## Notes  
 **hdr**  
 Informations communes à tous les messages **WM\_NOTIFY**.  
  
 **iItem**  
 Index du bouton associé à la notification.  
  
 **tbButton**  
 Structure `TBBUTTON` qui contient des informations sur le bouton de barre d’outils associé à la notification.  
  
 **cchText**  
 Nombre de caractères dans le texte du bouton.  
  
 **lpszText**  
 Pointeur vers le texte du bouton.  
  
 Les notifications envoyées par la barre d’outils sont les suivantes :  
  
-   **TBN\_BEGINADJUST** Envoyée quand l’utilisateur commence la personnalisation d’un contrôle de barre d’outils. Le pointeur pointe vers une structure **NMHDR** qui contient des informations sur la notification. Le gestionnaire ne doit retourner aucune valeur spécifique.  
  
-   **TBN\_BEGINDRAG** Envoyé quand l’utilisateur commence à faire glisser un bouton dans un contrôle de barre d’outils. Le pointeur pointe vers une structure **TBNOTIFY**. Le membre **iItem** contient l’index de base zéro du bouton qui est glissé. Le gestionnaire ne doit retourner aucune valeur spécifique.  
  
-   **TBN\_CUSTHELP** Envoyé quand l’utilisateur clique sur le bouton Aide dans la boîte de dialogue Personnaliser la barre d’outils. Pas de valeur de retour. Le pointeur pointe vers une structure **NMHDR** qui contient des informations sur le message de notification. Le gestionnaire ne doit retourner aucune valeur spécifique.  
  
-   **TBN\_ENDADJUST** Envoyé quand l’utilisateur arrête la personnalisation d’un contrôle de barre d’outils. Le pointeur pointe vers une structure **NMHDR** qui contient des informations sur le message de notification. Le gestionnaire ne doit retourner aucune valeur spécifique.  
  
-   **TBN\_ENDDRAG** Envoyé quand l’utilisateur arrête de faire glisser un bouton dans un contrôle de barre d’outils. Le pointeur pointe vers une structure **TBNOTIFY**. Le membre **iItem** contient l’index de base zéro du bouton qui est glissé. Le gestionnaire ne doit retourner aucune valeur spécifique.  
  
-   **TBN\_GETBUTTONINFO** Envoyé quand l’utilisateur personnalise un contrôle de barre d’outils. La barre d’outils utilise ce message de notification pour extraire les informations nécessaires à la boîte de dialogue Personnaliser la barre d’outils. Le pointeur pointe vers une structure **TBNOTIFY**. Le membre **iItem** membre spécifie l’index de base zéro d’un bouton. Les membres **pszText** et **cchText** spécifient l’adresse et la longueur en caractères du texte du bouton. Une application doit remplir la structure avec des informations sur le bouton. Retourne **TRUE** si les informations sur le bouton ont été copiées vers la structure ; sinon, **FALSE**.  
  
-   **TBN\_QUERYDELETE** Envoyé quand l’utilisateur personnalise une barre d’outils pour déterminer si un bouton peut être supprimé d’un contrôle de barre d’outils. Le pointeur pointe vers une structure **TBNOTIFY**. Le membre **iItem** contient l’index de base zéro du bouton à supprimer. Retourne **TRUE** pour autoriser la suppression du bouton ou **FALSE** pour empêcher la suppression du bouton.  
  
-   **TBN\_QUERYINSERT** Envoyé quand l’utilisateur personnalise un contrôle de barre d’outils pour déterminer si un bouton peut être inséré à gauche du bouton concerné. Le pointeur pointe vers une structure **TBNOTIFY**. Le membre **iItem** contient l’index de base zéro du bouton à insérer. Retourne **TRUE** pour autoriser l’insertion d’un bouton devant le bouton concerné, ou **FALSE** pour empêcher l’insertion du bouton.  
  
-   **TBN\_RESET** Envoyé quand l’utilisateur réinitialise le contenu de la boîte de dialogue Personnaliser la barre d’outils. Le pointeur pointe vers une structure **NMHDR** qui contient des informations sur le message de notification. Le gestionnaire ne doit retourner aucune valeur spécifique.  
  
-   **TBN\_TOOLBARCHANGE** Envoyé après que l’utilisateur a personnalisé un contrôle de barre d’outils. Le pointeur pointe vers une structure **NMHDR** qui contient des informations sur le message de notification. Le gestionnaire ne doit retourner aucune valeur spécifique.  
  
## Voir aussi  
 [Utilisation de CToolBarCtrl](../mfc/using-ctoolbarctrl.md)   
 [Contrôles](../mfc/controls-mfc.md)