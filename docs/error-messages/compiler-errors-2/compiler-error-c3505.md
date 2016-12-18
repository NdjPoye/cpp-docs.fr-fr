---
title: "Erreur du compilateur C3505 | Microsoft Docs"
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
  - "C3505"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3505"
ms.assetid: ed73c99e-93a1-4f3a-bac7-ba7ed5d836e4
caps.latest.revision: 4
caps.handback.revision: 4
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3505
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de charger la bibliothèque de types 'guid'  
  
 L'erreur C3505 peut être générée si vous exécutez le compilateur croisé \(32 bits à 64 bits\) sur un ordinateur 64 bits, car le compilateur s'exécute sous WOW64 et ne peut lire que dans la ruche du Registre 32 bits.  
  
 Vous pouvez résoudre cette erreur C3505 en générant des versions 32 bits et 64 bits de la bibliothèque de types que vous essayez d'importer et en les enregistrant toutes les deux.  Vous pouvez également utiliser le compilateur 64 bits natif, mais cela nécessite la modification de vos répertoires VC dans l'IDE afin qu'ils pointent vers le compilateur 64 bits.  
  
 Pour plus d'informations, consultez  
  
-   [Comment : activer un ensemble d'outils du compilateur Visual C\+\+ 64 bits sur la ligne de commande](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [Comment : activer un ensemble d'outils du compilateur Visual C\+\+ 64 bits sur la ligne de commande](../../build/how-to-enable-a-64-bit-visual-cpp-toolset-on-the-command-line.md)  
  
-   [Comment : configurer des projets Visual C\+\+ pour cibler des plateformes 64 bits](../../build/how-to-configure-visual-cpp-projects-to-target-64-bit-platforms.md)