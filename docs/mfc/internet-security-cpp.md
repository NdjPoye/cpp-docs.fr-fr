---
title: "S&#233;curit&#233; Internet (C++) | Microsoft Docs"
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
  - "sécurité d'accès du code (C++), considérations relatives à la sécurité Internet"
  - "signature du code (C++)"
  - "signature du code (C++), sécurité Internet"
  - "signatures numériques, sécurité Internet"
  - "applications Internet, sécurité"
  - "sandboxing"
  - "sécurité (MFC)"
  - "sécurité (MFC), Internet"
  - "sécurité des applications Web"
  - "sécurité des applications Web, approches de la sécurité Internet"
ms.assetid: bf0da697-81bc-41f0-83fa-d7f82ed83df8
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# S&#233;curit&#233; Internet (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La sécurité du code est un problème majeur pour les développeurs et les utilisateurs des applications Web.  Il existe des risques : code malveillant, code qui a été falsifié, et code de sites ou d'auteurs inconnus.  
  
 Il existe deux approches de base pour la sécurité du développement sur Internet.  Le premier est appelé « sandboxing ». Dans cette approche, une application est limitée à un ensemble spécifique d'API, et exclue de ceux qui peuvent se révéler dangereux tel qu'un fichier E\/S où un programme pourrait détruire les données sur l'ordinateur d'un utilisateur.  Le deuxième est implémenté à l'aide de signatures numériques.  Cette approche est appelée « shrinkwrap » pour Internet.  Le code est extrait et archivé à l'aide de la technologie de clé privée\/clé publique.  Avant que le code soit exécuté, la signature numérique est vérifiée pour garantir que le code provient d'une source connue authentifiée, et que le code n'a pas été modifié vu qu'il a été signé.  
  
 Dans le premier cas, vous espérez que l'application ne causera pas de problème et vous faites confiance à l'origine de l'application.  Dans le second, les signatures numériques sont utilisées pour vérifier l'authenticité.  La signature numérique est une utilisation standard pour identifier et fournir des détails sur l'auteur du code.  Sa technologie est basés sur des normes, notamment RSA et X.509.  Les navigateurs permettent généralement aux utilisateurs de choisir s'ils souhaitent télécharger et exécuter les codes d'origines inconnues.  
  
 Des informations supplémentaires sur la signature de code et d'autres mesures de sécurité sont disponibles sur le Web.  Les informations sont accessibles via le site d'atelier Web de MSDN Online [http:\/\/msdn.microsoft.com\/](http://msdn.microsoft.com/), ou via World Wide Web Consortium à [http:\/\/www.w3.org\/](http://www.w3.org/).  
  
## Voir aussi  
 [Tâches de programmation Internet MFC](../mfc/mfc-internet-programming-tasks.md)   
 [Éléments fondamentaux relatifs à la programmation Internet MFC](../mfc/mfc-internet-programming-basics.md)