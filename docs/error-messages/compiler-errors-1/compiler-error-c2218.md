---
title: "Erreur du compilateur C2218 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2218"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2218"
ms.assetid: b0f55da4-8edb-4b45-b298-1a091981bd7b
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2218
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'\_\_vectorcall' ne peut pas s'utiliser avec '\/arch:IA32'  
  
 La convention d'appel `__vectorcall` est prise en charge uniquement dans le code natif sur les processeurs x86 et x64 qui incluent les extensions Streaming SIMD 2 \(SSE2\) et versions ultérieures.  Pour plus d'informations, consultez [\_\_vectorcall](../../cpp/vectorcall.md).  
  
 Pour corriger cette erreur, modifiez les options du compilateur pour cibler les jeux d'instructions SSE2, AVX ou AVX2.  Pour plus d'informations, consultez [\/arch \(x86\)](../../build/reference/arch-x86.md).