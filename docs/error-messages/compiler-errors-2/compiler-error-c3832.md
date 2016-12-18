---
title: "Erreur du compilateur C3832 | Microsoft Docs"
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
  - "C3832"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3832"
ms.assetid: 9a41df82-42e1-4908-958c-76cff9235de0
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3832
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'bibliothèque de types' : la bibliothèque de types semble avoir été développée pour des pointeurs 32 bits ; veuillez modifier le qualificateur 'ptrsize'  
  
 L'information explicite fournie avec l'attribut `ptrsize` de la directive [\#import](../../preprocessor/hash-import-directive-cpp.md) ne correspond pas avec ce que le compilateur a trouvé dans la bibliothèque de types.