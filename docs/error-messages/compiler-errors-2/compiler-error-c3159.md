---
title: "Erreur du compilateur C3159 | Microsoft Docs"
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
  - "C3159"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3159"
ms.assetid: e115cc76-0021-4568-95fd-61a324c41a85
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3159
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'pointeur' : impossible de déclarer un tableau de pointeurs vers le type valeur  
  
 Il est impossible de déclarer un tableau de pointeurs vers un type valeur.  
  
 L'erreur C3159 n'est accessible qu'à l'aide de **\/clr:oldSyntax**.  
  
 L'exemple suivant génère l'erreur C3159 :  
  
```  
// C3159.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__value struct B {  
};  
  
void f( B*[] );   // C3159  
  
int main() {  
}  
```