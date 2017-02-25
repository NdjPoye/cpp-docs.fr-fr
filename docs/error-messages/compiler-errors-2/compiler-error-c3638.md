---
title: "Erreur du compilateur C3638 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3638"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3638"
ms.assetid: 8d8bc5ca-75aa-480e-b6b6-3178fab51b1d
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C3638
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'opérateur' : impossible de redéfinir les opérateurs de conversion boxing et unboxing standard  
  
 Le compilateur définit un opérateur de conversion pour chaque classe managée afin de prendre en charge la conversion boxing implicite.  Cet opérateur ne peut pas être redéfini.  
  
 Pour plus d'informations, consultez [Conversion boxing implicite](../../windows/boxing-cpp-component-extensions.md).  
  
 L'exemple suivant génère l'erreur C3638 :  
  
```  
// C3638.cpp  
// compile with: /clr  
value struct V {  
   V(){}  
   static operator V^(V);   // C3638  
};  
  
int main() {  
   V myV;  
   V ^ pmyV = myV;   // operator supports implicit boxing  
}  
```