---
title: "Acc&#232;s au statut de fichier | Microsoft Docs"
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
  - "exemples (MFC), état du fichier"
  - "état du fichier (C++)"
  - "fichiers (C++), accéder"
  - "fichiers (C++), informations d'état"
  - "statut des fichiers"
ms.assetid: 1b8891d6-eb0f-4037-a837-4928fe595222
caps.latest.revision: 10
caps.handback.revision: 6
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Acc&#232;s au statut de fichier
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

`CFile` prend aussi en charge l'état de récupération de fichier, notamment si le fichier existe, les dates et les heures de création et de modification, la taille logique, et le chemin d'accès.  
  
### L'état de récupération de fichier  
  
1.  Utilisez la classe [Fichier C](../mfc/reference/cfile-class.md) pour obtenir et définir les informations relatives à un fichier.  Une application utile consiste à utiliser la fonction membre statique **GetStatus** `CFile` pour déterminer si un fichier existe.  **GetStatus** renvoie 0 si le fichier cible n'existe pas.  
  
 Par conséquent, vous pouvez utiliser le résultat de **GetStatus** pour déterminer s'il faut utiliser le flag **CFile::modeCreate**quand vous ouvrez un fichier, tel qu'indiqué dans l'exemple suivant :  
  
 [!code-cpp[NVC_MFCFiles#3](../mfc/codesnippet/CPP/accessing-file-status_1.cpp)]  
  
 Pour plus d'informations, consultez [Sérialisation](../mfc/serialization-in-mfc.md).  
  
## Voir aussi  
 [Fichiers](../mfc/files-in-mfc.md)