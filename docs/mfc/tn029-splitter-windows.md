---
title: "TN029&#160;: fen&#234;tres fractionn&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.windows.splitter"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "fenêtres fractionnées, à propos des fenêtres fractionnées"
  - "TN029"
ms.assetid: 2c57ce99-2a3c-4eff-9cea-baccb13af075
caps.latest.revision: 18
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 14
---
# TN029&#160;: fen&#234;tres fractionn&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cette remarque décrit MFC [CSplitterWnd Class](../mfc/reference/csplitterwnd-class.md), qui fournit des fractionnements de fenêtre et gère le redimensionnement d'autres fenêtres du volet.  
  
## Styles de séparateur  
 Un `CSplitterWnd` prend en charge deux styles différents de fractionnement de fenêtres.  
  
 Dans la section des "séparateurs statiques", la fenêtre de fractionnement crée les volets lors de sa création.  L'ordre et le nombre des volets ne changent jamais.  Les barres de division sont utilisées pour redimensionner les différents volets.  Vous pouvez utiliser ce style pour afficher une classe d'affichage différente dans chaque volet.  L'éditeur graphique Visual C\+\+ et le gestionnaire de fichiers windows sont des exemples de programmes qui utilisent ce style de séparateur.  Ce style de la fenêtre de fractionnement n'utilise pas les zones de séparateur.  
  
 Dans « fractionneurs dynamiques » , des volets supplémentaires sont créés et détruits lorsque l'utilisateur fractionne et rassemble des affichages nouveaux.  Cette séparation commence par une vue et fournit des zones de séparateur de l'utilisateur à fractionner ouverture.  La fenêtre de fractionnement crée dynamiquement un objet de la vue lorsque la vue est fractionné dans une direction.  Ce nouvel objet de vue représente le nouveau volet.  Si la vue est fractionnée en deux instructions à l'aide de l'interface du clavier, la fenêtre de fractionnement crée trois nouveaux objets de vue des trois nouveaux volets.  Lorsque le fractionnement est actif, la fenêtre affiche la zone de séparateur sous la barre de fractionnement entre les volets.  Windows détruit les afficher des objets supplémentaires lorsque l'utilisateur supprime une division, mais la vue d'origine est conservée tant que la fenêtre de fractionnement est elle\-même détruite.  Microsoft Excel et Microsoft Word sont des exemples d'applications qui utilisent le style d'affichage de fractionnement.  
  
 Lorsque vous créez l'un ou l'autre de type du point de fractionnement, vous devez spécifier le nombre maximal de lignes et de colonnes que le séparateur gère.  Un séparateur statique crée des volets pour remplir toutes les lignes et colonnes.  Un point de fractionnement va créer uniquement le premier volet lorsque `CSplitterWnd` est créé.  
  
 Le nombre maximal des volets que vous pouvez spécifier des séparateurs statiques est 16 lignes par 16 colonnes.  Les configurations recommandées sont :  
  
-   1 ligne x 2 colonnes : généralement avec les différents volets  
  
-   2 lignes x 1 colonne : généralement avec les différents volets  
  
-   2 lignes X 2 colonnes : généralement avec les volets similaires  
  
 Le nombre maximal des volets que vous pouvez spécifier pour windows fractionnement est 2 lignes par 2 colonnes.  Les configurations recommandées sont :  
  
-   ligne 1 X 2 colonnes : pour des données en colonnes  
  
-   2 X 1 lignes colonne : pour les données textuelles ou autres  
  
-   2 lignes X 2 colonnes : pour la grille ou la table données orientées  
  
## Exemples de séparateur  
 Plusieurs fenêtres fractionnement d'exemples utilisent de MFC directement ou indirectement.  L'exemple général [VIEWEX](../top/visual-cpp-samples.md) de MFC illustre plusieurs utilise des séparateurs statiques, notamment le mode de placement d'un serveur de distribution dans un serveur de distribution.  
  
 Vous pouvez également utiliser ClassWizard pour créer une classe enfant de la fenêtre cadre de \(MDI\) nouvelle interface MD qui contient une fenêtre de fractionnement.  Pour plus d'informations sur les fenêtres de fractionnement, consultez l' [Plusieurs types de document, vues, et fenêtres frames](../mfc/multiple-document-types-views-and-frame-windows.md).  
  
## Terminologie utilisée par implémentation  
 Voici une liste de termes qui sont propres à windows fractionnement :  
  
 `CSplitterWnd`:  
 Une fenêtre fournissant volet\- fractionner les contrôles et les barres de défilement partagés entre les volets dans une ligne ou colonne.  Vous spécifiez les lignes et les colonnes contenant des numérations de base \(le premier volet est ligne \= 0 et la colonne \= 0\).  
  
 Pane:  
 Un point spécifique à l'application d' `CSplitterWnd` gère.  Un volet est généralement un objet dérivé de [CView Class](../mfc/reference/cview-class.md), mais peut être n'importe quel objet d' [CWnd](../mfc/reference/cwnd-class.md) associé à l'ID appropriée de fenêtre enfant  
  
 Pour utiliser un `CWnd`\- objet dérivé, passez `RUNTIME_CLASS` de l'objet à la fonction d' `CreateView` comme si vous avez utilisé `CView`\- classe dérivée.  Votre classe doit utiliser `DECLARE_DYNCREATE` et `IMPLEMENT_DYNCREATE` car l'infrastructure utilise la création dynamique au moment de l'exécution.  Bien qu'il y a beaucoup de code dans `CSplitterWnd` spécifiques à la classe d' `CView`, [CObject::IsKindOf](../Topic/CObject::IsKindOf.md) est toujours utilisé avant que ces actions sont exécutées.  
  
 Barre de fractionnement :  
 Un contrôle qui se trouve entre les lignes et les colonnes des volets.  Il peut être utilisé pour ajuster la taille des lignes ou des colonnes des volets.  
  
 Zone de séparateur :  
 Un contrôle d' `CSplitterWnd` dynamique que vous pouvez utiliser pour créer de nouvelles lignes ou colonnes des volets.  Il se trouve en haut des barres de défilement verticale ou à gauche des barres de défilement horizontales.  
  
 Intersection de séparateur :  
 L'intersection d'une barre de fractionnement verticale et la barre de fractionnement horizontale.  Vous pouvez le faire glisser pour ajuster la taille d'une ligne et une colonne des volets simultanément.  
  
## Barres de défilement partagées  
 La classe d' `CSplitterWnd` prend également en charge les barres de défilement partagées.  Ces contrôles de la barre de défilement sont des enfants d' `CSplitterWnd` et sont partagées avec les différents volets du séparateur.  
  
 Par exemple, dans une ligne 1 X fenêtre de 2 colonnes, vous pouvez spécifier WS\_VSCROLL en créant `CSplitterWnd`.  Windows crée un contrôle de barre de défilement spécial qui est partagée entre les deux volets.  
  
```  
[      ][      ][^]  
[pane00][pane01][|]  
[      ][      ][v]  
```  
  
 Lorsque l'utilisateur est la barre de défilement, les messages d' `WM_VSCROLL` sont envoyés aux deux vues.  Si l'une ou l'autre de vue définit la position de barre de défilement, la barre de défilement partagée est définie.  
  
 Notez que les barres de défilement partagées sont les plus utiles avec les objets de vue similaires.  Si vous combinez des vues de types différents dans un séparateur, vous devrez peut\-être écrire un code spécial pour coordonner leurs positions de défilement.  Tout `CView`\- la classe dérivée qui utilise les API de barre de défilement d' `CWnd` la délèguera dans la barre de défilement partagée si elle existe.  L'implémentation d' `CScrollView` est un exemple d'une classe d' `CView` qui prend en charge les barres de défilement partagées.  Les classes qui ne sont pas dérivées d' `CView`, les classes qui reposent sur des barres de défilement non contrôle, les classes qui utilisent des implémentations standard windows \(par exemple, `CEditView`\) ne fonctionnent pas avec la fonctionnalité partagée de barre de défilement d' `CSplitterWnd`.  
  
## Tailles minimales  
 Pour chaque ligne il existe une hauteur de ligne minimale, et pour chaque colonne il existe une largeur de colonne minimales.  Cette valeur assure qu'un volet n'est pas trop petit pour être affiché dans le détail complet.  
  
 Pour un point de fractionnement statique, la hauteur de ligne et la largeur des colonnes initiales minimale est 0.  Pour un point de fractionnement dynamique, la hauteur de ligne et la largeur de colonne minimales initiales sont définies par le paramètre d' `sizeMin` de la fonction d' `CSplitterWnd::Create`.  
  
 Vous pouvez modifier les tailles minimales à l'aide de [CSplitterWnd::SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) et [CSplitterWnd::SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) s'exécute.  
  
## Tailles réelles vs tailles idéales  
 La disposition des volets dans la fenêtre de fractionnement dépend de la taille du cadre qui les contient.  Lorsqu'un utilisateur redimensionne le cadre conteneur, `CSplitterWnd` REPLACE et redimensionne le volet afin qu'elles s'ajustent ainsi que possible.  
  
 L'utilisateur peut définir manuellement la taille de la hauteur de ligne et de largeur de colonne, le programme peut définir la taille idéale à l'aide de la classe d' `CSplitterWnd`.  La taille réelle peut être inférieure ou supérieure à l'idéal.  Windows régleront la taille réelle s'il n'y a pas assez de place pour afficher la taille idéale ou génère trop d'espace vide à droite et en bas de la fenêtre de fractionnement.  
  
## Contrôles personnalisés  
 Vous pouvez remplacer de nombreuses fonctions pour fournir le comportement personnalisé et une interface personnalisée.  Vous pouvez remplacer ce premier jeu pour fournir d'autres images pour les différents composants graphiques d'un point de fractionnement.  
  
-   `virtual void OnDrawSpltter(CDC* pDC, ESplitType nType, const CRect& rect);`  
  
-   `virtual void OnInvertTracker(const CRect& rect);`  
  
 Vous devez appeler cette fonction pour créer un contrôle de barre de défilement partagé.  Vous pouvez le remplacer pour créer les contrôles supplémentaires en regard de la barre de défilement.  
  
-   `virtual BOOL CreateScrollBarCtrl(DWORD dwStyle, UINT nID);`  
  
 Ces fonctions implémentent la logique de la fenêtre de fractionnement dynamique.  Vous pouvez remplacer ces pour fournir une logique plus avancées de séparateur.  
  
-   `virtual void DeleteView(int row, int col);`  
  
-   `virtual BOOL SplitRow(int cyBefore);`  
  
-   `virtual BOOL SplitColumn(int cxBefore);`  
  
-   `virtual void DeleteRow(int rowDelete);`  
  
-   `virtual void DeleteColumn(int colDelete);`  
  
## Fonctionnalités de CView  
 La classe d' `CView` utilise les commandes de haut niveau suivantes pour déléguer `CSplitterWnd` à l'implémentation.  Comme ces commandes sont virtuelles, l'implémentation standard d' `CView` ne requiert pas l'implémentation complète d' `CSplitterWnd` à lier dans.  Pour les applications qui utilisent `CView` mais pas `CSplitterWnd`, l'implémentation d' `CSplitterWnd` n'est pas liée à l'application.  
  
 `virtual BOOL CanActivateNext(BOOL bPrev = FALSE);`  
 Vérifie si ID\_NEXT\_PANE ou ID\_PREV\_PANE est actuellement possible.  
  
 `virtual void ActivateNext(BOOL bPrev = FALSE);`  
 Exécute la commande « du volet suivant » ou « volet précédent ».  
  
 `virtual BOOL DoKeyboardSplit();`  
 Exécute la commande de fractionnement du clavier, habituellement « fractionnement de fenêtre ».  
  
## Voir aussi  
 [Notes techniques par numéro](../mfc/technical-notes-by-number.md)   
 [Notes techniques par catégorie](../mfc/technical-notes-by-category.md)