---
title: "Prise en charge ATL pour les contr&#244;les DHTML | Microsoft Docs"
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
  - "DHTML (contrôles)"
  - "DHTML (contrôles), ATL (prise en charge)"
  - "contrôles HTML, ATL (prise en charge)"
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Prise en charge ATL pour les contr&#244;les DHTML
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

À l'aide de ATL, vous pouvez créer un contrôle à la fonction dynamique HTML \(DHTML\).  Un contrôle ATL DHTML :  
  
-   Héberge le contrôle WebBrowser.  
  
-   Spécifie, en utilisant HTML, l'interface utilisateur \(UI\) du contrôle DHTML.  
  
-   Accède à l'objet WebBrowser et à ses méthodes à son interface, [IWebBrowser2](https://msdn.microsoft.com/en-us/library/aa752127.aspx).  
  
-   Gère la communication entre le code C\+\+ et HTML.  
  
 Un contrôle DHTML est semblable à tout autre contrôle ATL, à moins que le contrôle DHTML inclut une interface de dispatch supplémentaire.  Voir la figure dans [Identifier les éléments du projet de contrôle DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) pour une illustration des interfaces fournies dans le DHTML par défaut pour un projet.  
  
 Vous pouvez afficher le contrôle ATL DHTML dans un navigateur web ou un autre conteneur, comme ActiveX Control Test Container.  
  
## Dans cette section  
 [Identifier les éléments du projet de contrôle DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 Décrit les éléments d'un projet de contrôle DHTML.  
  
 [Code C\+\+ appelant DHTML](../atl/calling-cpp-code-from-dhtml.md)  
 Fournit un exemple d'appeler le code C\+\+ d'un contrôle DHTML.  
  
 [Créer un contrôle ATL DHTML](../atl/creating-an-atl-dhtml-control.md)  
 Répertorie les étapes pour créer un contrôle DHTML.  
  
 [Tester le contrôle ATL DHTML](../atl/testing-the-atl-dhtml-control.md)  
 Montre comment générer et tester le projet de contrôle DHTML initiale.  
  
 [Modifier le contrôle ATL DHTML](../atl/modifying-the-atl-dhtml-control.md)  
 Montre comment ajouter certaines fonctionnalités au contrôle.  
  
 [Tester le contrôle modifié ATL DHTML](../atl/testing-the-modified-atl-dhtml-control.md)  
 Montre comment générer et tester la fonctionnalité ajoutée du contrôle.  
  
## Rubriques connexes  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Fournit des liens vers des rubriques conceptuelles sur comment programmer avec la bibliothèque ATL.