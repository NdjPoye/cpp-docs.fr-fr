---
title: "Adding Connection Points to an Object | Microsoft Docs"
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
  - "points de connexion (C++), ajouter aux objets ATL"
  - "Implement Connection Point ATL wizard"
ms.assetid: 843531be-4a36-4db0-9d54-e029b1a72a8b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Adding Connection Points to an Object
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

[Didacticiel ATL](../atl/active-template-library-atl-tutorial.md) montre comment créer un contrôle avec prise en charge des points de connexion, ajouter des événements, puis comment implémenter le point de connexion.  Points de connexion d'outils ATL à la classe d' [IConnectionPointImpl](../atl/reference/iconnectionpointimpl-class.md) .  
  
 Pour implémenter un point de connexion, vous avez deux possibilités :  
  
-   Implémentez votre propre source d'événement sortante, en ajoutant un point de connexion au contrôle ou à l'objet.  
  
-   Réutilisez une interface de point de connexion définie dans une autre bibliothèque de types.  
  
 Dans les deux cas, l'Assistant Implémentation d'un point de connexion utilise une bibliothèque de types pour effectuer son travail.  
  
### Pour ajouter un point de connexion à un contrôle ou un objet  
  
1.  Définissez une dispinterface dans le bloc bibliothèque du fichier .idl.  Si vous n'activez pas la prise en charge des points de connexion lorsque vous avez créé le contrôle avec l'Assistant Contrôle ATL, la dispinterface est déjà créée.  Si vous ne vous n'activez pas la prise en charge des points de connexion lorsque vous avez créé le contrôle, vous devez ajouter manuellement une dispinterface au fichier .idl.  Voici un exemple d'une dispinterface.  Les interfaces sortantes ne sont pas requises pour être des interfaces de dispatch mais de nombreux langages de script tels que VBScript et le JScript requièrent cela, les cet exemple utilise deux dispinterfaces :  
  
     [!code-cpp[NVC_ATL_Windowing#81](../atl/codesnippet/CPP/adding-connection-points-to-an-object_1.idl)]  
  
     Utilisez l'uuidgen.exe ou l'utilitaire de guidgen.exe pour générer un GUID.  
  
2.  Ajoutez la dispinterface comme l'interface d' `[default,source]` dans la coclasse pour l'objet dans le fichier .idl du projet.  Là encore, si vous n'activez pas la prise en charge des points de connexion lorsque vous avez créé le contrôle, l'Assistant Contrôle ATL crée l'entrée d' `[default,source`\].  Pour ajouter manuellement cette entrée, ajoutez la ligne en gras :  
  
     [!code-cpp[NVC_ATL_Windowing#82](../atl/codesnippet/CPP/adding-connection-points-to-an-object_2.idl)]  
  
     Consultez le fichier .idl dans l'exemple de [Circ](../top/visual-cpp-samples.md) ATL pour un exemple.  
  
3.  Utilisez l'Affichage de classes pour ajouter des méthodes et des propriétés à l'interface d'événement.  Cliquez avec le bouton droit sur la classe dans l'Affichage de classes, pointez sur **Ajouter** dans le menu contextuel, puis cliquez sur **AjouterConnection Point**.  
  
4.  Dans la zone de liste de **Source Interfaces** de l'Assistant Implémentation d'un point de connexion, **Project's interfaces**sélectionnez.  Si vous choisissez une interface pour votre contrôle et appuyez **OK**, vous :  
  
    -   Générez un fichier d'en\-tête avec une classe proxy d'événements qui implémente le code qui fera les appels sortants pour l'événement.  
  
    -   Ajoutez une entrée dans la table des points de connexion.  
  
     Vous obtiendrez également une liste de toutes les bibliothèques de types sur votre ordinateur.  Vous devez uniquement utiliser une de ces autres bibliothèques de types pour définir votre point de connexion si vous souhaitez implémenter le exactement la même interface sortante trouvée à une autre bibliothèque de types.  
  
### Pour réutiliser un point de connexion interface défini à une autre bibliothèque de types  
  
1.  Dans l'Affichage de classes, cliquez avec le bouton droit sur une classe qui implémente une macro de **BEGIN\_COM\_MAP** , pointez sur **Ajouter** dans le menu contextuel, puis cliquez sur **AjouterConnection Point**.  
  
2.  Dans l'Assistant Implémentation d'un point de connexion, sélectionnez une bibliothèque de types et une interface dans la bibliothèque de types et cliquez sur **Ajouter**.  
  
3.  Modifiez le fichier .idl à l'un ou l'autre :  
  
    -   Copiez la dispinterface à partir de le fichier .idl de l'objet de la source d'événements est utilisée.  
  
    -   Utilisez l'instruction d' **importlib** sur cette bibliothèque de types.  
  
## Voir aussi  
 [point de connexion](../atl/atl-connection-points.md)