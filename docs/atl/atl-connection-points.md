---
title: "ATL, points de connexion | Microsoft Docs"
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
  - "ATL, points de connexion"
  - "points de connexion (C++), à propos des points de connexion"
  - "connexions, points de connexion"
ms.assetid: 17d76165-5f83-4f95-b36d-483821c247a1
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ATL, points de connexion
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Un objet connectable est un objet qui prend en charge les interfaces sortantes.  Une interface sortante permet à l'objet de communiquer avec un client.  Pour chaque interface sortante, l'objet connectable expose un point de connexion.  Chaque interface sortante est implémentée par un client sur un objet appelé récepteur.  
  
 ![Points de connexion](../atl/media/vc2zw31.png "vc2ZW31")  
  
 Chaque point de connexion prend en charge l'interface [IConnectionPoint](http://msdn.microsoft.com/library/windows/desktop/ms694318).  L'objet connectable expose ses points de connexion au client via l'interface [IConnectionPointContainer](http://msdn.microsoft.com/library/windows/desktop/ms683857).  
  
## Dans cette section  
 [Classes de point de connexion ATL](../atl/atl-connection-point-classes.md)  
 Décrit brièvement les classes ATL qui prennent en charge les points de connexion.  
  
 [Ajout de points de connexion à un objet](../atl/adding-connection-points-to-an-object.md)  
 Décrit les étapes à suivre pour ajouter des points de connexion à un objet.  
  
 [Exemple de point de connexion ATL](../atl/atl-connection-point-example.md)  
 Présente un exemple de déclaration de point de connexion.  
  
## Rubriques connexes  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Propose des liens vers des rubriques conceptuelles traitant de la programmation à l'aide de la bibliothèque ATL \(Active Template Library\).  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)