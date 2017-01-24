---
title: "Erreur du compilateur C3116 | Microsoft Docs"
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
  - "C3116"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3116"
ms.assetid: 597463e1-a5cc-4ed3-a917-eae9a61d3312
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3116
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'spécificateur de stockage' : classe de stockage non valide pour la méthode d'interface  
  
 Vous avez utilisé `typedef`, `register` ou `static` comme classe de stockage pour une méthode d'interface.  Ces classes de stockage ne sont pas autorisées sur les membres d'interface.  
  
 L'exemple suivant génère l'erreur C3116 :  
  
```  
// C3116.cpp  
__interface ImyInterface  
{  
   static void myFunc();   // C3116  
};  
```