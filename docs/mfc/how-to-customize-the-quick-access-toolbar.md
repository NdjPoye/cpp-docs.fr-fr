---
title: "Comment&#160;: personnaliser la barre d&#39;outils Acc&#232;s rapide | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "barre d'outils Accès rapide, personnalisation"
ms.assetid: 2554099b-0c89-4605-9249-31bf9cbcefe0
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Comment&#160;: personnaliser la barre d&#39;outils Acc&#232;s rapide
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La Barre d'outils Accès rapide \(QAT\) est une barre d'outils personnalisable qui contient un jeu de commandes affichées en regard du bouton Application ou sous les onglets de catégorie.  L'illustration suivante montre une Barre d'outils Accès rapide classique.  
  
 ![Barre d'outils Accès rapide de ruban MFC](../mfc/media/quick_access_toolbar.png "Quick\_Access\_Toolbar")  
  
 Pour personnaliser la Barre d'outils Accès rapide, ouvrez\-la dans la fenêtre **Propriétés**, modifiez ses commandes, puis affichez un aperçu du contrôle du ruban.  
  
### Pour ouvrir la Barre d'outils Accès rapide dans la fenêtre Propriétés  
  
1.  Dans Visual Studio, dans le menu **Affichage**, cliquez sur **Affichage des ressources**.  
  
2.  Dans **Affichage des ressources**, double\-cliquez sur la ressource du ruban pour l'afficher dans l'aire de conception.  
  
3.  Dans l'aire de conception, faites clic droit sur le menu de la Barre d'outils Accès rapide puis cliquez sur **Propriétés**.  
  
## Propriétés de la Barre d'outils Accès rapide  
 Le tableau suivant définit les propriétés de la Barre d'outils Accès rapide.  
  
|Propriété|Définition|  
|---------------|----------------|  
|QAT Position|Spécifie la position de la Barre d'outils Accès rapide au démarrage de l'application.  L'emplacement peut être **Supérieur\(e\)** ou **Inférieur\(e\)** au contrôle du ruban.|  
|Eléments QAT|Spécifie les commandes disponibles pour la Barre d'outils Accès rapide.|  
  
#### Pour ajouter ou supprimer des commandes dans la Barre d'outils Accès rapide  
  
1.  Dans la fenêtre **Propriétés**, cliquez sur **Eléments QAT**, puis sur le bouton d'ellipse **\(...\)**.  
  
2.  Dans la boîte de dialogue **Éditeur d'éléments QAT**, utilisez les boutons **Ajouter** et **Supprimer** pour modifier la liste des commandes dans la Barre d'outils Accès rapide.  
  
3.  Si vous souhaitez qu'une commande apparaisse à la fois dans la Barre d'outils Accès rapide et dans le menu de la Barre d'outils Accès rapide, cochez la case située en regard de la commande.  Si vous souhaitez que la commande apparaisse uniquement dans le menu, décochez la case.  
  
## Afficher un aperçu du ruban  
 Les commandes de la Barre d'outils Accès rapide ne s'affichent pas dans l'aire de conception.  Pour les afficher, vous devez afficher un aperçu du ruban ou exécuter l'application.  
  
#### Pour afficher un aperçu du contrôle du ruban  
  
-   Dans la **Barre d'Outils de l'Éditeur Ribbon**, cliquez sur le bouton **Tester le Ruban**.  
  
## Voir aussi  
 [Concepteur de ruban \(MFC\)](../mfc/ribbon-designer-mfc.md)