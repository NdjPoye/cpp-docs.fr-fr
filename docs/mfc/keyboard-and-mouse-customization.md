---
title: "Personnalisation du clavier et de la souris | Microsoft Docs"
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
  - "personnalisations, clavier et de souris (extensions MFC)"
  - "personnalisations de clavier et de souris (extensions MFC)"
ms.assetid: 1f789f1b-5f2e-4b11-b974-e3e2a2e49d82
caps.latest.revision: 23
caps.handback.revision: 19
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Personnalisation du clavier et de la souris
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

MFC permet à l'utilisateur de l'application de personnaliser la façon dont il gère le clavier et l'entrée de la souris.  L'utilisateur peut personnaliser l'entrée clavier en attribuant des raccourcis clavier aux commandes.  L'utilisateur peut également personnaliser l'entrée souris en sélectionnant la commande qui doit être exécutée lorsque l'utilisateur double\-clique sur dans les fenêtres spécifiques de l'application.  Cette rubrique explique comment personnaliser les entrées pour votre application.  
  
 Dans la boîte de dialogue **Personnalisation**, l'utilisateur peut modifier les contrôles personnalisés pour la souris et du clavier.  Pour afficher cette boîte de dialogue, l'utilisateur pointe sur **Personnaliser** dans le menu **Affichage** puis clique sur **Barres d'outils et ancrage**.  Dans la boîte de dialogue, l'utilisateur clique soit sur l'onglet de **Clavier** ou sur l'onglet de **Souris**.  
  
## Personnalisation du clavier  
 L'illustration suivante montre l'onglet **Clavier** de la boîte de dialogue **Personnalisation**.  
  
 ![Onglet Clavier de la boîte de dialogue Personnalisation](../mfc/media/mfcnextkeyboardtab.png "MFCNextKeyboardTab")  
Onglet personnalisation du clavier  
  
 L'utilisateur interagit avec l'onglet clavier pour affecter un ou plusieurs raccourcis clavier à une commande.  Les commandes disponibles sont répertoriées sur le côté gauche de l'onglet.  L'utilisateur peut choisir n'importe quelle commande disponible dans le menu.  Seules les commandes de menu peuvent être associées à un raccourci clavier.  Une fois que l'utilisateur entre le raccourci, le bouton **Assign** devient actif.  Lorsque l'utilisateur clique sur ce bouton, l'application associe la commande sélectionnée à ce raccourci.  
  
 Tous les raccourcis clavier actuellement assignés sont répertoriés dans la zone de liste dans la colonne de droite.  L'utilisateur peut également sélectionner des raccourcis et les supprimer, ou réinitialiser tous les mappages de l'application.  
  
 Si vous voulez prendre en charge la personnalisation dans votre application, vous devez créer un objet [CKeyboardManager](../mfc/reference/ckeyboardmanager-class.md).  Pour créer un objet `CKeyboardManager`, appelez la fonction [CWinAppEx::InitKeyboardManager](../Topic/CWinAppEx::InitKeyboardManager.md).  Cette méthode crée et initialise un gestionnaire de clavier.  Si vous créez un gestionnaire de clavier manuellement, vous devez toujours appeler `CWinAppEx::InitKeyboardManager` pour l'initialisation.  
  
 Si vous utilisez l'Assistant pour créer votre application, il initialisera le gestionnaire de clavier.  Une fois que votre application a initialisé le gestionnaire de clavier, le framework ajoute un onglet **Clavier** à la boîte de dialogue **Personnalisation**.  
  
## Personnalisation de la souris  
 L'illustration suivante montre l'onglet **Souris** de la boîte de dialogue **Personnalisation**.  
  
 ![Onglet Souris de la boîte de dialogue Personnalisation](../mfc/media/mfcnextmousetab.png "MFCNextMouseTab")  
Onglet de personnalisation de la souris  
  
 L'utilisateur interagit avec cet onglet pour affecter une commande de menu à l'action de double\-clic de la souris.  L'utilisateur sélectionne une vue sur le côté gauche de la fenêtre puis utilise les contrôles à droite pour associer une commande à l'action de double\-clic.  Lorsque l'utilisateur clique sur **Fermer**, l'application exécute la commande associée à chaque fois que l'utilisateur double\-clique n'importe où dans la vue.  
  
 Par défaut, la personnalisation de la souris n'est pas activée lorsque vous créez une application à l'aide de l'Assistant.  
  
#### Pour activer la personnalisation de la souris  
  
1.  Initialisez un objet [CMouseManager](../mfc/reference/cmousemanager-class.md) en appelant [CWinAppEx::InitMouseManager](../Topic/CWinAppEx::InitMouseManager.md).  
  
2.  Obtenez un pointeur vers le gestionnaire de la souris à l'aide de [CWinAppEx::GetMouseManager](../Topic/CWinAppEx::GetMouseManager.md).  
  
3.  Ajoutez des vues dans le gestionnaire de souris en utilisant la méthode [CMouseManager::AddView](../Topic/CMouseManager::AddView.md).  Effectuez cette opération pour chaque vue que vous souhaitez ajouter au gestionnaire de souris.  
  
 Une fois que votre application a initialisé le gestionnaire de la souris, le framework ajoute l'onglet de **Souris** à la boîte de dialogue **Personnaliser**.  Si vous n'ajoutez pas de vue, l'accès de l'onglet génère une exception non gérée.  Après avoir créé une liste de vues, l'onglet de **Souris** est disponible pour l'utilisateur.  
  
 Lorsque vous ajoutez une nouvelle vue au gestionnaire de souris, vous lui attribuez un ID unique  Si vous voulez prendre en charge la personnalisation de la souris pour un point, vous devez traiter le message `WM_LBUTTONDBLCLICK` et appeler la fonction [CWinAppEx::OnViewDoubleClick](../Topic/CWinAppEx::OnViewDoubleClick.md).  Lorsque vous appelez cette fonction, l'un des paramètres est l'ID de cette fenêtre.  Il est de la responsabilité des programmeurs de conserver les numéros d'identification et les objets associés.  
  
## Considérations relatives à la sécurité  
 Comme décrit dans [Outils définis par l'utilisateur](../mfc/user-defined-tools.md), l'utilisateur peut associer un identificateur défini par l'utilisateur de l'outil à l'événement de double\-clic.  Lorsque l'utilisateur double\-clique sur une vue, l'application recherche un outil utilisateur qui correspond à l'ID associé.  Si l'application trouve un outil correspondant, il exécute l'outil.  Si l'application ne trouve pas d'outil correspondant, il envoie un message WM\_COMMAND avec l'ID de la vue sur laquelle a eu lieu le double\-clic.  
  
 Les paramètres personnalisés sont stockés dans le Registre.  En modifiant le Registre, un pirate peut remplacer un ID de l'outil d'utilisateur valide avec un ordre aléatoire.  Lorsque l'utilisateur double\-clique sur une vue, la vue traite l'ordre dans lequel la personne malveillante a attaquée.  Cela peut entraîner un comportement inattendu et potentiellement dangereux.  
  
 En outre, ce type d'attaque peut contourner les dispositifs de protection de l'interface utilisateur.  Par exemple, imaginez qu'une application où l'impression est désactivée.  Autrement dit, dans l'interface utilisateur, le menu **Imprimer** et son bouton ne sont pas disponibles.  Normalement cela empêche l'application d'imprimer.  Mais si un intrus a modifié le Registre, un utilisateur peut maintenant envoyer la commande imprimer directement en double\-cliquant sur la vue, en ignorant les éléments d'interface utilisateur qui ne sont pas disponibles.  
  
 Pour vous protéger contre ce type d'attaque, ajoutez du code à votre gestionnaire de commandes d'application pour vérifier qu'une commande est valide avant son exécution.  Ne dépendez pas de l'interface utilisateur pour éviter qu'une commande soit envoyée à l'application.  
  
## Voir aussi  
 [Personnalisation pour MFC](../mfc/customization-for-mfc.md)   
 [CKeyboardManager Class](../mfc/reference/ckeyboardmanager-class.md)   
 [CMouseManager Class](../mfc/reference/cmousemanager-class.md)   
 [Implications en matière de sécurité de la personnalisation](../mfc/security-implications-of-customization.md)