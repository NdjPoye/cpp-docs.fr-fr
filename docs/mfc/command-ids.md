---
title: "ID de commande | Microsoft Docs"
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
  - "ID de commande"
  - "ID de commande, MFC"
ms.assetid: e0171a2b-45b9-41fa-945d-ec2f7602ded0
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ID de commande
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Une commande est entièrement décrite par son seul ID de commande \(encodé dans le message de **WM\_COMMAND** \).  Cet ID est affecté à l'objet interface utilisateur qui génère la commande.  En règle générale, les ID sont nommés pour les fonctionnalités de l'objet interface utilisateur auxquelles elles sont affectées.  
  
 Par exemple, un élément "Tout Effacer" dans le menu Edition peut affecter un ID comme **ID\_EDIT\_CLEAR\_ALL**.  La bibliothèque de classes prédéfinit des ID, en particulier pour les commandes que l'infrastructure gère lui\-même, telles que **ID\_EDIT\_CLEAR\_ALL** ou `ID_FILE_OPEN`.  Vous allez créer d'autres ID de commande vous\-même.  
  
 Lorsque vous créez vos propres menus dans l'éditeur de menu de Visual C\+\+, il est judicieux de suivre la convention d'affectation des noms de la bibliothèque de classes comme illustré par `ID_FILE_OPEN`.  [Commandes standard](../mfc/standard-commands.md) explique les commandes standard définies par la bibliothèque de classes.  
  
## Voir aussi  
 [Objets d'interface utilisateur et ID de commande](../mfc/user-interface-objects-and-command-ids.md)