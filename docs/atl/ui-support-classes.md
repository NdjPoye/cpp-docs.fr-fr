---
title: "UI Support Classes | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.ui"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces utilisateur, ATL classes"
  - "interfaces utilisateur, support classes"
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# UI Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes suivantes fournissent la prise en charge général d'interface utilisateur :  
  
-   [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) une interface à l'analyse et au moteur de rendu HTML Microsoft.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) fournit les principales méthodes dans lesquelles un conteneur communique avec un contrôle.  Gère l'activation et la mise hors fonction de les contrôles sur place.  
  
-   [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md) gère la réactivation des contrôles sur place.  Permet à un contrôle sans fenêtre de recevoir des messages, ainsi que de participer aux opérations de glisser\-déplacer.  
  
-   [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md) permet la communication entre un contrôle sur place et son conteneur.  
  
-   [IViewObjectExImpl](../atl/reference/iviewobjecteximpl-class.md) permet à un contrôle d'afficher directement et d'informer le conteneur de modifications dans son affichage.  Fournit la prise en charge du dessin sans scintillement, les contrôles non rectangulaires et transparent, et le test d'atteinte.  
  
## Articles connexes  
 [Didacticiel ATL](../atl/active-template-library-atl-tutorial.md)  
  
## Voir aussi  
 [Class Overview](../atl/atl-class-overview.md)