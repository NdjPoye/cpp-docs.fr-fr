---
title: "Erreur du compilateur C2732 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C2732"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2732"
ms.assetid: 01b7ad2c-93cf-456f-a4c0-c5f2fdc7c07c
caps.latest.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 9
---
# Erreur du compilateur C2732
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les spécifications de la liaison contredisent les spécifications antérieures pour 'fonction'  
  
 La fonction est déjà déclarée avec un autre spécificateur de liaison.  
  
 Cette erreur peut être provoquée par des fichiers Include possédant des spécificateurs de liaison différents.  
  
 Pour corriger cette erreur, modifiez les instructions `extern` afin que les liaisons correspondent.  En particulier, n'imbriquez pas de directives `#include` dans des blocs `extern "C"`.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2732 :  
  
```  
// C2732.cpp  
extern void func( void );   // implicit C++ linkage  
extern "C" void func( void );   // C2732  
```