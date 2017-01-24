---
title: "Acc&#232;s de type s&#233;curis&#233; aux contr&#244;les avec Assistants Code | Microsoft Docs"
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
  - "Assistants Code"
  - "DDX (échange de données de boîtes de dialogue), accès aux contrôles"
  - "contrôles de boîte de dialogue, accéder"
  - "boîtes de dialogue, accès aux contrôles"
ms.assetid: b8874393-ee48-4124-8d78-e3648a7e29b9
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s de type s&#233;curis&#233; aux contr&#244;les avec Assistants Code
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Si vous connaissez bien les fonctionnalités de DDX, vous pouvez utiliser la propriété de contrôle dans l'[Assistant Ajout de variable membre](../ide/add-member-variable-wizard.md) pour créer un accès au type sécurisé.  Cette approche est plus facile que de créer des contrôles sans Assistants Code.  
  
 Si vous souhaitez simplement l'accès à la valeur d'un contrôle, DDX le fournit.  Si vous souhaitez effectuer plus d'accès à la valeur d'un contrôle, utilisez l'Assistant Ajout de variable membre pour ajouter une variable membre de la classe appropriée à votre classe de boîte de dialogue.  Attachez cette variable membre à la propriété de contrôle.  
  
 Les variables membres peuvent avoir une propriété de contrôle au lieu d'une propriété de valeur.  La propriété valeur correspond au type de données retourné par le contrôle, tel que `CString` ou `int`.  La propriété de contrôle permet l'accès direct au contrôle par l'intermédiaire d'une donnée membre dont le type est l'une des classes de contrôle de MFC, tel que `CButton` ou `CEdit`.  
  
> [!NOTE]
>  Pour un contrôle donné, vous pouvez, si vous le souhaitez, disposer de plusieurs variables membres avec une propriété de valeur et au plus une variable membre avec une propriété de contrôle.  Vous pouvez faire correspondre un seul objet de MFC à un contrôle car si plusieurs objets étaient associées à un contrôle, ou n'importe quelle autre fenêtre, cela mènerait à une ambiguïté dans la table des messages.  
  
 Vous pouvez utiliser l'objet pour appeler des fonctions membres pour l'objet de contrôle.  De tels appels affectent le contrôle dans la boîte de dialogue.  Par exemple, pour un contrôle CHECK Box représenté par une variable `m_Checkbox`, de type `CButton`, vous pouvez appeler :  
  
 [!code-cpp[NVC_MFCControlLadenDialog#52](../mfc/codesnippet/CPP/type-safe-access-to-controls-with-code-wizards_1.cpp)]  
  
 Ici la variable membre `m_Checkbox` sert le même fonction que la fonction membre `GetMyCheckbox` montrée dans [Accès de type sécurisé aux contrôles sans Assistant Code](../mfc/type-safe-access-to-controls-without-code-wizards.md).  Si la case à cocher n'est pas une case à cocher automatique, vous aurez toujours besoin d'un gestionnaire dans la classe de boîte de dialogue du message de notification de contrôle **BN\_CLICKED** lorsqu'un utilisateur clique sur le bouton.  
  
 Pour plus d'informations sur les contrôles personnalisés, consultez [Contrôles](../mfc/controls-mfc.md).  
  
## Voir aussi  
 [Accès de type sécurisé aux contrôles d'une boîte de dialogue](../mfc/type-safe-access-to-controls-in-a-dialog-box.md)   
 [Cycle de vie d'une boîte de dialogue](../mfc/life-cycle-of-a-dialog-box.md)   
 [Accès de type sécurisé aux contrôles sans Assistants Code](../mfc/type-safe-access-to-controls-without-code-wizards.md)