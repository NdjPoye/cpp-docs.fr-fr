---
title: "Avertissement RC4005 du compilateur de ressources  | Microsoft Docs"
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
  - "RC4005"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "RC4005"
ms.assetid: 71f03b4a-c9a9-415d-920f-bf2e58507f93
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement RC4005 du compilateur de ressources 
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : redéfinition de macro  
  
 L'identificateur est défini à deux reprises.  Le compilateur a utilisé la seconde définition de macro.  
  
 Cet avertissement peut s'afficher lorsqu'une macro est définie dans la ligne de commande et dans le code à l'aide d'une directive `#define`.  Il peut également être provoqué par des macros importées de fichiers include.  
  
 Pour l'éliminer, supprimez une des définitions ou placez une directive `#undef` avant la seconde définition.