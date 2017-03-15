---
title: "Erreur irr&#233;cup&#233;rable RC1020 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC1020"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC1020"
ms.assetid: 3e073ebf-9136-4bf8-ac6a-3c642ed64594
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable RC1020 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\#endif' inattendu  
  
 La directive `#endif` n'a pas de directive `#if`, **\#ifdef** ou **\#ifndef** correspondante.  
  
 Assurez\-vous qu'il existe une directive `#endif` pour chaque instruction `#if`, **\#ifdef** et **\#ifndef**.