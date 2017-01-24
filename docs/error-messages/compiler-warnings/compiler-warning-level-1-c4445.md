---
title: "Avertissement du compilateur (niveau 1) C4445 | Microsoft Docs"
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
  - "C4445"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4445"
ms.assetid: 535e92a0-ba08-4dfc-89b2-af2dcdd7caeb
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4445
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : dans un type WinRT ou managé, une méthode virtuelle ne peut pas être privée  
  
 Si une fonction virtuelle est privée, un type dérivé ne peut pas y accéder.  Pour corriger cette erreur, modifiez l'accessibilité de la fonction membre virtuelle pour qu'elle soit protégée ou publique.