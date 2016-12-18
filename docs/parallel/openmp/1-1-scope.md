---
title: "1.1 Scope | Microsoft Docs"
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
ms.assetid: a8570a3c-1dd6-4c3d-b368-a10fcb3534a6
caps.latest.revision: 4
caps.handback.revision: 4
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# 1.1 Scope
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Cette spécification traite uniquement la parallélisation utilisateur\-dirigée, où l'utilisateur spécifie explicitement les actions à entreprendre par le compilateur et le système runtime pour exécuter le programme en parallèle.  Les implémentations d'OpenMP C et C\+\+ ne sont pas requises pour vérifier les dépendances, les conflits, les interblocages, les conditions de concurrence critique, ou d'autres problèmes qui ont provoqué l'exécution du programme incorrecte.  L'utilisateur doit garantir que l'application des éléments à OpenMP C et C\+\+ API exécute correctement.  La parallélisation automatique générée par le compilateur et les directives au compilateur d'aider une telle parallélisation \- couvertes dans ce document.