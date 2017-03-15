---
title: "Architecture de l&#39;aper&#231;u avant impression | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "afficher un aperçu avant impression"
  - "aperçu avant impression, architecture"
  - "aperçu avant impression, Modifications de MFC"
  - "aperçu avant impression, processus"
  - "imprimer (MFC), aperçu avant impression"
ms.assetid: 0efc87e6-ff8d-43c5-9d72-9b729a169115
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Architecture de l&#39;aper&#231;u avant impression
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment l'infrastructure MFC implémente la fonctionnalité d'aperçu avant impression.  Les rubriques traitées ici sont les suivantes :  
  
-   [Processus d'aperçu avant impression](#_core_the_print_preview_process)  
  
-   [Modifier l'aperçu avant impression](#_core_modifying_print_preview)  
  
 L'aperçu avant impression est quelque peu différent de l'écran et de l'impression puisque, au lieu d'ajouter directement une image sur un périphérique, l'application doit simuler l'imprimante à l'écran.  Pour accueillir cela, la bibliothèque MFC définit une classe \(non documentée\) particulière dérivée de [CDC, classe](../mfc/reference/cdc-class.md), appelée **CPreviewDC**.  Tous les objets `CDC` contiennent deux contextes de périphérique, mais ils sont généralement les mêmes.  Dans un objet **CPreviewDC**, ils sont différents : la première représente l'imprimante à simuler, et le second représente l'écran sur lequel la sortie est réellement affichée.  
  
##  <a name="_core_the_print_preview_process"></a> Fenêtre Aperçu avant Processus.  
 Lorsque l'utilisateur sélectionne l'ordre d'aperçu avant impression dans le menu de **Fichier**, l'infrastructure crée un objet **CPreviewDC**.  Chaque fois que votre application effectue une opération définissant une caractéristique du contexte de l'imprimante, l'infrastructure exécute également une opération semblable dans le contexte de périphérique.  Par exemple, si votre application sélectionne une police pour l'impression, l'infrastructure sélectionne une police pour l'écran qui simule la police d'imprimante.  Chaque fois que votre application enverrait la sortie vers l'imprimante, l'infrastructure envoie à la place la sortie à l'écran.  
  
 L'aperçu avant impression diffère également de l'impression dans l'ordre de plan dans lequel chacun dessine les pages d'un document.  Lors de l'impression, l'infrastructure suit une boucle continue d'impression jusqu'à ce qu'une certaine plage de pages ait été affichée.  Pendant l'aperçu avant impression, une ou deux pages sont affichées à tout moment, puis l'application attend ; aucune page ne s'affiche jusqu'à ce que l'utilisateur réponde.  Pendant l'aperçu avant impression, l'application doit également respecter les messages `WM_PAINT`, comme elle le fait pendant l'affichage de l'écran ordinaire.  
  
 La fonction [CView::OnPreparePrinting](../Topic/CView::OnPreparePrinting.md) est appelée lorsque le mode aperçu est appelé, comme il l'est au début d'un travail d'impression.  La structure de [CPrintInfo Structure](../mfc/reference/cprintinfo-structure.md) transmise à cette fonction contient plusieurs membres dont vous pouvez définir les valeurs pour paramétrer certaines caractéristiques de l'opération d'aperçu avant impression.  Par exemple, vous pouvez définir le membre **m\_nNumPreviewPages** pour spécifier si vous souhaitez afficher un aperçu du document en mode une page ou deux page.  
  
##  <a name="_core_modifying_print_preview"></a> Modifier l'Aperçu avant Impression  
 Vous pouvez modifier le comportement et l'affichage de l'aperçu avant impression de plusieurs façons et facilement.  Par exemple, vous pouvez, entre autres choses :  
  
-   Amener l'aperçu avant impression à afficher une barre de défilement pour un accès aisé à toute page du document.  
  
-   Amener l'aperçu avant impression à maintenir la position de l'utilisateur dans le document en commençant son affichage par la page actuelle.  
  
-   Amener l'exécution de différentes initialisations pour l'aperçu avant impression et l'impression.  
  
-   Amenerl'aperçu avant impression à afficher des numéros de page dans vos propres formats.  
  
 Si vous connaissez le délai d'attente du document et appelez `SetMaxPage` avec la valeur appropriée, l'infrastructure peut utiliser ces informations en mode aperçu ainsi que lors de l'impression.  Une fois que l'infrastructure connaît la longueur du document, elle peut fournir à la fenêtre d'aperçu une barre de défilement, ce qui permet à l'utilisateur de passer d'une page à une autre dans les deux sens dans le document en mode aperçu.  Si vous n'avez pas défini la longueur du document, l'infrastructure ne peut pas placer la case de défilement pour indiquer la position actuelle, l'infrastructure n'ajoute pas de barre de défilement.  Dans ce cas, l'utilisateur doit utiliser les boutons page suivante et page précédente dans la barre de contrôle de la fenêtre d'aperçu pour naviguer dans le document.  
  
 Pour l'aperçu avant impression, il peut être utile d'affecter une valeur au `m_nCurPage` membre de `CPrintInfo`, même si vous ne l'auriez jamais fait pour une impression ordinaire.  Lors d'une l'impression ordinaire, ce membre distribue les informations de sync framework à la classe d'affichage.  Voici comment l'infrastructure indique à la vue quelle page doit être imprimée.  
  
 En revanche, lorsque le mode aperçu avant impression démarre, le membre de `m_nCurPage` distribue les informations dans le sens inverse : de la vue à l'infrastructure.  L'infrastructure utilise la valeur de ce membre pour déterminer si la page doit d'abord afficher un aperçu.  La valeur par défaut de ce membre est 1, la première page du document s'affiche initialement.  Vous pouvez remplacer `OnPreparePrinting` pour affecter à ce membre le numéro de la page affichée lorsque la commande aperçu avant impression fut appelée.  De cette manière, l'application gère la position actuelle de l'utilisateur lors du passage du mode d'affichage normale au mode d'aperçu avant impression.  
  
 Parfois vous pouvez souhaiter que `OnPreparePrinting` effectue différentes initialisations selon qu'il est appelé pour un travail d'impression ou pour l'aperçu avant impression.  Vous pouvez déterminer ce problème en examinant la variable membre de **m\_bPreview** dans la structure `CPrintInfo`.  Ce membre prend la valeur **TRUE** lorsque l'aperçu avant impression est appelé.  
  
 La structure `CPrintInfo` contient également un membre nommé **m\_strPageDesc**, qui est utilisé pour mettre en forme les chaînes affichées en bas de l'écran dans les modes une seule page et multiples pages.  Par défaut ces chaînes sont de la forme « Page *n*» et « Pages *n* \- *m* », mais vous pouvez modifier **m\_strPageDesc** depuis `OnPreparePrinting` et définir des chaînes pour qu'elle soit plus élaborée.  Consultez [CPrintInfo Structure](../mfc/reference/cprintinfo-structure.md) dans *Référence MFC* pour plus d'informations,  
  
## Voir aussi  
 [Impression et aperçu avant impression](../mfc/printing-and-print-preview.md)   
 [Impression](../mfc/printing.md)   
 [CView Class](../mfc/reference/cview-class.md)   
 [CDC, classe](../mfc/reference/cdc-class.md)