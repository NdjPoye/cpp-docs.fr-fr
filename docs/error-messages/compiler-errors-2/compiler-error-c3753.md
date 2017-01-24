---
title: "Erreur du compilateur C3753 | Microsoft Docs"
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
  - "C3753"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3753"
ms.assetid: a5b99e28-796c-4107-a673-97c2ae3bb2b9
caps.latest.revision: 3
caps.handback.revision: 3
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3753
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

propriété générique non autorisée  
  
 Les listes de paramètres génériques ne peuvent apparaître que sur les classes, structures ou fonctions managées  
  
 Pour plus d’informations, consultez [Generics](../../windows/generics-cpp-component-extensions.md) et [property](../../windows/property-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3753 :  
  
```  
// C3753.cpp  
// compile with: /clr /c  
ref struct A {  
   generic <typename T>  
   property int i;   // C3753 error  
};  
```