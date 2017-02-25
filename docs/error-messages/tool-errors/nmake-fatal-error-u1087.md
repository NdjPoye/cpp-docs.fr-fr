---
title: "Erreur irr&#233;cup&#233;rable NMAKE U1087 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "U1087"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "U1087"
ms.assetid: 5236ab54-e117-484d-99c3-852b061fd3d0
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur irr&#233;cup&#233;rable NMAKE U1087
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible d'avoir les dépendants : et :: pour la même cible  
  
 Il n'est pas possible de spécifier une cible à la fois dans une dépendance à un seul signe des deux\-points \(**:**\) et dans une dépendance à double signe des deux\-points \(`::`\).  
  
 Pour spécifier une cible dans plusieurs blocs de description, utilisez `::` dans chaque ligne de dépendance.