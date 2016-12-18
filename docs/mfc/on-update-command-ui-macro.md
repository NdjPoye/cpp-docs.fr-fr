---
title: "ON_UPDATE_COMMAND_UI, macro | Microsoft Docs"
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
  - "ON_UPDATE_COMMAND_UI"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "gestionnaire de commandes (macros)"
  - "ON_UPDATE_COMMAND_UI (macro)"
  - "gestionnaires de mise à jour"
  - "mettre à jour des objets d'interface utilisateur"
ms.assetid: 3e72b50f-4119-4c82-81cf-6e09b132de05
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# ON_UPDATE_COMMAND_UI, macro
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Utilisez la fenêtre **Propriétés** pour connecter un objet d'interface utilisateur à un gestionnaire de mise à jour de commande dans un objet de cible de commande.  Il connecte automatiquement l'ID de l'objet interface utilisateur à la macro `ON_UPDATE_COMMAND_UI` et crée un gestionnaire dans l'objet qui gère la mise à jour.  Pour plus d'informations, consultez [Mappage de messages à des fonctions](../mfc/reference/mapping-messages-to-functions.md).  
  
 Par exemple, pour mettre à jour une commande Clear All dans le menu Edition de votre programme, utilisez la fenêtre **Propriétés** pour ajouter une entrée de la table des messages dans la classe, une déclaration de fonction d'un gestionnaire de mise à jour de commande appelé `OnUpdateEditClearAll` dans la déclaration de classe, ainsi qu'un modèle de fonction vide du fichier d'implémentation de la classe.  Le prototype de la fonction ressemble à ceci :  
  
 [!code-cpp[NVC_MFCDocView#2](../mfc/codesnippet/CPP/on-update-command-ui-macro_1.h)]  
  
 Comme tous les gestionnaires, la fonction indique le mot clé **afx\_msg**.  Comme tous les gestionnaires de mise à jour, elle prend un argument, un pointeur vers un objet `CCmdUI`.  
  
## Voir aussi  
 [Comment : mettre à jour des objets d'interface utilisateur](../mfc/how-to-update-user-interface-objects.md)