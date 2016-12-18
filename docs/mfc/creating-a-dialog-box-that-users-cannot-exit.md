---
title: "Creating a Dialog Box That Users Cannot Exit | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
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
  - "dialog boxes, creating"
  - "modal dialog boxes, logon screens"
  - "logon screens"
ms.assetid: 54823c27-1658-4388-bd12-0a1ce8f3899e
caps.latest.revision: 12
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Creating a Dialog Box That Users Cannot Exit
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez créer une boîte de dialogue d’exécution qu’un utilisateur ne peut pas quitter. Ce type de boîte de dialogue est utile pour les ouvertures de session et pour le verrouillage d’application ou de document.  
  
### Pour créer une boîte de dialogue qu’un utilisateur ne peut pas quitter  
  
1.  Dans le volet **Propriétés** de la boîte de dialogue, affectez la valeur **false** à la propriété **Menu système**.  
  
     Cela désactive le menu système de boîte de dialogue et le bouton **Fermer**.  
  
2.  Dans le formulaire de boîte de dialogue, supprimez les boutons **Annuler** et **OK**.  
  
     Au moment de l’exécution, l’utilisateur ne peut pas quitter une boîte de dialogue modale qui possède ces caractéristiques.  
  
 Pour pouvoir tester ce type de boîte de dialogue, la fonction de test de boîte de dialogue détecte la touche Échap. \(Échap porte également le nom de touche virtuelle VK\_ESCAPE.\) Quel que soit le comportement prévu de la boîte de dialogue au moment de l’exécution, vous pouvez la fermer en mode test en appuyant sur Échap.  
  
> [!NOTE]
>  Pour les applications MFC, pour créer une boîte de dialogue que les utilisateurs ne peuvent pas quitter, vous devez substituer le comportement par défaut de `OnOK`et `OnCancel`, car même si vous supprimez les boutons associés, la boîte de dialogue peut toujours être ignorée en appuyant sur Entrée ou Échap.  
  
 Pour plus d’informations sur la façon d’ajouter des ressources aux projets managés, consultez [Ressources dans des applications de bureau](../Topic/Resources%20in%20Desktop%20Apps.md).  
  
## Spécifications  
 Win32  
  
## Voir aussi  
 [How to: Create a Resource](../windows/how-to-create-a-resource.md)   
 [Resource Files](../mfc/resource-files-visual-studio.md)   
 [Dialog Editor](../mfc/dialog-editor.md)