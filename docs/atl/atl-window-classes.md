---
title: "ATL, classes de fen&#234;tre | Microsoft Docs"
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
  - "ATL, fenêtres"
  - "sous-classer ATL (classes de fenêtre)"
  - "surclasser"
  - "surclasser, ATL"
  - "fenêtres (C++), ATL"
  - "fenêtres (C++), sous-classer"
  - "fenêtres (C++), surclasser"
ms.assetid: 1d12b708-de3e-49d5-9e41-42fe4769fa62
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 5
---
# ATL, classes de fen&#234;tre
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

ATL inclut plusieurs classes qui vous permettent à des fenêtres d'implémenter d'utiliser et.  Ces classes, comme d'autres classes ATL, fournissent une implémentation efficace qui n'applique pas une charge mémoire à votre code.  
  
 Cette section décrit les classes de fenêtres ATL et explique comment les utiliser.  
  
## Dans cette section  
 [Introduction aux classes de fenêtres ATL](../atl/introduction-to-atl-window-classes.md)  
 Décrit brièvement chaque classe de fenêtre ATL et fournit des liens vers une documentation de référence sur eux.  
  
 [Utilisation d'une fenêtre](../atl/using-a-window.md)  
 Explique comment utiliser `CWindow` pour manipuler une fenêtre.  
  
 [Implémentation d'une fenêtre](../atl/implementing-a-window.md)  
 Traite des gestionnaires de messages, les tables des messages, et utiliser `CWindowImpl`.  Inclut des informations sur superclassing et sous\-classement.  
  
 [implémenter une boîte de dialogue](../atl/implementing-a-dialog-box.md)  
 Présente les deux méthodes pour ajouter une classe de boîte de dialogue et montre un exemple de code.  
  
 [À l'aide de les fenêtres contenues](../atl/using-contained-windows.md)  
 Discusses contient les fenêtres dans ATL, qui sont des fenêtres qui délèguent leurs messages à un objet conteneur au lieu de les gérer dans leur propre classe.  
  
 [Traits de fenêtre de présentation](../atl/understanding-window-traits.md)  
 Décrit les classes de traits de fenêtre dans ATL.  Ces classes fournissent une méthode simple pour standardiser les styles utilisés pour la création d'un objet window.  
  
## Rubriques connexes  
 [ATL](../atl/active-template-library-atl-concepts.md)  
 Fournit des liens vers des rubriques conceptuelles sur comment programmer avec la bibliothèque ATL.  
  
 [Classes de prise en charge windows](../atl/windows-support-classes.md)  
 Répertorie les classes supplémentaires ATL qui prennent en charge les fenêtres et les tables des messages dans ATL.