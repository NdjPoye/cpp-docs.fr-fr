---
title: "Avertissement du compilateur (niveau 3) C4278 | Microsoft Docs"
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
  - "C4278"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4278"
ms.assetid: 4b6053fb-df62-4c04-b6c8-c011759557b8
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4278
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : l'identificateur de la bibliothèque de types 'tlb' est déjà une macro ; utilisez le qualificateur 'rename'  
  
 Lors de l'utilisation de [\#import](../../preprocessor/hash-import-directive-cpp.md), un identificateur dans le typelib en cours d'importation tente de déclarer un identificateur ***identificateur***.  Mais cet identificateur est déjà un symbole valide.  
  
 Utilisez l'attribut `#import` **rename** pour assigner un alias au symbole dans la bibliothèque de types.