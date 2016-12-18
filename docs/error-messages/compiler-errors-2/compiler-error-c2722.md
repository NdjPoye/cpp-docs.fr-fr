---
title: "Erreur du compilateur C2722 | Microsoft Docs"
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
  - "C2722"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2722"
ms.assetid: 4cc2c7fa-cb12-4bcf-9df1-6d627ef62973
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2722
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'::opérateur' : non conforme après une commande operator ; utilisez 'operator opérateur'  
  
 Une instruction `operator` redéfinit `::new` ou `::delete`.  Comme les opérateurs `new` et `delete` sont globaux, l'opérateur de résolution de portée \(`::`\) est sans importance.  Supprimez l'opérateur `::`.