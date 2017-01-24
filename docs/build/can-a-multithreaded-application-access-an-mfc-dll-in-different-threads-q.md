---
title: "Une application multithread peut-elle acc&#233;der &#224; une DLL MFC dans diff&#233;rents threads&#160;? | Microsoft Docs"
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
  - "DLL (C++), multithreading"
  - "DLL MFC (C++), multithreading"
  - "multithreading (C++), DLL"
  - "threads (MFC), DLL"
ms.assetid: e3452e62-021e-4d23-9cce-cff41eb8b46b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Une application multithread peut-elle acc&#233;der &#224; une DLL MFC dans diff&#233;rents threads&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les applications multithread peuvent accéder à des DLL normales liées de manière dynamique aux MFC et aux DLL d'extension à partir de différents threads.  Depuis la version 4.2 de Visual C\+\+, une application peut accéder à des DLL normales liées de manière statique aux MFC à partir de plusieurs threads créés dans l'application.  
  
 Avant la version 4.2, un seul thread externe pouvait s'attacher à une DLL normale liée de manière statique aux MFC.  Pour plus d'informations sur les restrictions d'accès aux DLL normales liées de manière statique aux MFC à partir de plusieurs threads \(versions antérieures à Visual C\+\+ 4.2\), consultez l'article de la Base de connaissances \(en anglais\) « INFO: Multiple Threads and MFC \_USRDLLs » \(Q122676\).  
  
 Remarquez que le terme USRDLL n'a plus cours dans la documentation Visual C\+\+.  Une DLL normale liée de manière statique aux MFC possède les mêmes caractéristiques que l'ancienne USRDLL.  
  
## Voir aussi  
 [Forum Aux Questions à propos des DLL](../build/dll-frequently-asked-questions.md)