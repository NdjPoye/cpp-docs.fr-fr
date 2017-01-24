---
title: "Erreur du compilateur C3645 | Microsoft Docs"
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
  - "C3645"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3645"
ms.assetid: 346da528-ae86-4cd0-9654-f41bee26ac0d
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3645
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : \_\_clrcall ne peut pas être utilisé sur les fonctions compilées en code natif  
  
 La présence de certains mots clés dans une fonction entraînera sa compilation en fonction native.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3645 :  
  
```  
// C3645.cpp  
// compile with: /clr /c  
#pragma unmanaged   
int __clrcall dog() {}   // C3645  
```