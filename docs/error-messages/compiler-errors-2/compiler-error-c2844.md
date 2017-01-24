---
title: "Erreur du compilateur C2844 | Microsoft Docs"
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
  - "C2844"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2844"
ms.assetid: dcaf4cd2-21b0-4280-ae42-0a706c524d83
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2844
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'membre' : ne peut pas être un membre de l'interface 'interface'  
  
 Une [interface class](../../windows/interface-class-cpp-component-extensions.md) ne peut pas contenir de donnée membre sauf si elle est également une propriété.  
  
 Seule une fonction membre ou de propriété est autorisée dans une interface.  Les constructeurs, les destructeurs et les opérateurs ne sont en outre pas autorisés.  
  
 L'exemple suivant génère l'erreur C2844 :  
  
```  
// C2844a.cpp  
// compile with: /clr /c  
public interface class IFace {  
   int i;   // C2844  
   // try the following line instead  
   // property int Size;  
};  
```  
  
 L'exemple suivant génère l'erreur C2844 :  
  
```  
// C2844b.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
__gc __interface IFace {  
   int i;   // C2844  
   // try the following line instead  
   // __property int Size { get; set; };  
};  
```