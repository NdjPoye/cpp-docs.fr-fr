---
title: "Existe-t-il des classes ou des fonctions MFC qui ne peuvent pas &#234;tre utilis&#233;es dans une DLL&#160;MFC&#160;? | Microsoft Docs"
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
  - "DLL (C++), MFC"
  - "DLL (C++), restrictions"
  - "DLL MFC (C++), restrictions"
ms.assetid: 18e2f1cb-4f72-4d3a-a951-3488208872c7
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Existe-t-il des classes ou des fonctions MFC qui ne peuvent pas &#234;tre utilis&#233;es dans une DLL&#160;MFC&#160;?
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Les DLL d'extension utilisent la classe dérivée de `CWinApp` de l'application cliente.  Elles ne doivent pas avoir leur propre classe dérivée de `CWinApp`.  
  
 À l'instar des applications MFC, les DLL normales doivent posséder une classe dérivée de `CWinApp` et un objet unique de cette classe d'application.  Contrairement à l'objet `CWinApp` d'une application, l'objet `CWinApp` de la DLL ne possède pas une pompe de messages principale.  
  
 Remarquez que comme le mécanisme `CWinApp::Run` ne s'applique pas à une DLL, c'est l'application qui possède la pompe de messages principale.  Si la DLL ouvre des boîtes de dialogue non modales ou possède une fenêtre frame principale qui lui est propre, la pompe de messages principale de l'application doit appeler une routine exportée par la DLL qui appelle à son tour la fonction membre `CWinApp::PreTranslateMessage` de l'objet application de la DLL.  
  
## Voir aussi  
 [Forum Aux Questions à propos des DLL](../build/dll-frequently-asked-questions.md)