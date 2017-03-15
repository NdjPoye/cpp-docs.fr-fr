---
title: "Inscription de classes de fen&#234;tre | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "WndProc"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "AfxRegisterWndClass (méthode)"
  - "classes (C++), inscrire des classes de fenêtre"
  - "MFC, fenêtres"
  - "inscrire des classes de fenêtre"
  - "Registre, inscrire des classes"
  - "classes de fenêtre, inscrire"
  - "WinMain (méthode)"
  - "WinMain (méthode), et inscrire des classes de fenêtre"
  - "WndProc (méthode)"
ms.assetid: 30994bc4-a362-43da-bcc5-1bf67a3fc929
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# Inscription de classes de fen&#234;tre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La fenêtre « classes » dans la programmation traditionnelle pour Windows définit les caractéristiques d'une « classe » \(classe non en C\+\+\) à partir de laquelle autant de fenêtres que l'on souhaite peuvent être créées.  Ce type de classe est un modèle ou un modèle pour créer des fenêtres.  
  
## Enregistrement de la fenêtre classe dans des programmes traditionnels pour Windows  
 Dans un programme traditionnel pour Windows, sans MFC, vous traitez les messages dans une fenêtre de sa « procédure de fenêtre » ou «**WndProc** ». Un **WndProc** est associé à une fenêtre au moyen d'un processus d'« alignement de la fenêtre de classe ».  La fenêtre principale est stockée dans la fonction d' `WinMain`, mais d'autres classes de fenêtres peuvent être stockées n'importe où dans l'application.  L'enregistrement dépend d'une structure qui contient un pointeur vers la fonction de **WndProc** avec les caractéristiques du curseur, pinceau d'arrière\-plan, etc.  La structure est passée comme paramètre, ainsi que le nom de chaîne de la classe, dans un appel antérieur à la fonction de **RegisterClass**.  Par conséquent, une classe d'enregistrement peut être partagée par plusieurs fenêtres.  
  
## Enregistrement de la classe de fenêtre dans les programmes de MFC  
 En revanche, la plupart des activités d'enregistrement de la classe de fenêtre sont effectuées automatiquement dans un programme\-framework MFC.  Si vous utilisez MFC, vous dérivez généralement la classe de fenêtre en C\+\+ à partir d'une classe existante de bibliothèque à l'aide de la syntaxe régulière C\+\+ pour l'héritage de la classe.  L'infrastructure utilise toujours les «classes d'inscription » traditionnelles, et elle en fournit plusieurs standard, inscrites automatiquement en cas de besoin.  Vous pouvez stocker les classes d'enregistrement en appelant la fonction globale [AfxRegisterWndClass](../Topic/AfxRegisterWndClass.md) puis en passant la classe enregistrée dans la fonction membre **Créer** d' `CWnd`.  Comme indiqué ici, la "classe d'enregistrement" classique dans Windows ne doit pas être confondue avec une classe en C\+\+.  
  
 Pour plus d'informations, consultez [Note Technique 1](../mfc/tn001-window-class-registration.md).  
  
## Voir aussi  
 [Création de fenêtres](../mfc/creating-windows.md)