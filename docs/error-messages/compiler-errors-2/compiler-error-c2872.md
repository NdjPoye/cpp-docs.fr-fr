---
title: "Erreur du compilateur C2872 | Microsoft Docs"
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
  - "C2872"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2872"
ms.assetid: c619ef97-6e0e-41d7-867c-f8d28a07d553
caps.latest.revision: 11
caps.handback.revision: 11
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2872
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : symbole ambigu  
  
 Le compilateur ne peut pas déterminer le symbole auquel vous faites référence.  
  
 L'erreur C2872 peut se produire si un fichier d'en\-tête comprend une [using, directive](../../misc/using-directive-cpp.md), et si un fichier d'en\-tête suivant est spécifié avec `#include` et contient un type qui est également contenu dans l'espace de noms spécifié dans la directive `using`.  Ne spécifiez une directive `using` que lorsque tous vos fichiers d'en\-tête ont été spécifiés avec `#include`.  
  
 Pour plus d'informations à propos de l'erreur C2872, consultez [http:\/\/support.microsoft.com\/default.aspx?scid\=kb;en\-us;316317](http://support.microsoft.com/default.aspx?scid=kb;en-us;316317).  
  
 L'exemple suivant génère l'erreur C2872 :  
  
```  
// C2872.cpp  
namespace A {  
   int i;  
}  
  
using namespace A;  
int i;  
int main() {  
   ::i++;   // ok  
   A::i++;   // ok  
   i++;   // C2872 ::i or A::i?  
}  
```