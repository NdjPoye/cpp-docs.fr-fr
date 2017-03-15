---
title: "Gestionnaires pour les plages de table des messages | Microsoft Docs"
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
  - "gestion des commandes, gestionnaires de mise à jour des commandes"
  - "ID de commande, mappage des messages"
  - "routage des commandes, gestionnaires de mise à jour des commandes"
  - "gestionnaires de mise à jour des commandes"
  - "messages de notification de contrôle"
  - "contrôles (MFC), notifications"
  - "fonctions gestionnaires"
  - "fonctions gestionnaires, déclarer"
  - "fonctions gestionnaires, plages des tables des messages"
  - "gestionnaires"
  - "gestionnaires, plages des tables des messages"
  - "mappages, plages des messages"
  - "gestionnaires de messages"
  - "gestion des messages, gestionnaire de messages (fonctions)"
  - "tables des messages, gestionnaire de messages (fonctions)"
  - "tables des messages, plages"
  - "plages des messages"
  - "plages des messages, mapper"
  - "plages des tables des messages"
ms.assetid: a271478b-5e1c-46f5-9f29-e5be44b27d08
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Gestionnaires pour les plages de table des messages
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Cet article explique comment mapper une plage des messages à une seule fonction gestionnaire des messages \(au lieu du message d'un mappage à une seule fonction\).  
  
 Il arrive que vous devez traiter plusieurs notifications de message ou le contrôle de la même manière.  Dans de tels cas, vous pouvez mapper tous les messages d'une seule fonction gestionnaire.  Les chaînes de table des messages vous permettent de procéder pour une plage contigue des messages :  
  
-   Vous pouvez mapper les plages des ID de commande :  
  
    -   Une fonction de responsable de commandes.  
  
    -   Une fonction du conseiller de mise à jour de commande.  
  
-   Vous pouvez mapper les messages de notification contrôle pour une plage des ID de contrôle dans une fonction gestionnaire des messages.  
  
 Les rubriques traitées dans cet article sont les suivantes :  
  
-   [Écriture de l'entrée de la table des messages](#_core_writing_the_message.2d.map_entry)  
  
-   [États la fonction gestionnaire](#_core_declaring_the_handler_function)  
  
-   [Exemple d'une plage d'ID de commande](#_core_example_for_a_range_of_command_ids)  
  
-   [Exemple d'une plage d'ID de contrôle.](#_core_example_for_a_range_of_control_ids)  
  
##  <a name="_core_writing_the_message.2d.map_entry"></a> Écriture de l'entrée du mappage des messages  
 Dans le fichier .cpp, ajoutez l'entrée de la table des messages, comme le montre l'exemple suivant :  
  
 [!code-cpp[NVC_MFCMessageHandling#6](../mfc/codesnippet/CPP/handlers-for-message-map-ranges_1.cpp)]  
  
 L'entrée de la table des messages incluent les éléments suivants :  
  
-   La macro de la plage de table des messages :  
  
    -   [ON\_COMMAND\_RANGE](../Topic/ON_COMMAND_RANGE.md)  
  
    -   [ON\_UPDATE\_COMMAND\_UI\_RANGE](../Topic/ON_UPDATE_COMMAND_UI_RANGE.md)  
  
    -   [ON\_CONTROL\_RANGE](../Topic/ON_CONTROL_RANGE.md)  
  
-   Paramètres de la macro :  
  
     Les deux premières macros prennent trois paramètres :  
  
    -   ID de commande qui engage la plage  
  
    -   ID de commande qui termine la plage  
  
    -   Le nom de la fonction gestionnaire des messages  
  
     La plage des ID de commande doit être contigue.  
  
     La troisième macro, `ON_CONTROL_RANGE`, accepte un premier paramètre supplémentaire : un message de notification contrôle, tel que **EN\_CHANGE**.  
  
##  <a name="_core_declaring_the_handler_function"></a> Déclare la fonction gestionnaire  
 Ajoutez votre déclaration de fonction gestionnaire de rôles dans. Fichier de H.  Le code suivant montre comment il peut le consulter, comme indiqué ci\-dessous :  
  
 [!code-cpp[NVC_MFCMessageHandling#7](../mfc/codesnippet/CPP/handlers-for-message-map-ranges_2.h)]  
  
 Les fonctions de gestion pour chaques commandes ne prennent pas de paramètres en général.  À l'exception de les fonctions du gestionnaire de mise à jour, les fonctions et pour les plages de table des messages requièrent un paramètre supplémentaire, `nID`, de type **UINT**.  Ce paramètre est le premier paramètre.  Le paramètre supplémentaire s'adapte à l'ID de commande supplémentaire requis pour spécifier quelle commande l'utilisateur a réellement choisi.  
  
 Pour plus d'informations sur les spécifications de paramètre pour mettre à jour les fonctions et, consultez [Exemple d'une plage d'ID de commande](#_core_example_for_a_range_of_command_ids).  
  
##  <a name="_core_example_for_a_range_of_command_ids"></a> Exemple d'une portée d'ID de commande  
 Quand pourrez\-vous utiliser ces plages ?  Un exemple est dans commandes de gestion tels que l'ordre de zoom dans l'exemple [HIERSVR](../top/visual-cpp-samples.md)de MFC.  Cette commande zoome la vue, la mise à l'échelle est comprise entre 25% et 300% de sa taille normale.  La classe d'affichage de HIERSVR utilise une plage pour gérer les commandes de zoom avec une entrée de la table des messages ressemblant à ceci :  
  
 [!code-cpp[NVC_MFCMessageHandling#8](../mfc/codesnippet/CPP/handlers-for-message-map-ranges_3.cpp)]  
  
 Lorsque vous entrez l'entrée du mappage des messages, spécifiez :  
  
-   Deux ID de commande, débute et fin de commande d'une plage contigue.  
  
     Ici ils sont `ID_VIEW_ZOOM25` et `ID_VIEW_ZOOM300`.  
  
-   Le nom de la fonction gestionnaire pour la commande.  
  
     Ici il s'agit `OnZoom`.  
  
 La déclaration de fonction ressemblerait à ceci :  
  
 [!code-cpp[NVC_MFCMessageHandling#9](../mfc/codesnippet/CPP/handlers-for-message-map-ranges_4.h)]  
  
 Le cas de la mise à jour des fonctions de gestions est similaire, et supposé être bien plus utile.  Il est assez fréquent d'écrire des gestionnaires de `ON_UPDATE_COMMAND_UI` pour plusieurs commandes et de recherche en écriture, ou en copiant le même code de façon répétée.  La solution consiste à mapper une plage d'ID d'ordre à une fonction du conseiller de mise à jour à l'aide de la macro de `ON_UPDATE_COMMAND_UI_RANGE`.  Les ID de commande doivent constituer une plage contigue.  Pour obtenir un exemple, consultez le gestionnaire de **OnUpdateZoom** et de son entrée de la table des messages de `ON_UPDATE_COMMAND_UI_RANGE` de la classe d'affichage de l'exemple de HIERSVR.  
  
 Les fonctionnalités du conseiller de mise à jour pour les commandes prennent généralement un seul paramètre, `pCmdUI`, de type **CCmdUI\***.  Contrairement aux fonctions, et les fonctionnalités du conseiller de mise à jour pour les plages de table des messages ne requièrent pas un paramètre supplémentaire, `nID`, de type **UINT**.  ID de commande, qui est nécessaire pour spécifier quelle commande l'utilisateur a choisi, se trouve dans l'objet de `CCmdUI`.  
  
##  <a name="_core_example_for_a_range_of_control_ids"></a> Exemple d'une plage d'ID de contrôle.  
 Un autre cas intéressant mappe les messages de notification de contrôle pour une plage des ID de contrôle à un seul gestionnaire.  Supposons que l'utilisateur peut cliquer sur l'un des 10 boutons.  Pour mapper chacun des 10 boutons à un responsable, votre entrée de la table des messages ressemblerait à ceci :  
  
 [!code-cpp[NVC_MFCMessageHandling#10](../mfc/codesnippet/CPP/handlers-for-message-map-ranges_5.cpp)]  
  
 Lorsque vous entrez la macro de `ON_CONTROL_RANGE` dans la table des messages, spécifiez :  
  
-   Un message particulier de contrôle de notification.  
  
     Ici il s'agit **BN\_CLICKED**.  
  
-   Les valeurs d'ID du contrôle associées à la plage contigue des contrôles.  
  
     Ici ce sont `IDC_BUTTON1` et `IDC_BUTTON10`.  
  
-   Le nom de la fonction gestionnaire des messages.  
  
     Ici il s'agit `OnButtonClicked`.  
  
 Lorsque vous entrez la fonction gestionnaire, spécifiez le paramètre supplémentaire de **UINT**, comme suit :  
  
 [!code-cpp[NVC_MFCMessageHandling#11](../mfc/codesnippet/CPP/handlers-for-message-map-ranges_6.cpp)]  
  
 Le gestionnaire de `OnButtonClicked` pour un seul message de **BN\_CLICKED** ne requiert aucun paramètre.  Le même gestionnaire pour une plage de boutons prend un **UINT**.  Le paramètre supplémentaire permet d'identifier le contrôle particulier chargé de générer un message de **BN\_CLICKED**.  
  
 Le code présenté dans l'exemple de scénario : la conversion de la valeur passée à `int` dans la plage de message et déclarer que c'est le cas.  Vous pouvez effectuer certaines mesures différente selon le bouton sur lequel l'utilisateur a cliqué.  
  
## Voir aussi  
 [Déclaration des fonctions de gestionnaire de messages](../mfc/declaring-message-handler-functions.md)