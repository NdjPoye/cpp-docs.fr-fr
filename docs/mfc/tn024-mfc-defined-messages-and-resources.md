---
title: "TN024&#160;: messages et ressources d&#233;finis par MFC | Microsoft Docs"
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
  - "vc.mfc.messages"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "messages (C++), MFC"
  - "ressources (MFC)"
  - "TN024"
  - "messages Windows (C++), définis par MFC"
ms.assetid: c65353ce-8096-454b-ad22-1a7a1dd9a788
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN024&#160;: messages et ressources d&#233;finis par MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

> [!NOTE]
>  La note technique suivante n'a pas été mise à jour depuis son inclusion initiale dans la documentation en ligne.  Par conséquent, certaines procédures et rubriques peuvent être obsolètes ou incorrectes.  Pour obtenir les informations les plus récentes, il est recommandé de rechercher l'objet qui vous intéresse dans l'index de la documentation en ligne.  
  
 Cette remarque décrit les messages internes de Windows et fournit les formats utilisés par MFC.  Ces informations expliquent l'implémentation de l'environnement de travail, et vous aideront à déboguer votre application.  Pour les audacieux, même si toutes ces informations sont officiellement non prises en charge, vous pouvez utiliser certaines de ces informations pour les implémentations avancées.  
  
 Cette remarque contient les détails d'implémentation privés de MFC ; tout le contenu est soumis à une modification dans le futur.  Les messages privés Windows de MFC ont un sens dans l'étendue d'une application seulement mais changeront à l'avenir pour contenir les messages au niveau du système.  
  
 La chaîne des messages privés Windows de MFC et les types de ressources sont dans la plage réservée « sys » mise de côté par Microsoft Windows.  Actuellement tous les nombres dans les plages ne sont pas utilisés et, ultérieurement, les nouveaux nombres dans la plage pourront être utilisés.  Les nombres utilisés actuellement peuvent être modifiés.  
  
 Les messages privés Windows de MFC sont dans la plage 0x360\-0x37F\>.  
  
 Les types de ressources privés de MFC sont dans la plage 0xF0\-0xFF\>.  
  
 **Messages privés Windows de MFC**  
  
 Ces messages Windows sont utilisés à la place des fonctions virtuelles C\+\+ où le relativement faible couplage est requis entre les objets window et où la fonction virtuelle du actuel C\+\+ n'est pas appropriée.  
  
 Ces messages privés Windows et structures associées de paramètres sont déclarés dans l'en\-tête privé « AFXPRIV.H » MFC.  Soyez prévenu qu'un de vos codes qui contient l'en\-tête peut s'appuyer sur le comportement non documenté et sera probablement enlevé dans les versions ultérieures de MFC.  
  
 Dans le cas, très peu fréquent, de traiter un de ces messages, vous devriez utiliser la table macro des messages `ON_MESSAGE` et traiter le message au format générique LRESULT\/WPARAM\/LPARAM.  
  
 **WM\_QUERYAFXWNDPROC**  
  
 Le message est envoyé dans une fenêtre qui est créée.  Cela est envoyé très tôt dans le processus de conception en tant que méthode pour déterminer si le WndProc est **AfxWndProc.AfxWndProc** retourne 1.  
  
|||  
|-|-|  
|wParam|Non utilisé|  
|lParam|Non utilisé|  
|retourne|1 si traité par **AfxWndProc**|  
  
 **WM\_SIZEPARENT**  
  
 Le message est envoyé par une fenêtre cadre à ses enfants immédiats au redimensionnement \(**CFrameWnd::OnSize** appelle `CFrameWnd::RecalcLayout` qui appelle `CWnd::RepositionBars`\) pour repositionner les barres de contrôle autour du côté du cadre.  La structure **AFX\_SIZEPARENTPARAMS** contient le rectangle client disponible actuellement du parent et un HDWP \(qui peut être NUL\) lequel va appeler `DeferWindowPos` pour minimiser la repeinte .  
  
|||  
|-|-|  
|wParam|Non utilisé|  
|lParam|Adresse d'une structure **AFX\_SIZEPARENTPARAMS**|  
|retourne «  »|Non utilisé \(0\)|  
  
 Ignorer le message indique que la fenêtre ne participe pas à la mise en page.  
  
 **WM\_SETMESSAGESTRING**  
  
 Le message est envoyé dans une fenêtre cadre pour lui demander de mettre à jour la ligne du message dans la barre d'état.  Un ID de chaîne ou un LPCSTR peut être spécifié \(mais pas les deux\).  
  
|||  
|-|-|  
|wParam|ID de type chaîne \(ou zéro\)|  
|lParam|LPCSTR de chaîne \(ou NULL\)|  
|retourne «  »|Non utilisé \(0\)|  
  
 **WM\_IDLEUPDATECMDUI**  
  
 Ce message est envoyé pendant une durée d'inactivité pour implémenter une mise à jour des gestionnaires de commande à l'interface utilisateur des temps d'inactivités.  Si la fenêtre \(en général une barre de contrôle\) traite le message, elle crée un objet `CCmdUI` \(ou un objet d'une classe dérivée\) et appelle **CCmdUI::DoUpdate** pour chacun des "éléments" dans la fenêtre.  Il vérifie ensuite un gestionnaire `ON_UPDATE_COMMAND_UI` pour les objets dans la chaîne du gestionnaire de commandes.  
  
|||  
|-|-|  
|wParam|BDisableIfNoHandler de BOOL|  
|lParam|Non utilisé \(0\)|  
|retourne «  »|Non utilisé \(0\)|  
  
 *le bDisableIfNoHandler* est différent de zéro pour désactiver l'objet d'interface s'il n'existe aucun `ON_UPDATE_COMMAND_UI` ni un gestionnaire `ON_COMMAND`.  
  
 **WM\_EXITHELPMODE**  
  
 Ce message est publié sur `CFrameWnd` qui pour quitter contextualise le mode d'aide sensible.  Réception de ce message termine la boucle modale démarrée par **CFrameWnd::OnContextHelp.**  
  
|||  
|-|-|  
|wParam|Non utilisé \(0\)|  
|lParam|Non utilisé \(0\)|  
|retourne «  »|Non utilisé|  
  
 **WM\_INITIALUPDATE**  
  
 Le message est envoyé par le modèle de document à tous les descendants d'une fenêtre cadre lorsqu'il est sans risque pour eux de faire leur mise à jour d'origine.  Il est mappé à un appel à `CView::OnInitialUpdate` mais peut être utilisé dans les autres `CWnd`\- classes dérivées pour une mise à jour unique.  
  
|||  
|-|-|  
|wParam|Non utilisé \(0\)|  
|lParam|Non utilisé \(0\)|  
|retourne «  »|Non utilisé \(0\)|  
  
 **WM\_RECALCPARENT**  
  
 Le message est envoyé par une vue à la fenêtre parente \(obtenue via `GetParent`\) pour forcer un recalcul de disposition \(en général, le parent appelle `RecalcLayout`\).  Utilisé dans OLE applications serveur où il est nécessaire que le cadre s'étende de taille lorsque la taille totale de la vue grandit.  
  
 Si la fenêtre parente traite ce message elle doit retourner TRUE et remplir RECT passée dans le lParam avec le nouvelle taille de la zone client.  Utilisé dans `CScrollView` pour gérer correctement les barres de défilement \(place ensuite à l'extérieur de la fenêtre lorsqu'ils sont ajoutés\) lorsqu'un objet serveur est activé sur place.  
  
|||  
|-|-|  
|wParam|Non utilisé \(0\)|  
|lParam|LPRECT rectClient, peut avoir la valeur NULL|  
|retourne «  »|TRUE si le nouveau rectangle client est retourné, sinon FALSE|  
  
 **WM\_SIZECHILD**  
  
 Ce message est envoyé par `COleResizeBar` dans la fenêtre propriétaire \(via `GetOwner`\) lorsque l'utilisateur redimensionne la barre de redimensionnement avec les poignées de redimensionnement.  `COleIPFrameWnd` répond à ce message en tentant de repositionner la fenêtre cadre tel que l'utilisateur l'a demandé.  
  
 Le nouveau rectangle, fourni dans les coordonnées client par rapport à la fenêtre cadre qui contient la barre de redimensionnement, est référencé par le lParam.  
  
|||  
|-|-|  
|wParam|Non utilisé \(0\)|  
|lParam|RectNew de LPRECT|  
|retourne «  »|Non utilisé \(0\)|  
  
 **WM\_DISABLEMODAL**  
  
 Ce message est envoyé à toutes les fenêtres publicitaires intempestives détenues par une fenêtre cadre désactivée.  La fenêtre cadre utilise le résultat pour déterminer s'il faut ou non désactiver la fenêtre pop\-up.  
  
 Vous pouvez l'utiliser pour effectuer un traitement spécial dans votre fenêtre pop\-up lorsque le cadre adopte un état modal ou pour empêcher certaines fenêtres publicitaires intempestives d'être désactivées.  Les info\-bulles utilisent ce message pour se détruire lorsque la fenêtre cadre entre dans un état modal, par exemple.  
  
|||  
|-|-|  
|wParam|Non utilisé \(0\)|  
|lParam|Non utilisé \(0\)|  
|retourne «  »|Différent de zéro de **NOT** désactive la fenêtre, 0 indique que la fenêtre sera désactivée|  
  
 **WM\_FLOATSTATUS**  
  
 Ce message est envoyé à toutes les fenêtres publicitaires intempestives détenues par une fenêtre cadre quand le cadre est activé ou désactivé par une autre fenêtre cadre de niveau supérieur.  Utilisé par l'implémentation de **MFS\_SYNCACTIVE** dans `CMiniFrameWnd`, pour conserver l'activation de ces fenêtres publicitaires intempestives synchronisée avec l'activation de la fenêtre cadre de niveau supérieur.  
  
|||  
|-|-|  
|wParam|C'est l'une des valeurs suivantes :<br /><br /> **FS\_SHOW**<br /><br /> **FS\_HIDE**<br /><br /> **FS\_ACTIVATE**<br /><br /> **FS\_DEACTIVATE**<br /><br /> **FS\_ENABLEFS\_DISABLE**<br /><br /> **FS\_SYNCACTIVE**|  
|lParam|Non utilisé \(0\)|  
  
 La valeur de retour doit être différente de zéro si **FS\_SYNCACTIVE** est défini et la fenêtre synchronise son activation avec le cadre parent.  `CMiniFrameWnd` retourne une valeur différente de zéro si le style est défini à **MFS\_SYNCACTIVE.**  
  
 Pour plus d'informations, consultez l'implémentation de `CMiniFrameWnd`.  
  
## WM\_ACTIVATETOPLEVEL  
 Ce message est envoyé dans une fenêtre de niveau supérieur quand une fenêtre dans son « groupe de haut niveau » est activée ou désactivée.  Une fenêtre fait partie d'un groupe de niveau supérieur s'il s'agit d'une fenêtre de niveau supérieur \(aucun parent ou propriétaire\), ou s'il appartient à une telle fenêtre.  Ce message est similaire en service à **WM\_ACTIVATEAPP,** mais les travaux dans les cas où les fenêtres appartenant à des processus différents sont combinées dans une hiérarchie de fenêtre unique \(courantes dans les applications OLE\).  
  
## WM\_COMMANDHELP, WM\_HELPHITTEST, WM\_EXITHELPMODE  
 Ces messages sont utilisés dans l'implémentation de l'aide contextuelle.  Rendez\-vous sur [Note technique 28](../mfc/tn028-context-sensitive-help-support.md) pour plus d'informations.  
  
## Formats privés de ressource MFC  
 Actuellement, MFC définit deux formats privés de ressources : **RT\_TOOLBAR** et **RT\_DLGINIT**.  
  
## Format de ressource RT\_TOOLBAR  
 La barre d'outils par défaut fournie par AppWizard est basée sur une ressource personnalisée en **RT\_TOOLBAR**, introduite dans MFC 4,0.  Vous pouvez modifier cette ressource grâce à l'Éditeur de barres d'outils.  
  
## Format de ressource RT\_DLGINIT  
 Un format privé de ressource MFC est utilisé pour stocker les informations supplémentaires d'initialisation de dialogue.  Cela inclut les chaînes initiales stockées dans une zone de liste déroulante.  Le format de cette ressource n'est pas conçu pour être modifié manuellement, mais est géré par Visual C\+\+.  
  
 Visual C\+\+ et cette ressource **RT\_DLGINIT** ne sont pas requis pour utiliser les fonctionnalités associées de MFC comme il existe une autre API pour utiliser les informations de la ressource.  Visual C\+\+ simplifie beaucoup pour écrire, gérer, et traduire l'application à long terme.  
  
 La structure de base d'une ressource **RT\_DLGINIT** est la suivante :  
  
```  
+---------------+                    \  
| Control ID    |   UINT             |  
+---------------+                    |  
| Message #     |   UINT             |  
+---------------+                    |  
|length of data |   DWORD            |  
+---------------+                    |   Repeated  
|   Data        |   Variable Length  |   for each control  
|   ...         |   and Format       |   and message  
+---------------+                    /  
|     0         |   BYTE  
+---------------+  
```  
  
 Une section répétée contient l'ID de contrôle pour envoyer le message à, le message \# pour envoyer \( un message windows normal\) et une de longueur variable de données.  Le message Windows est envoyé en un formulaire :  
  
```  
SendDlgItemMessage(<Control ID>, <Message #>, 0, &<Data>);  
```  
  
 C'est très un format très standard, autorisant tous les messages Windows et le contenu de données.  L'éditeur de ressources et Visual C\+\+ MFC prennent en charge uniquement un sous\-ensemble limité de messages windows : CB\_ADDSTRING pour les liste\- choix initiaux pour les zones de liste déroulante \(les données sont une chaîne de caractères\).  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)