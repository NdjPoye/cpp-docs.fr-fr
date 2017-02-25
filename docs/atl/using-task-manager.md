---
title: "Using Task Manager | Microsoft Docs"
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
  - "points d'arrêt, Task Manager"
  - "déboguer (ATL), using Task Manager"
  - "Task Manager"
ms.assetid: 773fccd5-308d-42c2-a17f-60ae94989062
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Using Task Manager
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une des solutions les plus simples de déboguer un service est l'utilisation du gestionnaire des tâches de Windows NT 4,0 ou Windows 2000.  Lorsque le service s'exécute, démarrez le gestionnaire de tâches et cliquez sur **Processus** tableau.  Cliquez avec le bouton droit sur le nom du fichier EXE puis cliquez sur **Déboguer**.  Cette opération lance Visual C\+\+ joint à ce processus en cours de exécution.  Maintenant, cliquez sur **Arrêter** dans le menu de **Déboguer** pour vous permettre aux points d'arrêt de positionnement dans votre code.  Cliquez sur **Run** pour exécuter à vos points d'arrêt sélectionnés.  
  
## Voir aussi  
 [Debugging Tips](../atl/debugging-tips.md)