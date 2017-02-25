---
title: "Erreur irr&#233;cup&#233;rable RC1022 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1022"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1022"
ms.assetid: 30a0f3c7-08a8-4c40-b0de-46ee5feb789d
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable RC1022 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\#endif' attendu  
  
 Il manque une directive `#endif` après une directive `#if`, **\#ifdef** ou **\#ifndef**.  
  
 Assurez\-vous que cette instruction est précédée d'une instruction `#if`, **\#ifdef** ou **\#ifndef** en vigueur.