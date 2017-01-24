---
title: "Erreur du compilateur C2856 | Microsoft Docs"
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
  - "C2856"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2856"
ms.assetid: fe616c51-124e-49e3-9dd8-883ec1660680
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2856
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma hdrstop ne peut pas se trouver dans un bloc \#if  
  
 Le pragma `hdrstop` ne peut pas être placé à l'intérieur du corps d'un bloc de compilation conditionnel.  
  
 Déplacez l'instruction `#pragma hdrstop` vers une zone qui n'est pas contenue dans un bloc `#if/#endif`.