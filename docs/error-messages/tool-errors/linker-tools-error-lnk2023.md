---
title: "Erreur des outils &#201;diteur de liens LNK2023 | Microsoft Docs"
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
  - "LNK2023"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "LNK2023"
ms.assetid: c99e35a8-739a-4a20-a715-29b8c3744703
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur des outils &#201;diteur de liens LNK2023
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

une dll ou un point d'entrée erronés \<dll ou point d'entrée\>  
  
 L'éditeur de liens charge une version incorrecte de msobj90.dll.  Vérifiez que les versions de link.exe et msobj90.dll dans le chemin d'accès sont identiques.  
  
 Il manque peut\-être une dépendance de msobj90.dll.  La liste de dépendances de msobj90.dll est la suivante :  
  
-   Msvcr90.dll  
  
-   Kernel32.dll  
  
 Vérifiez la présence sur votre ordinateur d'autres copies de msobj90.dll pouvant être obsolètes.