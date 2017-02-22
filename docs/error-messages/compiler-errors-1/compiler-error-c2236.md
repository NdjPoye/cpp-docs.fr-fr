---
title: "Erreur du compilateur C2236 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2236"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2236"
ms.assetid: 0b6771a7-a783-4729-9c3d-7a3339c432cc
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2236
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

jeton 'identificateur' inattendu.N'auriez\-vous pas oublié un ';' ?  
  
 L'identificateur est déjà défini comme un type et ne peut pas être remplacé par un type défini par l'utilisateur.  
  
 L'exemple suivant génère l'erreur C2236 :  
  
```  
// C2236.cpp  
// compile with: /c  
int class A {};  // C2236 "int class" is unexpected  
int i;  
class B {};  
```