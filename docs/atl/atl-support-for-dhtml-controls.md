---
title: "Prise en charge ATL pour les contrôles DHTML | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
dev_langs:
- C++
helpviewer_keywords:
- HTML controls, ATL support
- DHTML controls, ATL support
- DHTML controls
ms.assetid: 4ba98098-da5d-4362-96ad-8372f816c307
caps.latest.revision: 
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload:
- cplusplus
ms.openlocfilehash: ab796752cef10c48036966c2947d711a0e385032
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="atl-support-for-dhtml-controls"></a>Prise en charge ATL pour les contrôles DHTML
ATL, vous pouvez créer un contrôle avec la fonctionnalité de Dynamic HTML (DHTML). Un contrôle ATL DHTML :  
  
-   Héberge le contrôle WebBrowser.  
  
-   Spécifie, à l’aide de HTML, l’interface utilisateur (IU) du contrôle DHTML.  
  
-   Accède à l’objet WebBrowser et ses méthodes via son interface, [IWebBrowser2](https://msdn.microsoft.com/library/aa752127.aspx).  
  
-   Gère la communication entre le code C++ et HTML.  
  
 Un contrôle DHTML est similaire à n’importe quel autre contrôle ATL, excepté le contrôle DHTML comprend une interface de dispatch supplémentaire. Voir la figure dans [identifier les éléments du projet de contrôle DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md) pour obtenir une illustration des interfaces fournies dans le projet DHTML par défaut.  
  
 Vous pouvez afficher le contrôle ATL DHTML dans un navigateur Web ou un autre conteneur, telles que ActiveX Control Test Container.  
  
## <a name="in-this-section"></a>Dans cette section  
 [Identification des éléments du projet de contrôle DHTML](../atl/identifying-the-elements-of-the-dhtml-control-project.md)  
 Décrit les éléments d’un projet de contrôle DHTML.  
  
 [Appel de code C++ à partir de DHTML](../atl/calling-cpp-code-from-dhtml.md)  
 Fournit un exemple d’appel de code C++ à partir d’un contrôle DHTML.  
  
 [Création d’un contrôle ATL DHTML](../atl/creating-an-atl-dhtml-control.md)  
 Répertorie les étapes de création d’un contrôle DHTML.  
  
 [Test du contrôle ATL DHTML](../atl/testing-the-atl-dhtml-control.md)  
 Montre comment générer et tester le projet de contrôle DHTML initial.  
  
 [Modification du contrôle ATL DHTML](../atl/modifying-the-atl-dhtml-control.md)  
 Montre comment ajouter des fonctionnalités au contrôle.  
  
 [Test du contrôle modifiée ATL DHTML](../atl/testing-the-modified-atl-dhtml-control.md)  
 Montre comment générer et tester la fonctionnalité ajoutée au contrôle.  
  
## <a name="related-sections"></a>Rubriques connexes  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Propose des liens vers des rubriques conceptuelles traitant de la programmation à l'aide de la bibliothèque ATL (Active Template Library).

