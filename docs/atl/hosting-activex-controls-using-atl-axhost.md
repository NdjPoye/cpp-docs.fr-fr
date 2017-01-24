---
title: "Hosting ActiveX Controls Using ATL AXHost | Microsoft Docs"
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
  - "contrôles ActiveX (C++), héberger"
  - "AXHost method"
  - "Calendar control (ActiveX)"
  - "Calendar control (ActiveX), hosting with ATL AXHost"
  - "CAxWindow2T class"
  - "héberger des contrôles ActiveX"
ms.assetid: 2c1200ec-effb-4814-820a-509519699468
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Hosting ActiveX Controls Using ATL AXHost
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'exemple de cette rubrique indique comment créer AXHost et comment héberger un contrôle ActiveX à l'aide de ATL autre fonctionne.  Il indique également comment accéder aux événements de contrôle et du récepteur \(à l'aide de [IDispEventImpl](../atl/reference/idispeventimpl-class.md)\) du contrôle hébergé.  L'exemple héberge le contrôle Calendar dans une fenêtre principale ou dans une fenêtre enfant.  
  
 Notez la définition du symbole d' `USE_METHOD` .  Vous pouvez modifier la valeur de ce symbole pour faire varier entre 1 et 8.  La valeur du symbole détermine comment le contrôle est créé :  
  
-   Pour les valeurs paires d' `USE_METHOD`, l'appel pour créer les sous\-classes hôte une fenêtre et le convertit en elle contrôlent l'hôte.  Pour les valeurs impaires, le code crée une fenêtre enfant qui agit comme un hôte.  
  
-   Pour les valeurs d' `USE_METHOD` entre 1 et 4, l'accès au contrôle et jambage descendant les événements sont accomplis dans l'appel qui crée également l'hôte.  Les valeurs comprises entre 5 et 8 questionnent l'hôte pour les interfaces et accrochent le récepteur.  
  
 Voici un résumé :  
  
|USE\_METHOD|Hôte|Accès de contrôle et descendant d'événements|Fonction présentée|  
|-----------------|----------|--------------------------------------------------|------------------------|  
|1|Fenêtre enfant|Une étape|CreateControlLicEx|  
|2|Fenêtre principale|Une étape|AtlAxCreateControlLicEx|  
|3|Fenêtre enfant|Une étape|CreateControlEx|  
|4|Fenêtre principale|Une étape|AtlAxCreateControlEx|  
|5|Fenêtre enfant|Plusieurs étapes|CreateControlLic|  
|6|Fenêtre principale|Plusieurs étapes|AtlAxCreateControlLic|  
|7|Fenêtre enfant|Plusieurs étapes|CreateControl|  
|8|Fenêtre principale|Plusieurs étapes|AtlAxCreateControl|  
  
 [!code-cpp[NVC_ATL_AxHost#1](../atl/codesnippet/CPP/hosting-activex-controls-using-atl-axhost_1.cpp)]  
  
## Voir aussi  
 [FAQ sur la relation contenant\-contenu des contrôles](../atl/atl-control-containment-faq.md)   
 [AtlAxCreateControl](../Topic/AtlAxCreateControl.md)   
 [AtlAxCreateControlEx](../Topic/AtlAxCreateControlEx.md)   
 [AtlAxCreateControlLic](../Topic/AtlAxCreateControlLic.md)   
 [AtlAxCreateControlLicEx](../Topic/AtlAxCreateControlLicEx.md)   
 [CAxWindow2T Class](../atl/reference/caxwindow2t-class.md)   
 [IAxWinHostWindowLic Interface](../atl/reference/iaxwinhostwindowlic-interface.md)