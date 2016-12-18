---
title: "MFC MBCS DLL, compl&#233;ment | Microsoft Docs"
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
  - "MBCS"
  - "MFC"
ms.assetid: bebec0ff-e019-42ca-b5df-8c218ac5b54a
caps.latest.revision: 17
caps.handback.revision: 13
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# MFC MBCS DLL, compl&#233;ment
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans Visual Studio 2015, la bibliothèque MFC pour l’encodage des caractères multioctets est incluse dans les composants de l’installation de Visual C\+\+. Visual C\+\+ et MFC sont des configurations dont l’installation est facultative dans le programme d’installation de Visual Studio. Pour que MFC soit installé, choisissez **Personnalisé** dans le programme d’installation et, sous **Langages de programmation**, assurez\-vous que **Visual C\+\+** et **Microsoft Foundation Classes pour C\+\+** sont sélectionnés. Si vous avez déjà installé Visual Studio, il vous est demandé d’installer Visual C\+\+ et\/ou MFC quand vous tentez de créer un projet MFC.  
  
 Vous avez besoin des DLL multioctets pour pouvoir générer un projet MFC dans Visual Studio 2015 dont la propriété **Jeu de caractères** est définie sur **Utiliser le jeu de caractères multioctet \(MBCS\)** ou **Non défini**.  
  
## Voir aussi  
 [Versions de bibliothèque MFC](../mfc/mfc-library-versions.md)