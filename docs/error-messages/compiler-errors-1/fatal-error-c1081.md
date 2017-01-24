---
title: "Erreur irr&#233;cup&#233;rable C1081 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C1081"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C1081"
ms.assetid: e58adf17-cbe1-4955-a5c7-80622bbba249
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur irr&#233;cup&#233;rable C1081
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : nom de fichier trop long  
  
 La longueur d'un chemin d'accès de fichier dépasse `_MAX_PATH` \(défini par STDLIB.h à 260 caractères\).  Utilisez un nom de fichier plus court.  
  
 Si vous appelez CL.exe avec un nom de fichier court, le compilateur peut avoir à générer un chemin d'accès complet.  Par exemple, `cl -c myfile.cpp` peut entraîner la génération par le compilateur de :  
  
```  
D:\<very-long-directory-path>\myfile.cpp  
```