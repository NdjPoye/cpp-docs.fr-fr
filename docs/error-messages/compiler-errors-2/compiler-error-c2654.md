---
title: "Erreur du compilateur C2654 | Microsoft Docs"
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
  - "C2654"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2654"
ms.assetid: ca7de1bd-576b-40bf-96fc-a91984827d20
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2654
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : tentative d'accéder à un membre externe à une fonction membre  
  
 Un accès à un membre a lieu dans une déclaration.  Les données membres sont seulement accessibles dans les fonctions membres.  
  
 Cette erreur peut être provoquée par une tentative d'initialisation de variables dans une déclaration.  Utilisez un constructeur à cet effet.