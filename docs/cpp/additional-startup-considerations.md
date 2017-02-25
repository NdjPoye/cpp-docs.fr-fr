---
title: "Consid&#233;rations suppl&#233;mentaires sur le d&#233;marrage | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "initialiser avant principal"
  - "démarrage du programme (C++)"
  - "code de démarrage"
ms.assetid: 0e942aa6-8342-447c-b068-8980ed7622bd
caps.latest.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 6
---
# Consid&#233;rations suppl&#233;mentaires sur le d&#233;marrage
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

En langage C\+\+, la construction et la destruction d'objets peuvent impliquer l'exécution de code utilisateur.  Par conséquent, il est important de comprendre quelles initialisations ont lieu avant l'entrée dans **main** et quels destructeurs sont appelés après la sortie de **main**. \(Pour obtenir des informations détaillées sur la construction et la destruction d'objets, consultez [Constructeurs](../cpp/constructors-cpp.md) et [Destructeurs](../cpp/destructors-cpp.md).\)  
  
 Les initialisations suivantes ont lieu avant l'entrée dans **main** :  
  
-   Mise à zéro par défaut des données statiques.  Toutes les données statiques sans initialiseurs explicites sont mises à zéro avant d'exécuter tout autre code, y compris l'initialisation du runtime.  Les données membres statiques doivent encore être définies explicitement.  
  
-   Initialisation des objets statiques globaux dans une unité de traduction.  Cela peut se produire avant l'entrée dans **main** ou avant la première utilisation d'une fonction ou d'un objet quelconque dans l'unité de traduction de l'objet.  
  
 **Section spécifique à Microsoft**  
  
 Dans Microsoft C\+\+, les objets statiques globaux sont initialisés avant l'entrée dans **main**.  
  
 **FIN de la section spécifique à Microsoft**  
  
 Des objets statiques globaux mutuellement interdépendants mais figurant dans des unités de traduction distinctes peuvent provoquer un comportement incorrect.  
  
## Voir aussi  
 [Démarrage et terminaison](../cpp/startup-and-termination-cpp.md)