---
title: "Avertissement du compilateur (niveau 3) C4159 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4159"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4159"
ms.assetid: e2cf964e-f4b8-4b2c-9569-1abb94307232
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 3) C4159
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\#pragma pragma\(pop,...\) : a exécuté un pop sur l'identificateur 'identificateur' qui a préalablement fait l'objet d'un push  
  
 Votre code source contient une instruction **push** avec un identificateur pour un pragma suivi d'une instruction **pop** sans identificateur.  Le résultat est que ***identificateur*** est dépilé, les utilisations ultérieures de ***identificateur*** peuvent causer un comportement inattendu.  
  
 Pour éviter cet avertissement, donnez un identificateur dans l'instruction **pop**.  Par exemple :  
  
```  
// C4159.cpp  
// compile with: /W3  
#pragma pack(push, f)  
#pragma pack(pop)   // C4159  
  
// using the identifier resolves the warning  
// #pragma pack(pop, f)  
  
int main()  
{  
}  
```