---
title: "CSplitterWnd Class | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "reference"
f1_keywords: 
  - "CSplitterWnd"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "CSplitterWnd class"
  - "dynamic splitter windows"
  - "vues multiples"
  - "fenêtres fractionnées"
  - "static splitter windows"
  - "vues, multiples par frame"
ms.assetid: fd0de258-6dbe-4552-9e47-a39de0471d51
caps.latest.revision: 22
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# CSplitterWnd Class
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Fournit les fonctionnalités d'une fenêtre fractionnée, qui est une fenêtre qui contient plusieurs volets.  
  
## Syntaxe  
  
```  
class CSplitterWnd : public CWnd  
```  
  
## Membres  
  
### Constructeurs publics  
  
|Nom|Description|  
|---------|-----------------|  
|[CSplitterWnd::CSplitterWnd](../Topic/CSplitterWnd::CSplitterWnd.md)|Appelez pour construire un objet d' `CSplitterWnd` .|  
  
### Méthodes publiques  
  
|Nom|Description|  
|---------|-----------------|  
|[CSplitterWnd::ActivateNext](../Topic/CSplitterWnd::ActivateNext.md)|Exécute le prochain volet ou la commande précédente de volet.|  
|[CSplitterWnd::CanActivateNext](../Topic/CSplitterWnd::CanActivateNext.md)|Vérifie si le prochain volet ou la commande précédente du volet est possible actuellement.|  
|[CSplitterWnd::Create](../Topic/CSplitterWnd::Create.md)|Appelez pour créer une fenêtre fractionnée dynamique et pour la liaison à l'objet d' `CSplitterWnd` .|  
|[CSplitterWnd::CreateScrollBarCtrl](../Topic/CSplitterWnd::CreateScrollBarCtrl.md)|Crée un contrôle de barre de défilement partagé.|  
|[CSplitterWnd::CreateStatic](../Topic/CSplitterWnd::CreateStatic.md)|Appelez pour créer une fenêtre fractionnée statique et pour la liaison à l'objet d' `CSplitterWnd` .|  
|[CSplitterWnd::CreateView](../Topic/CSplitterWnd::CreateView.md)|Appelez pour créer un volet dans une fenêtre fractionnée.|  
|[CSplitterWnd::DeleteColumn](../Topic/CSplitterWnd::DeleteColumn.md)|Supprime une colonne de la fenêtre fractionnée.|  
|[CSplitterWnd::DeleteRow](../Topic/CSplitterWnd::DeleteRow.md)|Supprime une ligne de la fenêtre fractionnée.|  
|[CSplitterWnd::DeleteView](../Topic/CSplitterWnd::DeleteView.md)|Supprime une vue de la fenêtre fractionnée.|  
|[CSplitterWnd::DoKeyboardSplit](../Topic/CSplitterWnd::DoKeyboardSplit.md)|Exécute la commande fractionnée de clavier, généralement « fractionnement de fenêtre. »|  
|[CSplitterWnd::DoScroll](../Topic/CSplitterWnd::DoScroll.md)|Performs est synchronisé le défilement des fenêtres fractionnées.|  
|[CSplitterWnd::DoScrollBy](../Topic/CSplitterWnd::DoScrollBy.md)|Défile fractionnent les fenêtres par un nombre donné de pixels.|  
|[CSplitterWnd::GetActivePane](../Topic/CSplitterWnd::GetActivePane.md)|Détermine le volet actif à partir de le focus ou de la vue active dans le frame.|  
|[CSplitterWnd::GetColumnCount](../Topic/CSplitterWnd::GetColumnCount.md)|Retourne le nombre de colonnes actuellement pane.|  
|[CSplitterWnd::GetColumnInfo](../Topic/CSplitterWnd::GetColumnInfo.md)|Retourne des informations sur la colonne spécifiée.|  
|[CSplitterWnd::GetPane](../Topic/CSplitterWnd::GetPane.md)|Retourne le volet à la ligne et la colonne spécifiées.|  
|[CSplitterWnd::GetRowCount](../Topic/CSplitterWnd::GetRowCount.md)|Retourne le nombre de lignes en cours de volet.|  
|[CSplitterWnd::GetRowInfo](../Topic/CSplitterWnd::GetRowInfo.md)|Retourne des informations sur la ligne spécifiée.|  
|[CSplitterWnd::GetScrollStyle](../Topic/CSplitterWnd::GetScrollStyle.md)|Retourne le style partagé de barre de défilement.|  
|[CSplitterWnd::IdFromRowCol](../Topic/CSplitterWnd::IdFromRowCol.md)|Retourne l'ID de fenêtre enfant du volet à la ligne et la colonne spécifiées.|  
|[CSplitterWnd::IsChildPane](../Topic/CSplitterWnd::IsChildPane.md)|Appel à déterminer si la fenêtre est actuellement un volet enfant de cette fenêtre fractionnée.|  
|[CSplitterWnd::IsTracking](../Topic/CSplitterWnd::IsTracking.md)|Détermine si la barre de fractionnement actuel est déplacée.|  
|[CSplitterWnd::RecalcLayout](../Topic/CSplitterWnd::RecalcLayout.md)|Appelez pour afficher à nouveau la fenêtre fractionnée après avoir défini la taille de ligne ou de colonne.|  
|[CSplitterWnd::SetActivePane](../Topic/CSplitterWnd::SetActivePane.md)|Définit un volet pour être l'actif dans le frame.|  
|[CSplitterWnd::SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md)|Appelez pour définir les informations des colonnes spécifiées.|  
|[CSplitterWnd::SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md)|Appelez pour définir les informations spécifiées de ligne.|  
|[CSplitterWnd::SetScrollStyle](../Topic/CSplitterWnd::SetScrollStyle.md)|Spécifie le style de barre de défilement pour le stockage partagé de la barre de défilement de la fenêtre fractionnée.|  
|[CSplitterWnd::SplitColumn](../Topic/CSplitterWnd::SplitColumn.md)|Indique où une fenêtre frame fractionne verticalement.|  
|[CSplitterWnd::SplitRow](../Topic/CSplitterWnd::SplitRow.md)|Indique où une fenêtre frame fractionne horizontalement.|  
  
### Méthodes protégées  
  
|Nom|Description|  
|---------|-----------------|  
|[CSplitterWnd::OnDraw](../Topic/CSplitterWnd::OnDraw.md)|Appelé par l'infrastructure pour dessiner la fenêtre fractionnée.|  
|[CSplitterWnd::OnDrawSplitter](../Topic/CSplitterWnd::OnDrawSplitter.md)|Affiche une image d'une fenêtre fractionnée.|  
|[CSplitterWnd::OnInvertTracker](../Topic/CSplitterWnd::OnInvertTracker.md)|Affiche l'image d'une fenêtre fractionnée pour être la même taille et la forme comme une fenêtre frame.|  
  
## Notes  
 Un volet est généralement un objet spécifique à l'application dérivée de [CView](../../mfc/reference/cview-class.md), mais elle peut être n'importe quel objet de [CWnd](../../mfc/reference/cwnd-class.md) ayant l'ID appropriée de fenêtre enfant  
  
 Un objet d' `CSplitterWnd` est généralement inclus dans un objet parent de [CFrameWnd](../../mfc/reference/cframewnd-class.md) ou de [CMDIChildWnd](../../mfc/reference/cmdichildwnd-class.md) .  Créez un objet d' `CSplitterWnd` à l'aide de les étapes suivantes :  
  
1.  Incluez une variable membre d' `CSplitterWnd` dans le frame parent.  
  
2.  Substituez la fonction membre parent de [CFrameWnd::OnCreateClient](../Topic/CFrameWnd::OnCreateClient.md) du frame.  
  
3.  D' `OnCreateClient`substitution, appelez la fonction membre de [Create](../Topic/CSplitterWnd::Create.md) ou de [CreateStatic](../Topic/CSplitterWnd::CreateStatic.md) d' `CSplitterWnd`.  
  
 Appelez la fonction membre de **Créer** pour créer une fenêtre fractionnée dynamique.  Une fenêtre fractionnée dynamique est généralement utilisée pour créer et faire défiler plusieurs volets différents, ou vues, du même document.  l'infrastructure crée automatiquement un premier volet pour le séparateur ; l'infrastructure crée, redimensionne, et rejette les volets supplémentaires lorsque l'utilisateur fonctionne les contrôles de la fenêtre fractionnée.  
  
 Lorsque vous appelez **Créer**, vous spécifiez une hauteur de ligne et une largeur de colonne minimale qui déterminent si les volets sont trop petites pour être entièrement affichés.  Après avoir appelé **Créer**, vous pouvez adapter ces minimum en appelant les fonctions membres de [SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) et de [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) .  
  
 Utilisez également les fonctions membres d' `SetColumnInfo` et d' `SetRowInfo` pour définir une largeur « idéale » pour une colonne et la hauteur « idéale » pour une ligne.  Lorsque l'infrastructure affiche une fenêtre fractionnée, elle affiche d'abord le frame parent, la fenêtre fractionnée.  L'infrastructure répertorie les volets dans les lignes et colonnes selon leurs dimensions idéale, l'utilisation du supérieur gauche à l'angle inférieur droit de la zone cliente de la fenêtre fractionnée.  
  
 Tous les volets dans une fenêtre fractionnée dynamique doivent être de la même classe.  Les applications familières qui prennent en charge les fenêtres fractionnées dynamiques sont Microsoft Word et Microsoft Excel.  
  
 Utilisez la fonction membre d' `CreateStatic` pour créer une fenêtre fractionnée statique.  L'utilisateur peut modifier uniquement la taille des volets dans une fenêtre fractionnée statique, non leur numéro ou commande.  
  
 Vous devez créer spécifiquement les volets statiques du séparateur lorsque vous créez le séparateur statique.  Veillez à créer tous les volets avant que la fonction membre parent d' `OnCreateClient` du frame retourne, ou infrastructure n'affiche pas la fenêtre correctement.  
  
 La fonction membre d' `CreateStatic` lance automatiquement un séparateur statique avec une hauteur de ligne et une largeur de colonne minimum de 0.  Après avoir appelé **Créer**, ajustez ces minimum en appelant les fonctions membres de [SetColumnInfo](../Topic/CSplitterWnd::SetColumnInfo.md) et de [SetRowInfo](../Topic/CSplitterWnd::SetRowInfo.md) .  Utilisez également `SetColumnInfo` et `SetRowInfo` après avoir appelé `CreateStatic` pour indiquer les dimensions idéale souhaitées de volet.  
  
 Les volets différents d'un séparateur statique appartiennent souvent à des classes.  Pour obtenir des exemples de fenêtres fractionnées statiques, consultez l'éditeur graphique et le gestionnaire de fichiers windows.  
  
 Une fenêtre fractionnée en charge les barres de défilement spéciales \(en dehors des barres de défilement que les volets peuvent avoir\).  Ces barres de défilement sont des enfants de l'objet d' `CSplitterWnd` et sont partagés avec les volets.  
  
 Vous créez ces barres de défilement spéciales lorsque vous créez la fenêtre fractionnée.  Par exemple, `CSplitterWnd` qui a une ligne, deux colonnes, et le style de **WS\_VSCROLL** affichent une barre de défilement verticale partagée par les deux volets.  Lorsque l'utilisateur déplace la barre de défilement, les messages d' `WM_VSCROLL` sont envoyés aux deux volets.  Lorsque les volets définissez la position de la barre de défilement, la barre de défilement partagée est définie.  
  
 Pour plus d'informations sur des fenêtres fractionnées, consultez :  
  
-   [Note technique 29](../../mfc/tn029-splitter-windows.md)  
  
-   Article de la Base de connaissances Q262024 : HOWTO : utilisation CPropertySheet en tant qu'enfant de CSplitterWnd  
  
 Pour plus d'informations sur la création de fenêtres fractionnées dynamiques, consultez :  
  
-   Exemple [Scribble](../../top/visual-cpp-samples.md)MFC  
  
-   Exemple [VIEWEX](../../top/visual-cpp-samples.md)MFC.  
  
## Hiérarchie d'héritage  
 [CObject](../../mfc/reference/cobject-class.md)  
  
 [CCmdTarget](../../mfc/reference/ccmdtarget-class.md)  
  
 [CWnd](../../mfc/reference/cwnd-class.md)  
  
 `CSplitterWnd`  
  
## Configuration requise  
 **Header:** afxext.h  
  
## Voir aussi  
 [Exemple VIEWEX MFC](../../top/visual-cpp-samples.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)   
 [Graphique hiérarchique](../../mfc/hierarchy-chart.md)   
 [CView Class](../../mfc/reference/cview-class.md)   
 [CWnd, classe](../../mfc/reference/cwnd-class.md)