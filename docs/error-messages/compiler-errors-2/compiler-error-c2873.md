---
title: "Erreur du compilateur C2873 | Microsoft Docs"
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
  - "C2873"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2873"
ms.assetid: 7a10036b-400e-4364-bd2f-dcd7370c5e28
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2873
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : un symbole ne peut pas être utilisé dans une déclaration using  
  
 Un mot clé [namespace](../../misc/namespace-declaration.md) est manquant dans une directive `using`.  Le compilateur interprète alors par erreur le code comme une [déclaration using](../../cpp/using-declaration.md) plutôt que comme une [directive using](../../misc/using-directive-cpp.md).