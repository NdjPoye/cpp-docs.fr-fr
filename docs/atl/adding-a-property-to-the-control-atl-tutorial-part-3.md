---
title: "Ajout d&#39;une propri&#233;t&#233; au contr&#244;le (Didacticiel ATL, Partie&#160;3) | Microsoft Docs"
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
ms.assetid: f775fe34-103b-4f07-9999-400e987ee030
caps.latest.revision: 15
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Ajout d&#39;une propri&#233;t&#233; au contr&#244;le (Didacticiel ATL, Partie&#160;3)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`IPolyCtl` est l'interface qui contient les méthodes et les propriétés du contrôle, et vous allez ajouter une propriété à celui\-ci.  
  
### Pour ajouter une propriété à l'aide de l'Assistant Ajout de propriété  
  
1.  Dans l'Affichage de classes, développez la branche polygon.  
  
2.  Cliquez avec le bouton droit sur IPolyCtl.  
  
3.  Dans le menu contextuel, cliquez sur **Ajouter**, puis cliquez sur **Ajouter une propriété**.  
  
     L'Assistant Ajout de propriété s'affiche.  
  
4.  Dans la liste déroulante de types de propriété, `SHORT`sélectionnez.  
  
5.  Tapez `Côté` comme **nom de la propriété.**  
  
6.  Cliquez sur **Terminé** pour terminer ajouter la propriété.  
  
 Lorsque vous ajoutez la propriété l'interface, MIDL \(le programme qui compile les fichiers .idl\) définit une méthode d' `Get` pour extraire sa valeur et une méthode d' `Put` pour définir une nouvelle valeur.  Les méthodes sont appelées en ajoutant `put_` et `get_` au nom de la propriété.  
  
 L'Assistant Ajout de propriété ajoute les lignes nécessaires au fichier .idl.  Il ajoute également des prototypes de fonction d' `Get` et d' `Put` à la définition de classe dans PolyCtl.h et ajoute une implémentation vide à PolyCtl.cpp.  Vous pouvez contrôler cela en ouvrant PolyCtl.cpp et en recherchant les fonctions `get_Sides` et `put_Sides`.  
  
 Bien que vous ayez maintenant des fonctions squelettiques pour définir et récupérer la propriété, elle a besoin d'un emplacement à être stocké.  Vous allez créer une variable pour stocker la propriété et mettre à jour les fonctions en conséquence.  
  
#### Pour créer une variable pour stocker la propriété, et pour gérer la mise et pour obtenir des méthodes  
  
1.  Dans l'explorateur de solutions, PolyCtl.h ouverts et ajoutez la ligne suivante après la définition d' `m_clrFillColor`:  
  
     [!code-cpp[NVC_ATL_Windowing#44](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_1.h)]  
  
2.  Affectez la valeur par défaut d' `m_nSides`.  Faites de la forme par défaut un triangle en ajoutant une ligne au constructeur dans PolyCtl.h :  
  
     [!code-cpp[NVC_ATL_Windowing#45](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_2.h)]  
  
3.  Implémentez les méthodes `Get` et `Put`.  Les déclarations de fonction d' `get_Sides` et d' `put_Sides` ont été ajoutées à PolyCtl.h.  Remplacez le code dans PolyCtl.cpp pour `get_Sides` et `put_Sides` par le code suivant :  
  
     [!code-cpp[NVC_ATL_Windowing#46](../atl/codesnippet/CPP/adding-a-property-to-the-control-atl-tutorial-part-3_3.cpp)]  
  
 La méthode d' `get_Sides` retourne la valeur actuelle de la propriété d' `Sides` via le pointeur d' `pVal` .  Dans la méthode d' `put_Sides` , le code vérifie l'utilisateur définit la propriété d' `Sides` à une valeur acceptable.  Le minimum doit être de 2, et parce qu'un tableau de points est utilisé pour chaque côté, 100 est une limite raisonnable pour une valeur maximale.  
  
 Vous avez maintenant une propriété appelée `Sides`.  Dans l'étape suivante, vous allez modifier le code de dessin à utiliser.  
  
 [Pour revenir à l'étape 2](../atl/adding-a-control-atl-tutorial-part-2.md) &#124; [Sur à l'étape 4](../atl/changing-the-drawing-code-atl-tutorial-part-4.md)  
  
## Voir aussi  
 [Didacticiel](../atl/active-template-library-atl-tutorial.md)