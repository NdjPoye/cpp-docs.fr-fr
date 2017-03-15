---
title: "Avantages de l&#39;architecture document/vue | Microsoft Docs"
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
  - "architecture document/vue, avantages"
  - "vues, avantages"
ms.assetid: 0bc27071-e120-4889-939c-ce1e61fb9cb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Avantages de l&#39;architecture document/vue
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le principal avantage de l'utilisation de l'architecture documents\/Vue de MFC est que l'architecture prend en charge plusieurs vues du même document particulièrement bien. \(Si vous n'avez pas besoin de plusieurs vues et la surcharge du document ou de la vue est excessive dans votre application, évitez l'architecture.  [Solutions de remplacement de l'architecture document\/vue](../mfc/alternatives-to-the-document-view-architecture.md).\)  
  
 Supposons que votre application permet aux utilisateurs de voir des données numériques soit sous forme de feuille de calcul soit sous forme de graphique.  Un utilisateur peut souhaiter consulter simultanément les données brutes, sous la forme de feuille de calcul, et un graphique qui résulte des données.  Vous affichez les vues différentes dans les fenêtres cadres distinctes ou dans des volets de séparateur dans une fenêtre unique.  Supposons maintenant que l'utilisateur peut modifier les données de la feuille de calcul et afficher les modifications immédiatement répercutées dans le graphique.  
  
 Dans MFC, la vue de la feuille de calcul et la vue Graphique seraient fondées sur différentes classes dérivées de CView.  Les deux affichages sont associées à un objet de document unique.  Le document stocke les données \(ou peut\-être les obtient\-il d'une base de données\).  Affiche l'accès au document et affiche les données qu'ils extraient de celui\-ci.  
  
 Lorsqu'un utilisateur met à jour une des vues, cette vue d'objet appelle `CDocument::UpdateAllViews`.  La fonction notifie les vues de tous les documents, et chaque vue se met à jour elle\-même en utilisant les dernières données en date du document.  L'appel unique à `UpdateAllViews` synchronise les différentes vues.  
  
 Il est difficile de coder ce scénario sans séparation des données de la vue, en particulier si les vues enregistraient les données elles\-mêmes.  Avec le document\/vue, cela est facile.  Le .Net Framework effectue la majorité du travail de coordination automatiquement.  
  
## Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Alternatives au document\/vue](../mfc/alternatives-to-the-document-view-architecture.md)  
  
-   [CDocument](../mfc/reference/cdocument-class.md)  
  
-   [CView](../mfc/reference/cview-class.md)  
  
-   [CDocument::UpdateAllViews](../Topic/CDocument::UpdateAllViews.md)  
  
-   [CView::GetDocument](../Topic/CView::GetDocument.md)  
  
## Voir aussi  
 [Architecture document\/vue](../mfc/document-view-architecture.md)