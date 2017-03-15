---
title: "Types de messages associ&#233;s aux objets interface utilisateur | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.codewiz.uiobject.msgs"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "types de messages et objets de l'interface utilisateur"
ms.assetid: 681ee1a7-f6e6-4ea0-9fc6-1fb53a35516e
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Types de messages associ&#233;s aux objets interface utilisateur
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le tableau suivant indique les types d'objets que vous pouvez utiliser et les types de messages qui leur sont associés.  
  
### Objets interface utilisateur et messages associés  
  
|ID d'objet|Messages|  
|----------------|--------------|  
|Nom de la classe, représentant la fenêtre contenante|Messages Windows appropriés pour une classe dérivée de [CWnd](../../mfc/reference/cwnd-class.md) : boîte de dialogue, fenêtre, fenêtre enfant, fenêtre enfant MDI ou fenêtre frame située au premier plan.|  
|Identificateur de menu ou d'accélérateur|-   Message **COMMAND** \(exécute la fonction de programme\).<br />-   Message **UPDATE\_COMMAND\_UI** \(met à jour l'élément de menu de manière dynamique\).|  
|Identificateur de contrôle|Messages de notification de contrôle pour le type de contrôle sélectionné.|  
  
## Voir aussi  
 [Mappage de messages à des fonctions](../../mfc/reference/mapping-messages-to-functions.md)   
 [Ajout de fonctionnalités à l'aide des Assistants Code](../../ide/adding-functionality-with-code-wizards-cpp.md)   
 [Ajout d'une classe](../../ide/adding-a-class-visual-cpp.md)   
 [Ajout d'une fonction membre](../../ide/adding-a-member-function-visual-cpp.md)   
 [Ajout d'une variable membre](../../ide/adding-a-member-variable-visual-cpp.md)   
 [Substitution d'une fonction virtuelle](../../ide/overriding-a-virtual-function-visual-cpp.md)   
 [MFC, gestionnaire de messages](../../mfc/reference/adding-an-mfc-message-handler.md)   
 [Parcours de la structure de classe](../../ide/navigating-the-class-structure-visual-cpp.md)