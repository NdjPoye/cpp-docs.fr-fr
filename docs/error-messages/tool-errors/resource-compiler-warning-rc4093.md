---
title: "Avertissement RC4093 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC4093"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4093"
ms.assetid: 3c61b4a4-b418-465b-a4fd-cb1ff0adb8dd
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement RC4093 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

nouvelle ligne sans séquence d'échappement dans une constante caractère du code inactif  
  
 La valeur d'une expression constante d'une directive de préprocesseur `#if`, `#elif`, **\#ifdef** ou **\#ifndef** est égale à zéro, rendant le code qui la suit inactif.  Dans ce code inactif, un caractère de saut de ligne apparaît entre des guillemets simples ou doubles.  
  
 Tout le texte affiché jusqu'aux prochains guillemets doubles a été considéré comme appartenant à une constante de caractère.