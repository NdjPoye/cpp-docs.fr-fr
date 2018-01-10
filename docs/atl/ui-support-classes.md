---
title: "Classes de prise en charge de l’interface utilisateur (ATL) | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.ui
dev_langs: C++
helpviewer_keywords:
- user interfaces, support classes
- user interfaces, ATL classes
ms.assetid: 313dfc95-308a-4118-b919-5a3c3673b865
caps.latest.revision: "10"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 717e6cfc00c3d2442426698d910baac3c7fcb829
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="ui-support-classes"></a>Classes de prise en charge de l’interface utilisateur
Les classes suivantes fournissent la prise en charge de l’interface utilisateur générale :  
  
-   [IDocHostUIHandlerDispatch](../atl/reference/idochostuihandlerdispatch-interface.md) une interface avec le moteur de rendu et l’analyse HTML de Microsoft.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) fournit les méthodes principales par le biais duquel un conteneur communique avec un contrôle. Gère l’activation et la désactivation des contrôles de la place.  
  
-   [IOleInPlaceObjectWindowlessImpl](../atl/reference/ioleinplaceobjectwindowlessimpl-class.md) gère la réactivation des contrôles de la place. Permet à un contrôle sans fenêtre pour recevoir des messages, ainsi que pour participer aux opérations de glisser-déplacer.  
  
-   [IOleInPlaceActiveObjectImpl](../atl/reference/ioleinplaceactiveobjectimpl-class.md) vous aide à la communication entre un contrôle sur place et son conteneur.  
  
-   [IViewObjectExImpl](../atl/reference/iviewobjecteximpl-class.md) permet à un contrôle à afficher directement et pour notifier au conteneur des modifications de son affichage. Prend en charge sans scintillement dessin, les contrôles non rectangulaires et transparentes et le test de positionnement.  
  
## <a name="related-articles"></a>Articles connexes  
 [Didacticiel ATL](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../atl/atl-class-overview.md)

