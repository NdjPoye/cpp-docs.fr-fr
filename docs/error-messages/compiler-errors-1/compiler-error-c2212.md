---
title: "Erreur du compilateur C2212 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2212"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2212"
ms.assetid: 3fdab304-272c-4d07-bfd4-fad75170e536
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# Erreur du compilateur C2212
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : \_\_based non disponible pour les pointeurs vers des fonctions  
  
 Les pointeurs vers des fonctions ne peuvent pas être déclarés `__based`.  Si vos données doivent être basées sur le code, utilisez le mot clé `__declspec` ou le pragma `data_seg`.