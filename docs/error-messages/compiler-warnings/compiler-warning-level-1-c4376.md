---
title: "Avertissement du compilateur (niveau&#160;1) C4376 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4376"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4376"
ms.assetid: 5f202c74-9489-48fe-b36f-19cd882b1589
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau&#160;1) C4376
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

le spécificateur d'accès 'ancien\_spécificateur :' n'est plus pris en charge ; utilisez 'nouveau\_spécificateur :' à la place  
  
 Pour plus d'informations sur la spécification de l'accès aux types et aux membres dans les métadonnées, consultez [Visibilité du type](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) et [Visibilité de membre](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Member_visibility) dans [Comment : définir et consommer des classes et des structs](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4376 :  
  
```  
// C4376.cpp  
// compile with: /clr /W1 /c  
public ref class G {  
public public:   // C4376  
   void m2();  
};  
  
public ref class H {  
public:   // OK  
   void m2();  
};  
```