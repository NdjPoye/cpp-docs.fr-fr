---
title: "Marshaling | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "interfaces COM, marshaling"
  - "marshaling"
  - "marshaling, COM Interop"
ms.assetid: 40644b0a-1106-4fc8-9dfb-9bee9915d825
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Marshaling
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La technique COM du marshaling fournit des interfaces exposées par un objet dans un processus à utiliser dans un autre processus.  Dans le marshaling, COM fournit le code \(ou le code d'utilisation fourni par l'implémenteur d'interface\) les deux pour compresser les paramètres d'une méthode dans un format qui peut être déplacé à travers des processus \(ainsi que, entre le thread aux processus qui s'exécutent sur d'autres ordinateurs quitter\) et ces paramètres à l'autre extrémité.  De même, COM doit exécuter ces mêmes étapes au retour de l'appel.  
  
> [!NOTE]
>  Le marshaling n'est généralement pas nécessaire lorsqu'une interface fournie par un objet est utilisée dans le même processus que l'objet.  Toutefois, le marshaling peut être nécessaire entre les threads.  
  
## Voir aussi  
 [Introduction to COM](../atl/introduction-to-com.md)   
 [Marshaling Details](http://msdn.microsoft.com/library/windows/desktop/ms692621)