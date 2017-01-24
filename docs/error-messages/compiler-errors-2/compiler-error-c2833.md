---
title: "Erreur du compilateur C2833 | Microsoft Docs"
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
  - "C2833"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2833"
ms.assetid: b9418ce1-e2ee-4599-8959-6fde89c27569
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2833
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator opérateur' n'est pas un opérateur ou type reconnu  
  
 Le mot `operator` doit être suivi d'un opérateur que vous voulez substituer ou d'un type que vous voulez convertir.  
  
 Pour obtenir la liste des opérateurs que vous pouvez définir dans un type managé, consultez [Opérateurs définis par l'utilisateur](../../dotnet/user-defined-operators-cpp-cli.md).  
  
 L'exemple suivant génère l'erreur C2833 :  
  
```  
// C2833.cpp  
// compile with: /c  
class A {};  
  
void operator ::* ();   // C2833  
void operator :: ();   // OK  
```