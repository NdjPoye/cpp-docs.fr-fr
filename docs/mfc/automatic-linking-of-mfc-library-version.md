---
title: "Liaison automatique de la version de la biblioth&#232;que&#160;MFC | Microsoft Docs"
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
  - "defaultlib"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "liens automatiques (C++)"
  - "defaultlib dans MFC"
  - "liaison (C++)"
  - "liaison (C++), automatique de la version de la bibliothèque MFC"
  - "liaison (C++), de MFC"
  - "bibliothèques MFC, lier"
  - "bibliothèques MFC, versions"
ms.assetid: 02af4a20-2034-4fce-b200-c2202c3c8311
caps.latest.revision: 11
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Liaison automatique de la version de la biblioth&#232;que&#160;MFC
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Dans les versions de MFC avant la version 3,0 \(avant version 2,0 Visual C\+\+\), vous deviez spécifier manuellement la version correcte de la bibliothèque MFC dans la liste d'entrée des bibliothèques de l'éditeur de liens.  Avec la version 3,0 de MFC et versions ultérieures, il n'est plus nécessaire de spécifier manuellement la version de la bibliothèque MFC.  À la place, les fichiers d'en\-tête MFC déterminent automatiquement la version correcte de la bibliothèque MFC, en fonction des valeurs définies avec `#define`, tels que **\_DEBUG** ou **\_UNICODE**.  Les fichiers d'en\-tête MFC ajoutent les directives **\/defaultlib** en demandant à l'éditeur de liens d'établir la liaison avec une version spécifique de la bibliothèque MFC.  
  
 Par exemple, le fragment de code suivant à partir du fichier d'en\-tête d'AFX.H indique à l'éditeur de liens de lier dans la version soit de NAFXCWD.LIB soit de NAFXCW.LIB de MFC, selon la version de débogage de MFC que vous utilisez :  
  
 `#ifndef _UNICODE`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "nafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "nafxcw.lib")`  
  
 `#endif`  
  
 `#else`  
  
 `#ifdef _DEBUG`  
  
 `#pragma comment(lib, "uafxcwd.lib")`  
  
 `#else`  
  
 `#pragma comment(lib, "uafxcw.lib")`  
  
 `#endif`  
  
 `#endif`  
  
 Les fichiers d'en\-tête de MFC lient aussi dans toutes les bibliothèques nécessaires, notamment les bibliothèques MFC, les bibliothèques Win32, OLE bibliothèques, les bibliothèques OME générées à partir d'exemples, les bibliothèques ODBC, et ainsi de suite.  Les bibliothèques Win32 sont Kernel32.Lib, User32.Lib, et GDI32.Lib.  
  
## Voir aussi  
 [Versions de bibliothèque MFC](../mfc/mfc-library-versions.md)