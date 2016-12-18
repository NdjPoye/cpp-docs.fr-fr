---
title: "Contr&#244;les ActiveX MFC&#160;: ajout d&#39;&#233;v&#233;nements personnalis&#233;s | Microsoft Docs"
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
  - "événements Click, événements personnalisés"
  - "ClickIn (événement)"
  - "COleControl (classe), événements personnalisés"
  - "événements personnalisés"
  - "événements personnalisés, ajouter aux contrôles ActiveX"
  - "EVENT_CUSTOM (macro)"
  - "EVENT_CUSTOM (préfixe)"
  - "événements (C++), contrôles ActiveX"
  - "FireClickIn (événement)"
  - "FireEvent (méthode), ajouter des événements personnalisés"
  - "InCircle (méthode)"
  - "contrôles ActiveX MFC, événements"
ms.assetid: c584d053-1e34-47aa-958e-37d3e9b85892
caps.latest.revision: 14
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Contr&#244;les ActiveX MFC&#160;: ajout d&#39;&#233;v&#233;nements personnalis&#233;s
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les événements personnalisés sont différentes des événements magasin du fait qu'ils ne sont pas automatiquement générés par la classe `COleControl`.  Un événement personnalisé identifie une action, définie par le développeur de contrôle, comme un événement.  Les entrées de table pour les événements personnalisés sont représentées par la macro `EVENT_CUSTOM`.  La section suivante implémente un événement personnalisé pour un projet de contrôle ActiveX qui a été créé à l'aide de l'Assistant Contrôle ActiveX.  
  
##  <a name="_core_adding_a_custom_event_with_classwizard"></a> Ajouter un événement personnalisé à l'aide de l'Assistant Ajout d'événement  
 La procédure suivante ajoute un événement personnalisé spécifique, ClickIn.  Vous pouvez utiliser cette procédure pour ajouter d'autres événements personnalisés.  Remplacez le nom d'événement personnalisé et ses paramètres au nom d'événement et aux paramètres de ClickIn.  
  
#### Pour ajouter l'événement personnalisé de ClickIn à l'aide de l'événement  
  
1.  Chargez votre projet.  
  
2.  Sous Affichage de classes, cliquez avec le bouton droit sur votre classe de contrôle ActiveX pour ouvrir le menu contextuel.  
  
3.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter un événement**.  
  
     Cela ouvre le menu de création d'événements.  
  
4.  Dans la zone de **Nom de l'événement**, commencez par sélectionner n'importe quel événement existant, cliquez sur la case d'option **Personnalisé**, puis tapez `ClickIn`.  
  
5.  Dans la zone **Internal name**, tapez le nom de la fonction lancée au déclenchement de l'événement.  Pour cet exemple, utilisez la valeur par défaut fournie par l'Assistant Ajout d'événement \(`FireClickIn`\).  
  
6.  Ajoutez un paramètre, appelé `xCoord` \(type `OLE_XPOS_PIXELS`\), à l'aide de les contrôles de **Nom du paramètre** et de **Type de paramètre** .  
  
7.  Ajoutez un deuxième paramètre, appelé `yCoord` \(type `OLE_YPOS_PIXELS`\).  
  
8.  Cliquez sur **Terminer** pour créer l'événement.  
  
##  <a name="_core_classwizard_changes_for_custom_events"></a> Modifications de l'Assistant Ajout d'événement pour les événements personnalisés  
 Lorsque vous ajoutez un événement personnalisé, l'assistant ajour d'événements apporte des modifications aux fichiers .H, .CPP, et .IDL de la classe de contrôle.  Les exemples de code suivants sont propres à l'événement de ClickIn.  
  
 Les lignes suivantes apparaissent dans l'en\-tête \(. H\) fichier de la classe de contrôle :  
  
 [!code-cpp[NVC_MFC_AxUI#7](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-events_1.h)]  
  
 Ce code déclare une fonction inline appelée `FireClickIn` qui appelle [COleControl::FireEvent](../Topic/COleControl::FireEvent.md) pour l'événement et les paramètres de ClickIn que vous avez définis avec l'assistant ajout d'événement.  
  
 En outre, la ligne suivante est ajoutée à la table pour le contrôle, situé dans le fichier d'implémentation \(.CPP\) de la classe de contrôle :  
  
 [!code-cpp[NVC_MFC_AxUI#8](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-events_2.cpp)]  
  
 Ce code associe l'événement ClickIn à la fonction inline `FireClickIn`, en passant les paramètres que vous avez définis à l'aide de l'assistant ajout d'événement.  
  
 Enfin, la ligne suivante est ajoutée à votre fichier .IDL :  
  
 [!code-cpp[NVC_MFC_AxUI#9](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-events_3.idl)]  
  
 Cette ligne affecte à l'événement de ClickIn un ID spécifique, tiré de la position des événements dans la liste d'événements c d'événements.  La liste d'entrée dans le permet à un conteneur anticiper l'événement.  Par exemple, il peut fournir un code du gestionnaire d'exécution lorsque l'événement est déclenché.  
  
##  <a name="_core_calling_fireclickin"></a> Appeler FireClickIn  
 Maintenant que vous avez ajouté l'événement personnalisé de ClickIn à l'aide de l'événement, vous devez décider quand cet événement doit être généré.  Vous effectuez cette opération en appelant `FireClickIn` lorsque l'action appropriée se produit.  Pour cette discussion, la commande utilise la fonction `InCircle` dans un gestionnaire de messages `WM_LBUTTONDOWN` pour déclencher l'événement de ClickIn lorsqu'un utilisateur clique sur région une circulaire ou elliptique.  La procédure suivante ajoute le gestionnaire `WM_LBUTTONDOWN`.  
  
#### Pour ajouter un gestionnaire de messages avec l'assistant ajout d'événement  
  
1.  Chargez votre projet.  
  
2.  Sous Affichage de classes, sélectionnez votre classe de contrôles ActiveX.  
  
3.  Dans la fenêtre Propriétés, cliquez sur le bouton **Messages**.  
  
     La fenêtre Propriétés affiche une liste de messages pouvant être traités par le contrôle ActiveX.  Un message apparaissant en gras a déjà une fonction gestionnaire affectée.  
  
4.  Dans la fenêtre des Propriétés, sélectionnez le message à traiter.  Pour cet exemple, sélectionnez `WM_LBUTTONDOWN`.  
  
5.  Dans la liste déroulante à droite, sélectionnez **\<Ajouter\> OnLButtonDown**  
  
6.  Double\-cliquez sur la nouvelle fonction gestionnaire d'Affichage de classes pour accéder au code de gestionnaire de messages du fichier d'implémentation \(.CPP\) de votre contrôle ActiveX.  
  
 L'exemple de code suivant appelle la fonction **InCircle** chaque fois que le bouton gauche de la souris est cliqué dans la fenêtre de contrôle.  Cet exemple se trouve dans la fonction gestionnaire `WM_LBUTTONDOWN`, `OnLButtonDown`, dans le résumé de [Exemple de Circ](../top/visual-cpp-samples.md).  
  
 [!code-cpp[NVC_MFC_AxUI#10](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-events_4.cpp)]  
  
> [!NOTE]
>  Lorsque l'Assistant Ajout d'événement crée des gestionnaires de messages pour les actions de bouton de la souris, un appel au même gestionnaire de messages de la classe de base est automatiquement ajouté.  Ne retirez pas cet appel.  Si votre contrôle utilise un des messages de la souris magasin, les gestionnaires des messages dans la classe de base doivent être appelés pour garantir que la capture de la souris est gérée correctement.  
  
 Dans l'exemple suivant, l'événement est activé uniquement lorsque le bouton se trouvent dans une zone circulaire ou elliptique dans le contrôle.  Pour obtenir ce comportement, vous pouvez placer la fonction `InCircle` dans le fichier à l'implémentation de votre contrôle \(.CPP\) :  
  
 [!code-cpp[NVC_MFC_AxUI#11](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-events_5.cpp)]  
  
 Vous devez également ajouter la déclaration suivante de la fonction `InCircle` à l'en\-tête de votre contrôle \(. H\) fichier :  
  
 [!code-cpp[NVC_MFC_AxUI#12](../mfc/codesnippet/CPP/mfc-activex-controls-adding-custom-events_6.h)]  
  
##  <a name="_core_custom_events_with_stock_names"></a> Événements personnalisés avec des noms de stock  
 Vous pouvez créer des événements personnalisés avec le même nom que les événements magasin, mais vous ne pouvez pas appliquer les deux à la fois dans le même contrôle.  Par exemple, vous pouvez créer un événement personnalisé appelé "Click" qui ne s'active quand l'événement standard "Click" s'active.  Vous pouvez ensuite activer l'événement Click à tout moment en appelant la fonction d'activation.  
  
 La procédure suivante ajoute un événement Click personnalisé.  
  
#### Pour ajouter un événement personnalisé qui utilise un nom d'événement stock  
  
1.  Chargez votre projet.  
  
2.  Sous Affichage de classes, cliquez avec le bouton droit sur votre classe de contrôle ActiveX pour ouvrir le menu contextuel.  
  
3.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter un événement**.  
  
     Cela ouvre le menu de création d'événements.  
  
4.  Dans la liste déroulante **Nom d'événement**, sélectionnez un nom d'événement standard.  Pour cet exemple, sélectionnez **"Click"**.  
  
5.  Pour **Type d'événement**, sélectionnez **Personnalisé**.  
  
6.  Cliquez sur **Terminer** pour créer l'événement.  
  
7.  Appelez `FireClick` aux emplacements appropriés dans votre code.  
  
## Voir aussi  
 [Contrôles ActiveX MFC](../mfc/mfc-activex-controls.md)   
 [Contrôles ActiveX MFC : méthodes](../mfc/mfc-activex-controls-methods.md)   
 [COleControl Class](../mfc/reference/colecontrol-class.md)