---
title: "Avertissement du compilateur (niveau 3) C4641 | Microsoft Docs"
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
  - "C4641"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4641"
ms.assetid: 28fe5c3e-6039-42da-9100-1312b5b15aea
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4641
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Le commentaire de document XML comporte une référence croisée ambiguë  
  
 Le compilateur n'a pas pu résoudre clairement une référence.  Pour résoudre cet avertissement, spécifiez les informations sur les paramètres nécessaires pour rendre la référence non équivoque.  
  
 Pour plus d'informations, consultez [Documentation XML](../../ide/xml-documentation-visual-cpp.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4641 :  
  
```  
// C4641.cpp  
// compile with: /W3 /doc /clr /c  
  
/// <see cref="f" />   // C4641  
// try the following line instead  
// /// <see cref="f(int)" />  
public ref class GR {  
public:  
   void f( int ) {}  
   void f( char ) {}  
};  
```