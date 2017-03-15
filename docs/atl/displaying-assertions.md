---
title: "Displaying Assertions | Microsoft Docs"
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
  - "assertions, débogage"
  - "assertions, afficher"
  - "déboguer (ATL), displaying assertions"
  - "déboguer les assertions"
ms.assetid: fa353fe8-4656-4384-a5d2-8866bc977f06
caps.latest.revision: 11
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Displaying Assertions
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si le client connecté à votre service est cesser de répondre, le service peut avoir affirmé et affiche un message que vous ne pouvez pas consulter.  Vous pouvez confirmer ceci à l'aide de le débogueur Visual C\+\+ pour déboguer votre code \(consultez [À l'aide de le gestionnaire de tâches](../atl/using-task-manager.md) précédemment dans cette section\).  
  
 Si vous déterminez que votre service affiche un message que vous ne voyez pas, vous pouvez définir l'option de **Autoriser le service à interagir avec le Bureau** avant d'utiliser le service de nouveau.  Cette option est un paramètre de démarrage qui autorise tous les messages affichés par le service à afficher sur le Bureau.  Pour définir cette option, ouvrez l'application du panneau de configuration des services, sélectionnez le service, cliquez sur **Démarrage**, puis sélectionnez l'option de **Autoriser le service à interagir avec le Bureau** .  
  
## Voir aussi  
 [Debugging Tips](../atl/debugging-tips.md)