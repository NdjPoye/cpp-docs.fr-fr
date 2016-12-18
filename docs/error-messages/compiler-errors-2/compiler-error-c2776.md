---
title: "Erreur du compilateur C2776 | Microsoft Docs"
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
  - "C2776"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2776"
ms.assetid: 9d80addc-62c7-40fc-a2cc-60303abb87df
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2776
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

une seule méthode 'get' peut être spécifiée par propriété  
  
 Vous pouvez spécifier uniquement une fonction `get` dans l'attribut étendu [property](../../cpp/property-cpp.md).  Cette erreur se produit lorsque plusieurs fonctions `get` sont spécifiées.  
  
 L'exemple suivant génère l'erreur C2776 :  
  
```  
// C2776.cpp  
struct A {  
   __declspec(property(get=GetProp,get=GetPropToo))  
   // try the following line instead  
   // __declspec(property(get=GetProp))  
      int prop;   // C2776  
   int GetProp(void);  
   int GetPropToo(void);  
};  
```