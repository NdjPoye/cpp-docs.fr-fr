---
title: "Compilation et liaison de programmes multithread | Microsoft Docs"
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
  - "compiler des programmes multithread"
  - "compiler le code source (C++), programmes multithread"
  - "liaison (C++), programmes multithread"
  - "multithreading (C++), programmes compilés"
  - "multithreading (C++), lier des programmes"
  - "threads (C++), programmes compilés"
  - "threads (C++), lier des programmes"
ms.assetid: 27589afc-daf2-4f26-b868-a99de5c9dfec
caps.latest.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 8
---
# Compilation et liaison de programmes multithread
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le programme Bounce.c est présenté dans [Exemple de programme multithread en langage C](../parallel/sample-multithread-c-program.md).  
  
 Les programmes sont compilés multithread par défaut.  
  
#### Pour compiler et lier le programme multithread Bounce.c dans l'environnement de développement  
  
1.  Dans le menu **Fichier**, cliquez sur **Nouveau**, puis sur **Projet**.  
  
2.  Dans le volet **Types de projet**, cliquez sur **Win32**.  
  
3.  Dans le volet **Modèles**, cliquez sur **Application console Win32**, puis attribuez un nom au projet.  
  
4.  Ajoutez le fichier contenant le code source C au projet.  
  
5.  Dans le menu **Générer**, générez le projet en cliquant sur la commande **Générer**.  
  
#### Pour compiler et lier le programme multithread Bounce.c à partir de la ligne de commande  
  
1.  Compilez et liez le programme :  
  
    ```  
    CL BOUNCE.C  
    ```  
  
## Voir aussi  
 [Multithreading à l'aide de C et de Win32](../parallel/multithreading-with-c-and-win32.md)