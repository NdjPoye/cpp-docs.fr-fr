---
title: "Erreur du compilateur C2800 | Microsoft Docs"
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
  - "C2800"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2800"
ms.assetid: a2f1a590-9fe6-44cb-ad09-b4505ef47c6a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2800
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'operator opérateur' ne peut pas être surchargé  
  
 Les opérateurs suivants ne peuvent pas être surchargés : accès à un membre de classe \(`.`\), pointeur vers membre \(`.*`\), résolution de portée \(`::`\), expression conditionnelle \(`? :`\) et `sizeof`.  
  
 L'exemple suivant génère l'erreur C2800 :  
  
```  
// C2800.cpp  
// compile with: /c  
class C {  
   operator:: ();   // C2800  
};  
```