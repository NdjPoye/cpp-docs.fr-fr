---
title: "Control Containment Classes | Microsoft Docs"
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
  - "vc.atl.controls.containment"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "control containment classes"
ms.assetid: e0812aee-c078-4ced-b967-247976552b9a
caps.latest.revision: 10
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Control Containment Classes
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les classes suivantes fournissent la prise en charge de relation contenant\-contenu pour héberger des contrôles :  
  
-   [CAxWindow](../atl/reference/caxwindow-class.md) fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX.  
  
-   [CAxWindow2T](../atl/reference/caxwindow2t-class.md) fournit des méthodes pour manipuler une fenêtre qui héberge un contrôle ActiveX et a également une prise en charge de l'hébergement des contrôles ActiveX autorisés.  
  
-   Appel d'[IAxWinAmbientDispatch](../atl/reference/iaxwinambientdispatch-interface.md) les méthodes sur cette interface pour définir les propriétés ambiantes disponibles pour un contrôle hébergé.  
  
-   Appel d'[IAxWinHostWindow](../atl/reference/iaxwinhostwindow-interface.md) les méthodes sur cette interface pour créer la liaison et\/ou un contrôle à un objet hôte, ou pour obtenir une interface d'un contrôle hébergé.  
  
## Articles connexes  
 [FAQ de contenance de contrôles ATL](../atl/atl-control-containment-faq.md)  
  
## Voir aussi  
 [Class Overview](../atl/atl-class-overview.md)