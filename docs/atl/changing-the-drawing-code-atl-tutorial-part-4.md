---
title: "Changement du code de dessin (Didacticiel ATL, partie&#160;4) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "get-started-article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "_ATL_MIN_CRT (macro)"
ms.assetid: 08ff14e8-aa49-4139-a110-5d071939cf1e
caps.latest.revision: 18
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Changement du code de dessin (Didacticiel ATL, partie&#160;4)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Par défaut, le code de dessin du contrôle affiche un carré et le texte **PolyCtl**.  Dans cette étape, vous allez modifier le code pour afficher un nom plus intéressante.  Les tâches suivantes sont impliqués :  
  
-   Modifier le fichier d'en\-tête  
  
-   Modifier la fonction d' `OnDraw`  
  
-   Ajouter une méthode pour calculer les points polygon  
  
-   Initialiser la couleur de remplissage  
  
## Modifier le fichier d'en\-tête  
 Commencez par ajouter la prise en charge des fonctions mathématiques `sin` et `cos`, qui seront utilisés calculent les points de polygone, et en créant un tableau pour stocker des positions.  
  
#### Pour modifier le fichier d'en\-tête  
  
1.  Ajoutez la ligne `#include <math.h>` en haut de PolyCtl.h.  Le début du fichier doit ressembler à ceci :  
  
     [!code-cpp[NVC_ATL_Windowing#47](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_1.cpp)]  
  
2.  Une fois les points polygon sont calculées, ils seront stockés dans un tableau de type `POINT`par conséquent, ajoutez le tableau après la définition d' `m_nSides` dans PolyCtl.h :  
  
     [!code-cpp[NVC_ATL_Windowing#48](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_2.h)]  
  
## Modifier la méthode d'OnDraw  
 Maintenant vous devez modifier la méthode d' `OnDraw` dans PolyCtl.h.  Le code que vous ajouterez crée un stylet et le pinceau avec lequel dessiner le polygone, puis appelle `Ellipse` et l'API Win32 d' `Polygon` fonctionne pour effectuer le dessin proprement dit.  
  
#### Pour modifier la fonction d'OnDraw  
  
1.  Remplacez la méthode existante d' `OnDraw` dans PolyCtl.h par le code suivant :  
  
     [!code-cpp[NVC_ATL_Windowing#49](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_3.cpp)]  
  
## Ajouter une méthode pour calculer les points polygon  
 Ajoutez une méthode, `CalcPoints`appelé, qui calculera les coordonnées des points qui composent le périmètre de le polygone.  Ces calculs sont basés sur la variable RECT passé dans la fonction.  
  
#### Pour ajouter la méthode de CalcPoints  
  
1.  Ajoutez la déclaration d' `CalcPoints` à la section publique d' `IPolyCtl` de la classe d' `CPolyCtl` dans PolyCtl.h :  
  
     [!code-cpp[NVC_ATL_Windowing#50](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_4.h)]  
  
     La dernière partie de la section publique de la classe d' `CPolyCtl` se présentera comme suit :  
  
     [!code-cpp[NVC_ATL_Windowing#51](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_5.h)]  
  
2.  Ajoutez cette implémentation de la fonction d' `CalcPoints` à la fin de PolyCtl.cpp :  
  
     [!code-cpp[NVC_ATL_Windowing#52](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_6.cpp)]  
  
## Initialiser la couleur de remplissage  
 Initialisez `m_clrFillColor` avec une couleur par défaut.  
  
#### Pour initialiser la couleur de remplissage  
  
1.  Utilisez le vert comme la couleur par défaut en ajoutant cette ligne au constructeur d' `CPolyCtl` dans PolyCtl.h :  
  
     [!code-cpp[NVC_ATL_Windowing#53](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_7.h)]  
  
 Recherche de constructeur maintenant comme suit :  
  
 [!code-cpp[NVC_ATL_Windowing#54](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_8.h)]  
  
## Génération et test du contrôle  
 Régénérez le contrôle.  Assurez \-vous que le fichier PolyCtl.htm est fermé s'il est ouvert, puis cliquez sur **Générez le polygone** dans le menu **Générer** .  Vous pouvez afficher le contrôle à nouveau de la page PolyCtl.htm, mais cette utilisation de fois ActiveX Control Test Container.  
  
#### Pour utiliser ActiveX Control Test Container  
  
1.  Générez et démarrez ActiveX Control Test Container.  Pour plus d'informations, consultez l' [Exemple TSTCON : ActiveX Control Test Container](../top/visual-cpp-samples.md).  
  
2.  Dans l'outil Test Container, dans le menu **Modifier** , cliquez sur **Contrôle d'insertion**.  
  
3.  Localisez votre contrôle, qui sera appelé `PolyCtl Class`, puis cliquez sur **OK**.  Vous verrez un triangle vert dans un cercle.  
  
 Essayez de modifier le nombre de côtés en suivant la procédure suivante.  Pour modifier des propriétés sur une interface double de Test Container, utilisez **Invoke Methods**.  
  
#### Pour modifier la propriété d'un contrôle de Test Container  
  
1.  Dans l'outil Test Container, cliquez sur **appelez les méthodes** dans le menu **contrôle** .  
  
     La boîte de dialogue **appelez la méthode** s'affiche.  
  
2.  Sélectionnez la version d' **PropPut** de la propriété d' **Sides** de la zone de liste déroulante **Nom de la méthode** .  
  
3.  Tapez `5` dans la zone **Valeur du paramètre** , cliquez sur **Valeur Set**, puis cliquez sur **Appeler**.  
  
 Notez que le contrôle ne change pas.  Bien que vous ayez modifié le nombre de côtés en interne en définissant la variable d' `m_nSides` , cela n'a pas effectué la redessiner le contrôle.  Si vous basculez vers une autre application puis basculez vers Test Container, vous constaterez que le contrôle est redessiné et a le nombre correct de côté.  
  
 Pour résoudre ce problème, ajoutez un appel à la fonction d' `FireViewChange` , définie dans `IViewObjectExImpl`, après avoir défini le nombre de côtés.  Si le contrôle s'exécute dans sa propre fenêtre, `FireViewChange` appelle la méthode d' `InvalidateRect` directement.  Si le contrôle est exécuter sans fenêtre, la méthode d' `InvalidateRect` sera appelée sur l'interface du site du conteneur.  Cela force le contrôle se repeindre.  
  
#### Pour ajouter un appel à FireViewChange  
  
1.  Mettez à jour PolyCtl.cpp en ajoutant l'appel à `FireViewChange` à la méthode d' `put_Sides` .  Lorsque vous avez terminé, la méthode d' `put_Sides` doit ressembler à ceci :  
  
     [!code-cpp[NVC_ATL_Windowing#55](../atl/codesnippet/CPP/changing-the-drawing-code-atl-tutorial-part-4_9.cpp)]  
  
 Après avoir ajouté `FireViewChange`, la régénération et testez le contrôle de nouveau dans ActiveX Control Test Container.  Ce moment où vous modifiez le nombre de côtés et cliquez sur `Invoke`, vous devez voir l'arrêt du contrôle immédiatement.  
  
 Dans l'étape suivante, vous allez ajouter un événement.  
  
 [Pour revenir à l'étape 3](../atl/adding-a-property-to-the-control-atl-tutorial-part-3.md) &#124; [Sur à l'étape 5](../atl/adding-an-event-atl-tutorial-part-5.md)  
  
## Voir aussi  
 [Didacticiel](../atl/active-template-library-atl-tutorial.md)   
 [Test des propriétés et des événements avec le conteneur de test](../mfc/testing-properties-and-events-with-test-container.md)