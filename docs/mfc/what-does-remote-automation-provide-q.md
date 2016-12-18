---
title: "Que fournit l&#39;automation &#224; distance&#160;? | Microsoft Docs"
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
  - "Automation à distance, DCOM"
ms.assetid: 269ad218-e164-40ef-9b87-25fcc8ba21de
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Que fournit l&#39;automation &#224; distance&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

L'automatisation à distance permet aux programmes d'invoquer les implémentations d' `IDispatch` sur un ordinateur à partir d'un autre.  Il prend également en charge d'autres interfaces nécessaires à l'automatisation, notamment **IEnumVARIANT** pour la prise en charge de la collection.  Elle ne fournit pas la possibilité de ne distribuer aucune autre interface COM \(sauf **IUnknown**naturellement\) et, comme l'automation standard, il contient la prise en charge de marshaling uniquement pour les types de données pris en charge par automation.  
  
 Cet ensemble de fonctionnalités permet à un programme d'accéder aux méthodes et propriétés, y compris celles qui retournent des collections ou des objets d'automation ultérieurs, d'un objet s'exécutant sur un nœud de réseau accessible.  Si l'ordinateur client exécute également le logiciel approprié, il est possible pour le serveur de rappeler le client, à nouveau à l'aide de les fonctionnalités d'automation \(ceci fonctionne pour les clients 32 bits et 64 bits uniquement, et est conceptuellement semblable aux événements, bien qu'il n'utilise pas le même mécanisme\).  
  
 Pour qu'une application soit fonctionnelle comme serveur d'automation à distance, elle doit être implémentée comme un fichier exécutable \(autrement dit, comme « serveur local » et non comme « serveur inproc »\).  
  
## Voir aussi  
 [Quand l'automation à distance convient\-elle ?](../mfc/where-does-remote-automation-fit-in-q.md)   
 [Historique de DCOM](../mfc/history-of-dcom.md)