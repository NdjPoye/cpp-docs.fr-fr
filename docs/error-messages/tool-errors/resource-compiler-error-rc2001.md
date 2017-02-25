---
title: "Erreur RC2001 du compilateur de ressources  | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "RC2001"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC2001"
ms.assetid: 92bfb4c0-1879-4606-bb9f-ef7368707b4a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur RC2001 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

saut de ligne dans la constante  
  
 Une constante de chaîne se poursuit sur une seconde ligne, sans utilisation d'une barre oblique inverse \(**\\**\) ou de guillemets doubles fermants et ouvrants \(**"**\).  
  
 Pour interrompre une constante de chaîne répartie sur deux lignes d'un fichier source, procédez de l'une des manières suivantes :  
  
-   Terminez la première ligne par une barre oblique inverse, qui est le caractère de continuation de ligne.  
  
-   Fermez la chaîne sur la première ligne à l'aide de guillemets doubles, puis ouvrez\-la sur la seconde ligne, de la même façon.  
  
 Il ne suffit pas de terminer la première ligne par \\n, la séquence d'échappement servant à incorporer un caractère de saut de ligne dans une constante de chaîne.