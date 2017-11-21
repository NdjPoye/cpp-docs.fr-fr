---
title: "Contrôles ATL : Classes de prise en charge général | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-windows
ms.tgt_pltfrm: 
ms.topic: article
f1_keywords: vc.atl.controls
dev_langs: C++
helpviewer_keywords:
- controls [ATL]
- general support classes
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
caps.latest.revision: "12"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.openlocfilehash: 5d969481874762c5eefeb805d954ffad6114033e
ms.sourcegitcommit: ebec1d449f2bd98aa851667c2bfeb7e27ce657b2
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 10/24/2017
---
# <a name="controls-general-support-classes"></a>Contrôles : Classes de prise en charge général
Les classes suivantes fournissent la prise en charge générale pour les contrôles ATL :  
  
-   [CComControl](../atl/reference/ccomcontrol-class.md) se compose de membres de données et des fonctions d’assistance qui sont essentielles à des contrôles ATL.  
  
-   [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) fournit les méthodes nécessaires pour les contrôles.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) fournit les méthodes principales par le biais duquel un conteneur communique avec un contrôle. Gère l’activation et la désactivation des contrôles de la place.  
  
-   [IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) combine l’initialisation en un seul appel pour éviter des retards lors du chargement de contrôles conteneurs.  
  
-   [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) fournit une interaction minimale de la souris pour un contrôle inactif dans le cas contraire.  
  
## <a name="sample-program"></a>Exemple de programme  
 [ATLFire](../visual-cpp-samples.md)  
  
## <a name="related-articles"></a>Articles connexes  
 [Didacticiel ATL](../atl/active-template-library-atl-tutorial.md)  
  
## <a name="see-also"></a>Voir aussi  
 [Vue d’ensemble de la classe](../atl/atl-class-overview.md)

