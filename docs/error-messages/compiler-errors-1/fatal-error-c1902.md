---
title: "Erreur irr&#233;cup&#233;rable C1902 | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1902"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1902"
ms.assetid: 2dc066cc-fcb1-4725-8bcb-9f44dd0905b7
caps.latest.revision: 13
caps.handback.revision: 13
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1902
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

incompatibilité de gestionnaire de bases de données du programme ; veuillez vérifier votre installation  
  
 Un fichier de base de données du programme \(.pdb\) a été créé à l'aide d'une version plus récente de mspdb*XX*.dll que celle que le compilateur a trouvé sur votre système.  Cette erreur indique habituellement que mspdbsrv.exe ou mspdbcore.dll sont manquants ou ont des versions différentes de mspdb*XX*.dll. \(L'espace réservé *XX* dans le nom de fichier de mspdb*XX*.dll change avec chaque version finale du produit.  Par exemple, dans [!INCLUDE[vsprvslong](../../error-messages/compiler-errors-1/includes/vsprvslong_md.md)], le nom de fichier est mspdb80.dll..  
  
 Assurez\-vous que les versions correspondantes de mspdbsrv.exe, mspdbcore.dll et mspdb*XX*.dll sont installées sur votre système.  Assurez\-vous que des versions incompatibles n'ont pas été copiées vers le répertoire qui contient le compilateur et les outils LINK pour votre plateforme cible.  Par exemple, vous auriez pu copier les fichiers et ainsi appeler le compilateur ou l'outil LINK à partir de l'invite de commandes sans définir la variable d'environnement **PATH** en conséquence.