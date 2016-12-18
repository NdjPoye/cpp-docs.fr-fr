---
title: "Erreur du compilateur C3126 | Microsoft Docs"
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
  - "C3126"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3126"
ms.assetid: e72658a3-5d85-4a31-89a4-dbc3d475973d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3126
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

impossible de définir une union 'union' à l'intérieur du type managé 'type'  
  
 Une union ne peut pas être définie à l'intérieur d'un type managé.  
  
 L'exemple suivant génère l'erreur C3126 :  
  
```  
// C3126_2.cpp  
// compile with: /clr /c  
ref class Test  
{  
   union x  
   {   // C3126  
      int a;  
      int b;  
   };  
};  
```  
  
 L'exemple suivant génère l'erreur C3126 :  
  
```  
// C3126.cpp  
// compile with: /clr:oldSyntax /c  
#using <mscorlib.dll>  
  
__gc class Test  
{  
   union x  
   {   // C3126  
      int a;  
      int b;  
   };  
};  
```