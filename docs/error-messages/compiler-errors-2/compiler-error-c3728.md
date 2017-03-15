---
title: "Erreur du compilateur C3728 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3728"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3728"
ms.assetid: 6b510cb1-887f-4fcd-9a1f-3bb720417ed1
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3728
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'événement' : l'événement ne possède pas de méthode raise  
  
 Des métadonnées créées avec un langage tel que C\# qui ne permet pas de déclencher un événement depuis l'extérieur de la classe dans lequel il a été défini, ont été incluses avec la directive [\#using](../../preprocessor/hash-using-directive-cpp.md), et un programme Visual C\+\+ qui utilise la programmation CLR essaie de déclencher l'événement.  
  
 Pour déclencher un événement dans un programme développé dans un langage tel que C\#, la classe contenant l'événement doit également définir une méthode publique qui déclenche l'événement.