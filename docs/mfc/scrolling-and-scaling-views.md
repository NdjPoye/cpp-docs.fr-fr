---
title: "D&#233;filement et mise &#224; l&#39;&#233;chelle des vues | Microsoft Docs"
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
  - "gestionnaires de messages"
  - "gestion des messages, barres de défilement dans la classe de vue"
  - "mettre à l'échelle les vues"
  - "barres de défilement, messages"
  - "faire défiler les vues"
ms.assetid: f98a3421-c336-407e-97ee-dbb2ffd76fbd
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# D&#233;filement et mise &#224; l&#39;&#233;chelle des vues
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC prend en charge les vues de défilement et les vues qui sont automatiquement mises à l'échelle de la taille de la fenêtre cadre qui s'affiche.  La classe `CScrollView` prend en charge les deux types de vues.  
  
 Pour plus d'informations sur le défilement et la mise à l'échelle, consultez la classe [CScrollView](../mfc/reference/cscrollview-class.md) dans *le guide de MFC*.  Pour obtenir un exemple de défilement, consultez [L'exemple Griffonnage](../top/visual-cpp-samples.md).  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   Faire défiler une vue  
  
-   Mettre une vue à l'échelle  
  
-   [\<caps:sentence id\="tgt8" sentenceid\="f321fcf7c88bc6e3f892ae0fc9b2f0d8" class\="tgtSentence"\>Coordonnées de vue\<\/caps:sentence\>](http://msdn.microsoft.com/library/windows/desktop/dd145205)  
  
##  <a name="_core_scrolling_a_view"></a> Faire défiler une vue  
 Si la taille d'un document est supérieure à la taille que la vue peut afficher.  Cela peut se produire si les données du document augmentent ou réduisent la fenêtre qui encadre la vue.  Dans ce cas, la vue doit prendre en charge le défilement.  
  
 Toute vue peut traiter les messages de barre de défilement dans les fonctions membres `OnHScroll` et `OnVScroll`.  Implémentez la gestion des messages de barre de défilement de ces fonctions, soit en effectuant tout le travail vous\-même, soit en utilisant la classe `CScrollView` pour gérer le défilement pour vous.  
  
 `CScrollView` procède comme suit :  
  
-   Gère la taille et le mode de mappage de la fenêtre et de la fenêtre d'affichage  
  
-   Défile automatiquement en réponse aux messages de barre de défilement  
  
 Vous pouvez spécifier le défilement pour une « page » \(lorsque l'utilisateur clique sur un axe de barre de défilement\) et une « ligne » \(lorsque l'utilisateur clique sur la flèche de défilement\).  Envisagez ces valeurs en fonction de la nature de la vue.  Par exemple, vous pouvez faire défiler par incréments de 1 pixels pour une vue de graphiques et par incréments de la hauteur de ligne dans les documents texte.  
  
##  <a name="_core_scaling_a_view"></a> Mettre une vue à l'échelle  
 Lorsque vous souhaitez que la vue pour ajuste automatiquement la taille de la fenêtre cadre, vous pouvez utiliser `CScrollView` pour mettre à l'échelle au lieu de défiler.  La vue logique est étirée ou réduite à la zone client de la fenêtre exactement.  Une vue mise à l'échelle n'a pas de barre de défilement.  
  
## Voir aussi  
 [Utilisation de vues](../mfc/using-views.md)