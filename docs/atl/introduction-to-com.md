---
title: "Introduction to COM | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "index-page "
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "COM"
ms.assetid: 120735d9-db71-4ad3-a730-ce576ea2354e
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Introduction to COM
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

COM est « modèle objet » fondamental sur les contrôles ActiveX et OLE est généré.  COM permet à un objet d'exposer ses fonctionnalités à d'autres composants et d'héberger des applications.  Il définit comment l'objet s'expose et comment cette surface s'exécute à travers des processus et entre les réseaux.  COM définit également le cycle de vie de l'objet.  
  
 Le principe fondamental à COM sont ces concepts :  
  
-   [interfaces](../atl/interfaces-atl.md) — le mécanisme par lequel un objet expose ses fonctionnalités.  
  
-   [IUnknown](../atl/iunknown.md) — l'interface de base dans lequel tous les autres sont basés.  Elle implémente le décompte de références et l'interface interrogeant les mécanismes de l'exécution via COM.  
  
-   [décompte de références](../atl/reference-counting.md) — la technique par laquelle un objet \(ou, strictement, une interface\) décide lorsqu'il est plus utilisé et n'est donc libre de le supprimer.  
  
-   [QueryInterface](../atl/queryinterface.md) — la méthode utilisée pour interroger un objet pour une interface spécifiée.  
  
-   [marshaler](../atl/marshaling.md) — le mécanisme qui permet aux objets d'être utilisés sur le thread, le processus, et les frontières réseau, tenant compte de l'indépendance d'emplacement.  
  
-   [regroupement](../atl/aggregation.md) — une méthode dans lequel l'objet peut utiliser des autres.  
  
## Voir aussi  
 [Introduction to COM and ATL](../atl/introduction-to-com-and-atl.md)   
 [The Component Object Model](http://msdn.microsoft.com/library/windows/desktop/ms694363)