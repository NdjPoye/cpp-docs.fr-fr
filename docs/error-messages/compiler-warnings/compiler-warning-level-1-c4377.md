---
title: "Avertissement du compilateur (niveau 1) C4377 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4377"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4377"
ms.assetid: a1c797b8-cd5e-4a56-b430-d07932e811cf
caps.latest.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 5
---
# Avertissement du compilateur (niveau 1) C4377
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

les types natifs sont privés par défaut ; \-d1PrivateNativeTypes est déconseillé  
  
 Dans les versions précédentes, les types natifs contenus dans les assemblys étaient publics par défaut, et une option interne non documentée du compilateur \(**\/d1PrivateNativeTypes**\) était utilisée pour les rendre privés.  
  
 Tous les types, natifs et CLR, sont désormais privés par défaut dans un assembly ; par conséquent, **\/d1PrivateNativeTypes** n'est plus nécessaire.  
  
## Exemple  
 L'exemple suivant génère l'erreur C4377 :  
  
```  
// C4377.cpp  
// compile with: /clr /d1PrivateNativeTypes /W1  
// C4377 warning expected  
int main() {}  
```