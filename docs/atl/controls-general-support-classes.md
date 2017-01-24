---
title: "Controls: General Support Classes | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.atl.controls"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "controls [ATL]"
  - "general support classes"
ms.assetid: cf73f1d2-7542-48e3-b8c8-9d3abf29f85b
caps.latest.revision: 12
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Controls: General Support Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes suivantes fournissent la prise en charge général des contrôles ATL :  
  
-   [CComControl](../atl/reference/ccomcontrol-class.md) se compose des fonctions d'assistance et les données membres qui sont essentielles à ATL contrôle.  
  
-   [IOleControlImpl](../atl/reference/iolecontrolimpl-class.md) fournit des méthodes nécessaires pour les contrôles.  
  
-   [IOleObjectImpl](../atl/reference/ioleobjectimpl-class.md) fournit les principales méthodes dans lesquelles un conteneur communique avec un contrôle.  Gère l'activation et la mise hors fonction de les contrôles sur place.  
  
-   Initialisation de regroupe d'[IQuickActivateImpl](../atl/reference/iquickactivateimpl-class.md) dans un seul appel pour aider les conteneurs pour éviter des délais lorsque contrôles de charge.  
  
-   [IPointerInactiveImpl](../atl/reference/ipointerinactiveimpl-class.md) fournit l'interaction souris minimale pour un contrôle être inactif.  
  
## Exemple de programme  
 [ATLFire](../top/visual-cpp-samples.md)  
  
## Articles connexes  
 [Didacticiel ATL](../atl/active-template-library-atl-tutorial.md)  
  
## Voir aussi  
 [Class Overview](../atl/atl-class-overview.md)