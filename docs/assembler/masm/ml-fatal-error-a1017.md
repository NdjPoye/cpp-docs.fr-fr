---
title: "ML Fatal Error A1017 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A1017"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A1017"
ms.assetid: bef0b312-5431-4e5a-b637-c19919acf01b
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# ML Fatal Error A1017
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**nom de fichier manquant de source**  
  
 ML n'a pas pu trouver un fichier pour satisfaire ou passer à l'éditeur de liens.  
  
 Cette erreur est générée lorsque vous donnez des options de ligne de commande de ML sans spécifier un nom de fichier à l'acte au moment.  Pour compiler les fichiers qui n'ont pas d'extension .asm, utilisez l'option de ligne de commande de **\/Ta** .  
  
 Cette erreur peut également être générée en appelant ML sans paramètres si la variable d'environnement de ML contient des options de ligne de commande.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)