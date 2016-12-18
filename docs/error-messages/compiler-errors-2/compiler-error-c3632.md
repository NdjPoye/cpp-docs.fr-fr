---
title: "Erreur du compilateur C3632 | Microsoft Docs"
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
  - "C3632"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3632"
ms.assetid: a04e3217-f5a1-4461-a1db-d69fd096d468
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3632
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'événement' : style d'événement non conforme pour construct  
  
 Les déclarations [\_\_event](../../cpp/event.md) ne sont pas valides dans toutes les constructions.  
  
 L'erreur C3632 n'est accessible qu'à l'aide de **\/clr:oldSyntax**.  
  
 L'exemple suivant génère l'erreur C3632 :  
  
```  
// C3632.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __gc __interface I  
{  
   __event void sna();   // C3632  
};  
  
// use the following as an example  
__delegate void MyDel();  
public __gc __interface I2  
{  
   __event MyDel* sna;  
};  
  
int main()  
{  
}  
```