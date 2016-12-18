---
title: "Erreur du compilateur C3619 | Microsoft Docs"
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
  - "C3619"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3619"
ms.assetid: 76ae80d0-9fbe-4297-a1ef-b1503377fdcf
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3619
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un modèle ne peut pas être déclaré dans un type WinRT ou managé  
  
 Les modèles de classe ne sont pas autorisés dans une interface ou une classe managée ou WinRT.  
  
 C3619 est accessible uniquement à l'aide de **\/clr:oldSyntax**.  
  
 L'exemple suivant génère l'erreur C3619 :  
  
```  
// C3619.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class X {  
   template<typename T> class Y {   // C3619  
   };  
};  
```