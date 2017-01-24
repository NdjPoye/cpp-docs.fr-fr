---
title: "Erreur du compilateur C3874 | Microsoft Docs"
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
  - "C3874"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3874"
ms.assetid: fd55fc05-69a7-4237-b3b7-dca1d5400b4f
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3874
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le type de retour de 'fonction' doit être 'int' au lieu de 'type'  
  
 Une fonction ne possède pas le type de retour attendu par le compilateur.  
  
 L'exemple suivant génère l'erreur C3874 :  
  
```  
// C3874b.cpp  
double main()  
{   // C3874  
}  
```