---
title: "Erreur du compilateur C3539 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3539"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3539"
ms.assetid: 34a33a0f-d1b6-498f-b312-ffad2d4799b3
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Erreur du compilateur C3539
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

« type » : un argument template ne peut pas être un type qui contient « auto »  
  
 Le type d'argument template indiqué ne peut pas contenir une utilisation du mot clé `auto`.  
  
### Pour corriger cette erreur  
  
1.  Ne spécifiez pas l'argument template avec le mot clé `auto`.  
  
## Exemple  
 L'exemple suivant donne C3539.  
  
```  
// C3539.cpp  
// Compile with /Zc:auto  
template<class T> class C{};  
int main()  
{  
   C<auto> c;   // C3539  
   return 0;  
}  
```  
  
## Voir aussi  
 [auto, mot clé](../../cpp/auto-keyword.md)