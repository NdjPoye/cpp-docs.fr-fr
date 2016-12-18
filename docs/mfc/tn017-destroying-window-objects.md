---
title: "TN017&#160;: destruction d&#39;objets fen&#234;tres | Microsoft Docs"
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
  - "vc.objects"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "détruire des fenêtres"
  - "PostNcDestroy (méthode)"
  - "TN017"
ms.assetid: 5bf208a5-5683-439b-92a1-547c5ded26cd
caps.latest.revision: 15
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# TN017&#160;: destruction d&#39;objets fen&#234;tres
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit l'utilisation de la méthode [CWnd::PostNcDestroy](../Topic/CWnd::PostNcDestroy.md).  Utilisez cette méthode si vous souhaitez que l'allocation personnalisée de `CWnd`\- objets dérivés.  Cette remarque explique aussi pourquoi vous devez utiliser [CWnd::DestroyWindow](../Topic/CWnd::DestroyWindow.md) pour détruire un objet Windows C\+\+ au lieu de l'opérateur `delete`.  
  
 Si vous suivez les instructions de cette rubrique, vous aurez pas de problèmes de nettoyage.  Ces problèmes peuvent provenir des problèmes tels que oublier de suppression\/mémoire libre C\+\+, oublier de libérer des ressources système telles que `HWND`s, soit libérer des objets nombre de fois.  
  
## Le problème  
 Chaque objet windows \(objet d'une classe dérivée de `CWnd`\) représente à la fois l'objet du actuel \+\+ c et `HWND`.  Les objets C\+\+ sont alloués dans le segment d'application et `HWND`s sont alloués dans les ressources système par le gestionnaire de windows.  Comme il existe plusieurs façons de détruire objet window, nous devons spécifier un ensemble de règles qui empêchent la ressource système ou des fuites de mémoire.  Ces règles doit également empêcher les objets et les descripteurs de fenêtres d'être détruit plusieurs fois.  
  
## Destruction des fenêtres  
 Voici les deux méthodes autorisées pour détruire un objet windows :  
  
-   Appeler `CWnd::DestroyWindow` ou l'API Windows `DestroyWindow`.  
  
-   Supprimez explicitement avec l'opérateur `delete`.  
  
 Le premier cas est de loin le plus courant.  Cette option s'applique même si le code n'appelle pas `DestroyWindow` directement.  Lorsque l'utilisateur ferme directement une fenêtre frame, cette action crée le message `WM_CLOSE`, et la réponse par défaut à ce message consiste à appeler `DestroyWindow.` lorsqu'une fenêtre parente est détruit, il appelle `DestroyWindow` de tous ses enfants.  
  
 Le deuxième cas, l'utilisation de l'opérateur `delete` sur des objets Windows, doit être rare.  Voici quelques cas où l'utilisation de `delete` est le bon choix.  
  
## Nettoyage automatique avec CWnd::PostNcDestroy  
 Lorsque le système détruit une fenêtre windows, le dernier message windows envoyé à la fenêtre est `WM_NCDESTROY`.  Le gestionnaire par défaut `CWnd` du message est [CWnd::OnNcDestroy](../Topic/CWnd::OnNcDestroy.md).  `OnNcDestroy` détachera `HWND` de l'objet C\+\+ et appelle la fonction virtuelle `PostNcDestroy`.  Certaines classes remplacent cette fonction pour supprimer l'objet C\+\+.  
  
 L'implémentation par défaut de `CWnd::PostNcDestroy` n'a aucun effet, ce qui concerne les objets window qui sont alloués sur le frame de pile ou incorporés dans d'autres objets.  Ce n'est pas pertinent pour les objets window conçus pour être alloués sur le segment sans autre objet.  En d'autres termes, il n'est pas pertinente pour les objets window qui ne sont pas incorporés dans d'autres objets C\+\+.  
  
 Ces classes conçues pour être allouées seules sur la substitution de segment la méthode `PostNcDestroy` pour effectuer `delete this`.  Cette instruction libèrera toute mémoire associée à l'objet C\+\+.  Bien que le destructeur de `CWnd` par défaut appelle `DestroyWindow` si `m_hWnd` est non NULL, cela n'entraîne pas la récurrence infinie car le descripteur est détaché et NULL pendant la phase de nettoyage.  
  
> [!NOTE]
>  Le système appelle habituellement `CWnd::PostNcDestroy` lorsqu'il traite le message `WM_NCDESTROY` windows et `HWND` et l'objet fenêtre C\+\+ ne sont plus connectés.  Le système appelle également `CWnd::PostNcDestroy` dans l'implémentation de la plupart des appels de [CWnd::Create](../Topic/CWnd::Create.md) si l'erreur se produit.  Les règles automatiques de nettoyage sont décrites plus loin dans cette rubrique.  
  
## Classes de nettoyage automatique  
 Les classes suivantes ne sont pas conçues pour l'autoparamétrage CLEANUP.  Ils sont généralement intégrées dans d'autres objets C\+\+ ou de la pile :  
  
-   Tous les contrôles Windows standard \(`CStatic`, `CEdit`, `CListBox`, etc.\).  
  
-   Les fenêtres enfants dérivées directement à partir de `CWnd` \(par exemple, contrôles personnalisés.\)  
  
-   Fractionner des fenêtres \(`CSplitterWnd`\).  
  
-   Barres de contrôle par défaut \(les classes dérivées `CControlBar`, consultez [Note technique 31](../mfc/tn031-control-bars.md) pour activer la suppression automatique des objets de la barre de contrôle\).  
  
-   Conversations \(`CDialog`\) conçu pour les boîtes de dialogue modales sur le frame de pile.  
  
-   Tous les dialogues standard sauf `CFindReplaceDialog`.  
  
-   Les dialogues par défaut créés par ClassWizard.  
  
 Les classes suivantes sont conçues pour l'autoparamétrage CLEANUP.  Ils sont généralement alloués directement sur le segment :  
  
-   Fenêtres cadres clés \(dérivées directement ou indirectement de `CFrameWnd`\).  
  
-   Fenêtres d'affichage \(dérivées directement ou indirectement de `CView`\).  
  
 Si vous souhaitez arrêter ces règles, vous devez substituer la méthode `PostNcDestroy` dans la classe dérivée.  Pour ajouter l'autoparamétrage CLEANUP à votre classe, appelez votre classe de base et faites `delete this`.  Pour supprimer l'autoparamétrage CLEANUP de votre classe, appelez `CWnd::PostNcDestroy` directement à la place de la méthode `PostNcDestroy` de la classe de base directe.  
  
 L'utilisation la plus courante pour modifier le comportement automatique de nettoyage consiste à créer une boîte de dialogue non modal qui peut être allouée sur le segment.  
  
## Lorsqu'il faut appeler supprimer  
 Nous recommandons que vous appelez `DestroyWindow` à détruire objet windows, la méthode C\+\+ ou l'API globale `DestroyWindow`.  
  
 N'appelez pas l'API globale `DestroyWindow` à détruire une fenêtre enfant MDI.  Vous devez utiliser à la place la méthode virtuelle `CWnd::DestroyWindow`.  
  
 Pour les objets window C\+\+ qui n'effectuent pas automatiquement CLEANUP, l'opérateur `delete` peut entraîner une fuite de mémoire lorsque vous essayez d'appeler `DestroyWindow` dans le destructeur de `CWnd::~CWnd` si le VTBL n'indique pas correctement la classe dérivée.  Cela se produit parce que le système ne trouve pas le approprié détruisent la méthode à appeler.  Utilisation `DestroyWindow` au lieu de `delete` éviter ces problèmes.  Comme il peut s'agir d'une erreur subtile, la compilation en mode débogage génère l'erreur suivante si vous êtes menacée.  
  
```  
Warning: calling DestroyWindow in CWnd::~CWnd  
   OnDestroy or PostNcDestroy in derived class will not be called  
```  
  
 Dans le cas des objets windows C\+\+ qui effectuent l'autoparamétrage CLEANUP, vous devez appeler `DestroyWindow`.  Si vous utilisez l'opérateur `delete` directement, l'allocateur de mémoire et de MFC vous informera que vous relâchez la mémoire deux fois.  Les deux occurrences sont votre premier appel explicite et l'appel indirect à `delete this` dans l'implémentation d'autoparamétrage CLEANUP `PostNcDestroy`.  
  
 Après avoir appelé `DestroyWindow` sur un objet de non\-AUTO\- CLEANUP, l'objet C\+\+ sera toujours ce problème, mais `m_hWnd` sera NULL.  Après avoir appelé `DestroyWindow` sur un objet d'autoparamétrage CLEANUP, l'objet C\+\+ est allé, libéré par l'opérateur C\+\+ dans l'implémentation d'autoparamétrage CLEANUP `PostNcDestroy`.  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)