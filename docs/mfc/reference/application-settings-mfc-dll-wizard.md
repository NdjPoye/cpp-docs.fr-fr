---
title: "Param&#232;tres de l&#39;application, Assistant DLL MFC | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "vc.appwiz.mfc.dll.appset"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "Assistant DLL MFC, paramètres de l’application"
ms.assetid: 0a96b94f-ae36-4975-951b-c9ffb3def21c
caps.latest.revision: 9
caps.handback.revision: 5
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Param&#232;tres de l&#39;application, Assistant DLL MFC
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Utilisez cette page de l'Assistant DLL MFC pour concevoir et ajouter des fonctionnalités de base à un nouveau projet DLL MFC.  
  
## Type de DLL  
 Sélectionnez le type de DLL que vous souhaitez créer.  
  
 **DLL normale utilisant une DLL MFC partagée**  
 Sélectionnez cette option pour lier la bibliothèque MFC à votre programme en tant que DLL partagée.  Si vous utilisez cette option, vous ne pouvez pas partager les objets MFC entre votre DLL et l'application appelante.  Votre programme effectue des appels à la bibliothèque MFC au moment de l'exécution.  Cette option réduit les besoins en mémoire et espace disque de votre programme s'il est composé de plusieurs fichiers exécutables qui utilisent la bibliothèque MFC.  Les programmes Win32 et MFC peuvent appeler des fonctions dans votre DLL.  Vous devez redistribuer la DLL MFC avec ce type de projet.  
  
 **DLL normale liée statiquement aux MFC**  
 Sélectionnez cette option pour lier votre programme statiquement à la bibliothèque MFC au moment de la génération.  Les programmes Win32 et MFC peuvent appeler des fonctions dans votre DLL.  Bien que cette option augmente la taille de votre programme, vous n'avez pas besoin de redistribuer la DLL MFC avec ce type de projet.  Vous ne pouvez pas partager des objets MFC entre votre DLL et l'application appelante.  
  
 **DLL d'extension MFC**  
 Sélectionnez cette option si vous souhaitez que votre programme effectue des appels à la bibliothèque MFC au moment de l'exécution, et si vous souhaitez partager les objets MFC entre votre DLL et l'application appelante.  Cette option réduit les besoins en mémoire et espace disque de votre programme, s'il est composé de plusieurs fichiers exécutables qui utilisent tous la bibliothèque MFC.  Seuls les programmes MFC peuvent appeler des fonctions dans votre DLL.  Vous devez redistribuer la DLL MFC avec ce type de projet.  
  
## Fonctionnalités supplémentaires  
 Vous permet de sélectionner si votre DLL MFC prend en charge l'automation et Windows sockets.  
  
 **Automation**  
 Sélectionnez **Automation** pour permettre à votre programme de manipuler des objets implémentés par un autre programme.  Si vous sélectionnez **Automation**, votre programme est également exposé à d'autres clients Automation.  Consultez [Automation](../../mfc/automation.md) pour plus d'informations.  
  
 **Windows sockets**  
 Sélectionnez cette option pour indiquer que votre programme prend en charge Windows sockets.  Windows sockets vous permet d'écrire des programmes qui communiquent sur les réseaux TCP\/IP.  
  
 Lorsque votre DLL MFC avec la prise en charge Windows sockets est créée, [CWinApp::InitInstance](../Topic/CWinApp::InitInstance.md) initialise la prise en charge pour les sockets et le fichier d'en\-tête MFC StdAfx.h comprend AfxSock.h.  
  
## Voir aussi  
 [DLL MFC \(Assistant\)](../../mfc/reference/mfc-dll-wizard.md)   
 [Création d'un projet DLL MFC](../../mfc/reference/creating-an-mfc-dll-project.md)