---
title: "Erreur du compilateur C2581 | Microsoft Docs"
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
  - "C2581"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2581"
ms.assetid: 24a4e4c1-24d3-4e42-b760-7dcaf9740b16
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2581
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type' : fonction static 'operator \=' non conforme  
  
 L'opérateur d'assignation \(`=`\) est déclaré comme étant `static` de façon incorrecte.  Les opérateurs d'assignation ne peuvent pas être `static`.  Pour plus d'informations, consultez [Opérateurs définis par l'utilisateur](../../dotnet/user-defined-operators-cpp-cli.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C2581 :  
  
```  
// C2581.cpp  
// compile with: /clr /c  
ref struct Y {  
   static Y ^ operator = (Y^ me, int i);   // C2581  
   Y^ operator =(int i);   // OK  
};  
```