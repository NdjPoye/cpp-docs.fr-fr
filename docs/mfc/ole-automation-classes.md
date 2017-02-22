---
title: "Classes Automation OLE | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.classes.ole"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "classes Automation"
  - "classes Automation, classes OLE"
  - "Automation, classes"
  - "OLE (Automation)"
  - "OLE (Automation), classes"
ms.assetid: 96e5372b-ff8a-4da1-933b-4d9bbf4dceb3
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Classes Automation OLE
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ces classes prennent en charge les clients Automation \(les applications qui contrôlent les autres applications\).  Les serveurs Automation \(applications qui peuvent être contrôlés par d'autres applications\) sont pris en charge par [tables de dispatch](../mfc/reference/dispatch-maps.md).  
  
 [COleDispatchDriver](../mfc/reference/coledispatchdriver-class.md)  
 Utilisé pour appeler des serveurs COM de votre client Automation.  En ajoutant une classe, cette classe est utilisée pour créer les classes de type sécurisé pour les serveurs COM qui fournissent une bibliothèque de types.  
  
 [COleDispatchException](../mfc/reference/coledispatchexception-class.md)  
 Une exception résultant d'une erreur pendant l'automation OLE.  Les exceptions d'automation sont levées par les serveurs COM et interceptées par les clients d'automation.  
  
## Voir aussi  
 [Vue d'ensemble des classes](../mfc/class-library-overview.md)