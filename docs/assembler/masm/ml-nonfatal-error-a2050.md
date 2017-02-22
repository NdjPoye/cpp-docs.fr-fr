---
title: "ML Nonfatal Error A2050 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "A2050"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "A2050"
ms.assetid: 16f3a58f-4bde-48f1-b0e3-2ed9612780a5
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# ML Nonfatal Error A2050
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

**nombre réel ou de BCD non \- autorisés**  
  
 \(Une véritable\) constante à virgule flottante de nombres ou \(BCD\) de décimale encodée en binaire a été utilisée que celle d'un initialiseur de données.  
  
 L'une des opérations suivantes produit :  
  
-   un nombre réel ou un BCD a été utilisé dans une expression.  
  
-   un nombre réel a été utilisé pour initialiser une directive autre que [valeur DWORD](../../assembler/masm/dword.md), [QWORD](../../assembler/masm/qword.md), ou [TBYTE](../../assembler/masm/tbyte.md).  
  
-   Un BCD a été utilisé pour initialiser une directive autre qu' `TBYTE`.  
  
## Voir aussi  
 [ML Error Messages](../../assembler/masm/ml-error-messages.md)