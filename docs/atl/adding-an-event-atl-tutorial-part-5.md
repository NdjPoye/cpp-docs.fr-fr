---
title: "Ajout d&#39;un &#233;v&#233;nement (Didacticiel ATL, Partie&#160;5) | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
ms.assetid: 2de12022-3148-4ce3-8606-8a9d4274f0e9
caps.latest.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Ajout d&#39;un &#233;v&#233;nement (Didacticiel ATL, Partie&#160;5)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans cette étape, vous ajouterez `ClickIn` et un événement d' `ClickOut` à votre contrôle ATL.  Vous déclencherez l'événement d' `ClickIn` si l'utilisateur clique sur dans le polygone et du feu `ClickOut` si l'utilisateur clique sur en dehors de.  Les tâches d'ajouter un événement sont les suivantes :  
  
-   Ajouter des méthodes d' `ClickIn` et d' `ClickOut`  
  
-   Générer la bibliothèque de types  
  
-   Implémenter les interfaces de points de connexion  
  
## Ajouter les méthodes de ClickIn et de ClickOut  
 Lorsque vous avez créé le contrôle ATL à l'étape 2, vous avez activé la case à cocher **Points de connexion** .  Cela a créé l'interface d' `_IPolyCtlEvents` dans le fichier de Polygon.idl.  Notez que le nom de l'interface commence par un trait de soulignement.  Il s'agit d'une convention pour indiquer que l'interface est une interface interne.  Par conséquent, les programmes qui vous permettent de parcourir les objets COM peuvent choisir de ne pas afficher l'interface à l'utilisateur.  Notez également que sélectionne **Points de connexion** ajout de la ligne suivante dans le fichier de Polygon.idl pour indiquer qu' `_IPolyCtlEvents` est l'interface source par défaut :  
  
 `[default, source] dispinterface _IPolyCtlEvents;`  
  
 L'attribut source indique que le contrôle est la source des notifications, il appellera cette interface dans le conteneur.  
  
 Ajoutez maintenant `ClickIn` et les méthodes d' `ClickOut` à `_IPolyCtlEvents` avec onglets.  
  
#### Pour ajouter les méthodes de ClickIn et de ClickOut  
  
1.  Dans l'Affichage de classes, développez le polygone et le PolygonLib pour afficher des \_IPolyCtlEvents.  
  
2.  Cliquez avec le bouton droit sur les \_IPolyCtlEvents.  Dans le menu contextuel, cliquez sur **Ajouter**, puis sur **Ajouter une méthode**.  
  
3.  Sélectionnez **Type de retour** d' `void`.  
  
4.  Entrez `ClickIn` dans la zone **Nom de la méthode** .  
  
5.  Sous **attributs de paramètre**, sélectionnez la zone **dans** .  
  
6.  Sélectionnez **Type de paramètre** d' `LONG`.  
  
7.  Tapez `X` comme **Nom du paramètre**, puis cliquez sur **Ajouter**.  
  
8.  Répétez les étapes 5 à 7, cette fois pour **Nom du paramètre** de Est.  
  
9. Cliquez sur **Suivant**.  
  
10. Tapez `méthode ClickIn` comme **helpstring**.  
  
11. Cliquez sur **Terminer**.  
  
12. Répétez les étapes ci\-dessus pour définir une méthode d' `ClickOut` avec les mêmes paramètres d' `LONG``x` et `y`, même **attributs de paramètre** et le même type de retour d' `void` .  
  
 Vérifiez le fichier de Polygon.idl pour vérifier que le code a été ajouté à la dispinterface d' `_IPolyCtlEvents` .  
  
 La dispinterface d' `_IPolyCtlEvents` dans votre fichier de Polygon.idl doit maintenant ressembler à ceci :  
  
 [!code-cpp[NVC_ATL_Windowing#56](../atl/codesnippet/CPP/adding-an-event-atl-tutorial-part-5_1.idl)]  
  
 Les méthodes d' `ClickIn` et d' `ClickOut` prennent les coordonnées x et y du point cliqué en tant que paramètres.  
  
## Générer la bibliothèque de types  
 Générez la bibliothèque de types à ce stade, car l'Assistant Point de connexion l'utilisera pour obtenir les informations qu'il doit générer une interface de point de connexion et une interface de conteneur de point de connexion pour votre contrôle.  
  
#### Pour générer la bibliothèque de types  
  
1.  Régénérez votre projet.  
  
     ou  
  
2.  Cliquez avec le bouton droit sur le fichier de Polygon.idl de solutions et cliquez sur **Compiler** dans le menu contextuel.  
  
 Cette commande crée le fichier de Polygon.tlb, qui est votre bibliothèque de types.  Le fichier de Polygon.tlb n'est pas visible de l'explorateur de solutions, car il s'agit d'un fichier binaire et ne peut pas être affiché ou modifié directement.  
  
## Implémenter les interfaces de points de connexion  
 Implémentez une interface de point de connexion et une interface de conteneur de point de connexion pour votre contrôle.  Dans COM, les événements sont implémentées via le mécanisme de points de connexion.  Pour recevoir des événements d'un objet COM, un conteneur établit une connexion consultative au point de connexion que l'objet COM implémente.  Étant donné qu'un objet COM peut avoir plusieurs points de connexion, l'objet COM implémente également une interface de conteneur de point de connexion.  \- Cette interface, le conteneur peut déterminer les points de connexion sont pris en charge.  
  
 l'interface qui implémente un point de connexion est appelée `IConnectionPoint`, et l'interface qui implémente un conteneur de point de connexion est appelée `IConnectionPointContainer`.  
  
 Pour aider à implémenter `IConnectionPoint`, vous utiliserez Assistant Implémentation d'un point de connexion.  Cet assistant génère l'interface d' `IConnectionPoint` en lisant votre bibliothèque de types et en implémentant une fonction pour chaque événement qui peut être déclenché.  
  
#### Pour utiliser l'Assistant Implémentation d'un point de connexion  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur la classe `CPolyCtl`de l'implémentation de votre contrôle.  
  
2.  Dans le menu contextuel, cliquez sur **Ajouter**, puis cliquez sur **Ajouter un point de connexion**.  
  
3.  `_IPolyCtlEvents` sélectionnez dans la liste **interfaces sources** et la double\-cliquez sur pour l'ajouter à la colonne **Points de connexion d'implémentation** .  Cliquez sur **Terminer**.  Une classe proxy pour le point de connexion est générée, dans ce cas, `CProxy_IPolyCtlEvents`.  
  
 Si vous regardez l'explorateur généré de fichier de \_IPolyCtlEvents\_CP.h de solutions, vous verrez qu'elle possède une classe appelée `CProxy_IPolyCtlEvents` qui dérive d' `IConnectionPointImpl`.  \_IPolyCtlEvents\_CP.h définit également les deux méthodes `Fire_ClickIn` et `Fire_ClickOut`, qui acceptent les deux paramètres de coordonnées.  Vous appelez ces méthodes lorsque vous souhaitez déclencher un événement de votre contrôle.  
  
 l'assistant a également ajouté `CProxy_PolyEvents` et `IConnectionPointContainerImpl` à la liste de l'héritage multiple de votre contrôle.  L'assistant `IConnectionPointContainer` également exposées pour vous en ajoutant des entrées appropriées au mappage COM.  
  
 Vous avez terminé vous implémentez le code pour prendre en charge des événements.  Maintenant, ajoutez du code pour déclencher des événements au moment approprié.  N'oubliez pas, vous allez déclencher un événement d' `ClickIn` ou d' `ClickOut` lorsque l'utilisateur clique sur le bouton gauche de la souris dans le contrôle.  Pour découvrir lorsque l'utilisateur clique sur le bouton, ajoutez un gestionnaire pour le message d' `WM_LBUTTONDOWN` .  
  
#### Pour ajouter un gestionnaire pour le message de WM\_LBUTTONDOWN  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur la classe de CPolyCtl et cliquez sur **Propriétés** dans le menu contextuel.  
  
2.  Dans la fenêtre **Propriétés** , cliquez sur l'icône **Messages** puis cliquez sur `WM_LBUTTONDOWN` de la liste à gauche.  
  
3.  Dans la liste déroulante qui apparaît, cliquez sur **\<Add\> OnLButtonDown**.  La déclaration de gestionnaire d' `OnLButtonDown` sera ajoutée à PolyCtl.h, et l'implémentation du gestionnaire sera ajoutée à PolyCtl.cpp.  
  
 Ensuite, modifiez le gestionnaire.  
  
#### Pour modifier la méthode d'OnLButtonDown  
  
1.  Modifiez le code qui comporte la méthode d' `OnLButtonDown` dans PolyCtl.cpp \(suppression du code défini par l'assistant\) afin qu'il ressemble à ceci :  
  
     [!code-cpp[NVC_ATL_Windowing#57](../atl/codesnippet/CPP/adding-an-event-atl-tutorial-part-5_2.cpp)]  
  
 Ce code utilise des points calculées dans la fonction d' `OnDraw` pour créer une zone qui détecte les clics de souris de l'utilisateur avec l'appel à `PtInRegion`.  
  
 Le paramètre d' `uMsg` est l'ID de message windows étant géré.  Cela vous permet d'avoir une fonction qui gère une plage de messages.  `wParam` et d' `lParam` sont les valeurs standard pour le message qui est géré.  Le paramètre bHandled vous permet de spécifier, que la fonction a géré le message ou pas.  Par défaut, la valeur est affectée à `TRUE` pour indiquer que la fonction a géré le message, mais vous pouvez le placer à `FALSE`.  Cela entraîne continuer ATL pour rechercher une autre fonction gestionnaire de messages pour envoyer un message à.  
  
## Génération et test du contrôle  
 Essayez à présent les événements.  Générez le contrôle et reprenez ActiveX Control Test Container.  Cette fois, affichez la fenêtre du journal des événements.  Pour router les événements dans la fenêtre Sortie, cliquez sur **Journalisation** le menu **Options** et sélectionnez **Journal dans la fenêtre Sortie**.  Insérez le contrôle et le test cliquant sur dans la fenêtre.  Notez qu' `ClickIn` est déclenché si vous cliquez à l'intérieur de le polygone rempli, et `ClickOut` est déclenché lorsque vous cliquez en dehors de celle\-ci.  
  
 Ensuite, vous allez ajouter une page de propriétés.  
  
 [Pour revenir à l'étape 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md) &#124; [Sur à l'étape 6](../atl/adding-a-property-page-atl-tutorial-part-6.md)  
  
## Voir aussi  
 [Didacticiel](../atl/active-template-library-atl-tutorial.md)