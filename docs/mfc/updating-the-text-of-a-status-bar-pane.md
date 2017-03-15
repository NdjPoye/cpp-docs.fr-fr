---
title: "Mise &#224; jour du texte d&#39;un volet de barre d&#39;&#233;tat | Microsoft Docs"
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
  - "CStatusBar (classe), mettre à jour"
  - "ON_UPDATE_COMMAND_UI (macro)"
  - "volets, barre d'état"
  - "SetText (méthode)"
  - "barres d'état, mettre à jour"
  - "texte, barre d'état"
  - "mettre à jour des objets de l'interface utilisateur"
  - "objets de l'interface utilisateur, mettre à jour"
ms.assetid: 4984a3f4-9905-4d8c-a927-dca19781053b
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Mise &#224; jour du texte d&#39;un volet de barre d&#39;&#233;tat
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment modifier le texte qui apparaît dans un de volet barre d'état MFC.  Une barre d'état — objet fenêtre de la classe [CStatusBar](../mfc/reference/cstatusbar-class.md) — contient plusieurs "volets". Chaque volet est une zone rectangulaire de la barre d'état que vous pouvez utiliser pour afficher des informations.  Par exemple, de nombreuses applications affichent l'état de CAPS LOCK, de NUM LOCK, et d'autres touches dans les volets à droite.  Les applications affichent également souvent le texte informatif dans le volet situé le plus à gauche \(volet 0\), parfois appelé le "volet de message". Par exemple, la barre d'état MFC par défaut utilise le volet de message pour afficher une chaîne qui explique l'élément de menu ou le bouton de la barre d'outils sélectionné.  La figure dans [Barres d'état](../mfc/status-bar-implementation-in-mfc.md) affiche une barre d'état d'une application créée par l'Assistant Application MFC.  
  
 Par défaut, MFC n'active pas un volet `CStatusBar` lorsqu'il crée le volet.  Pour activer un volet, vous devez utiliser la macro `ON_UPDATE_COMMAND_UI` pour chaque volet dans la barre d'état et mettre à jour les volets.  Comme les volets n'envoie aucun message **WM\_COMMAND** \(ils ne sont pas comme les boutons de la barre d'outils\), vous devez taper le code manuellement.  
  
 Par exemple, supposons qu'un volet a `ID_INDICATOR_PAGE` comme identificateur de commande et qu'il contient le numéro de page actuelle dans un document.  La procédure suivante explique comment créer un nouveau volet dans la barre d'état.  
  
### Pour créer un nouveau volet  
  
1.  Définissez l'ID de commande du volet  
  
     Dans le menu **View**, cliquez sur **Resource View**.  Cliquez avec le bouton droit sur la ressource projet puis cliquez sur **Resource Symbols**.  Dans la boîte de dialogue Symboles de ressource, cliquez sur `New`.  Tapez le nom de l'ID de commande : par exemple, `ID_INDICATOR_PAGE`.  Spécifiez une valeur pour l'ID, ou acceptez la valeur suggérée par la boîte de dialogue de symboles de ressources.  Par exemple, pour `ID_INDICATOR_PAGE`, acceptez la valeur par défaut.  Fermez la boîte de dialogue de symboles de ressources.  
  
2.  Définissez une chaîne par défaut à afficher dans le volet.  
  
     Avec l'affichage des ressources ouvert, double\-cliquez sur **Table de chaînes** dans la fenêtre qui répertorie les types de ressources pour votre application.  Avec l'éditeur de **Table de chaînes** ouvert, choisissez **Nouvelle chaîne** dans le menu **Insert** .  Dans la fenêtre de propriétés de chaîne, sélectionnez l'ID de commande du volet \(par exemple, `ID_INDICATOR_PAGE`\) et tapez une valeur de chaîne par défaut, telle que « page ».  Fermez l'éditeur de chaîne. \(Vous avez besoin d'une chaîne par défaut pour éviter une erreur de compilation.\)  
  
3.  Ajoutez le volet au tableau d'**indicators**.  
  
     Dans le fichier MAINFRM.CPP, recherchez le tableau d'**indicators**.  Ces tableaux listent les ID de commande pour tous les indicateurs de barre d'état, de gauche à droite.  Au point approprié dans le tableau, entrez l'ID de commande du volet, comme indiqué ici pour `ID_INDICATOR_PAGE`:  
  
     [!code-cpp[NVC_MFCDocView#10](../mfc/codesnippet/CPP/updating-the-text-of-a-status-bar-pane_1.cpp)]  
  
 La méthode recommandée d'affichage du texte dans le volet consiste à appeler la méthode **SetText** de la classe `CCmdUI` dans une fonction de gestionnaire de mise à jour du volet.  Par exemple, vous pouvez vouloir placer une variable de type entier `m_nPage` qui contient le numéro de page et utilise **SetText** pour définir le texte du volet vers une version en chaîne de cette valeur.  
  
> [!NOTE]
>  La méthode **SetText** est recommandée.  Il est possible d'effectuer cette tâche à un niveau légèrement inférieur en appelant la méthode `SetPaneText`de `CStatusBar`.  Toutefois, vous avez toujours besoin d'un gestionnaire de mise à jour.  Sans ce gestionnaire pour le volet, MFC désactive automatiquement le volet, effaçant son contenu.  
  
 La procédure suivante montre comment utiliser une fonction du gestionnaire de mise à jour pour afficher du texte dans le volet.  
  
#### Pour qu'un volet affiche du texte  
  
1.  Ajoutez un gestionnaire de mise à jour de commande pour la commande.  
  
     Ajoutez manuellement un prototype du gestionnaire, comme indiqué ici pour `ID_INDICATOR_PAGE` \(dans MAINFRM.H\) :  
  
     [!code-cpp[NVC_MFCDocView#11](../mfc/codesnippet/CPP/updating-the-text-of-a-status-bar-pane_2.h)]  
  
2.  Dans le fichier .cpp adapté, ajoutez la définition du gestionnaire, comme indiqué ici pour `ID_INDICATOR_PAGE` \(dans MAINFRM.CPP\) :  
  
     [!code-cpp[NVC_MFCDocView#12](../mfc/codesnippet/CPP/updating-the-text-of-a-status-bar-pane_3.cpp)]  
  
     Les trois dernières lignes de ce gestionnaire sont le code qui affiche le texte.  
  
3.  Dans la table des messages appropriée, ajoutez la macro `ON_UPDATE_COMMAND_UI`, comme indiqué ici pour `ID_INDICATOR_PAGE` \(dans MAINFRM.CPP\) :  
  
     [!code-cpp[NVC_MFCDocView#13](../mfc/codesnippet/CPP/updating-the-text-of-a-status-bar-pane_4.cpp)]  
  
 Une fois que vous donnez une valeur à l'attribut `m_nPage` \(classe `CMainFrame`\), cette technique fait que le numéro de page apparaît dans le volet au cours du traitement du temps d'inactivité de la même façon que l'application met à jour d'autres indicateurs.  Si `m_nPage` change, l'affichage change durant la boucle inactive suivante.  
  
### Sur quels éléments souhaitez\-vous obtenir des informations supplémentaires ?  
  
-   [Mise à jour des objets d'interface utilisateur \(comment mettre à jour les boutons des barres d'outils et les éléments de menu comme modification des états de programme\)](../mfc/how-to-update-user-interface-objects.md)  
  
## Voir aussi  
 [Implémentation de la barre d'état dans MFC](../mfc/status-bar-implementation-in-mfc.md)   
 [CStatusBar Class](../mfc/reference/cstatusbar-class.md)