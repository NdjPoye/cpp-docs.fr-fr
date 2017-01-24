---
title: "Pages de propri&#233;t&#233;s ATL COM | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "ATL COM (objets)"
  - "ATL (pages de propriétés)"
  - "objets COM, ATL"
  - "COM (pages de propriétés)"
  - "pages de propriétés, ATL"
  - "pages de propriétés, COM"
ms.assetid: 663c7caa-2e5e-4b5c-b8ea-fd434ceb1654
caps.latest.revision: 13
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Pages de propri&#233;t&#233;s ATL COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les pages de propriétés COM fournissent une interface utilisateur pour définir les propriétés \(ou appeler les méthodes\) d'un ou plusieurs objets COM.  Les pages de propriétés sont largement utilisées par les contrôles ActiveX pour la fourniture des interfaces utilisateur élaborées qui permettent aux propriétés de contrôle à définir au moment de le design.  
  
 Les pages de propriétés sont des objets COM qui implémentent l'interface d' [IPropertyPage](http://msdn.microsoft.com/library/windows/desktop/ms691246) ou d' [IPropertyPage2](http://msdn.microsoft.com/library/windows/desktop/ms683996) .  Ces interfaces fournissent des méthodes qui permettent la page à associer à `site` \(un objet COM qui représente le conteneur de la page\) et plusieurs *objets* \(les objets COM dont les méthodes sont appelées en réponse à les modifications apportées par l'utilisateur de la page de propriétés\).  Le conteneur de page de propriétés est responsable des méthodes sur l'interface de page de propriétés pour indiquer la page lorsque afficher ou masquer son interface utilisateur, et quand appliquer les modifications apportées par l'utilisateur aux objets sous\-jacents.  
  
 Chaque page de propriétés peut être générée intégralement indépendamment des objets dont les propriétés peuvent être définies.  Tout de laquelle une page de propriétés a besoin est d'inclure une interface particulière \(ou l'ensemble d'interfaces\) et de fournir une interface utilisateur pour appeler des méthodes sur cette interface.  
  
 Pour plus d'informations, consultez [feuilles de propriétés et pages de propriétés](http://msdn.microsoft.com/library/windows/desktop/ms686577) dans [!INCLUDE[winSDK](../atl/includes/winsdk_md.md)].  
  
## Dans cette section  
 [Spécifier les pages de propriétés](../atl/specifying-property-pages.md)  
 Répertorie les étapes pour spécifier des pages de propriétés à votre contrôle et illustre une classe d'exemple.  
  
 [implémenter des pages de propriétés](../atl/implementing-property-pages.md)  
 Répertorie les étapes pour implémenter des pages de propriétés, notamment des méthodes pour substituer.  Promenades vous présente un exemple complet en fonction de l'exemple de programme ATLPages.  
  
## Rubriques connexes  
 [Exemple ATLPages](../top/visual-cpp-samples.md)  
 L'exemple abrégé sur pour l'exemple ATLPages, qui implémente une page de propriétés à l'aide de `IPropertyPageImpl`.  
  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Fournit des liens vers des rubriques conceptuelles sur comment programmer avec la bibliothèque ATL.  
  
## Voir aussi  
 [Concepts](../atl/active-template-library-atl-concepts.md)