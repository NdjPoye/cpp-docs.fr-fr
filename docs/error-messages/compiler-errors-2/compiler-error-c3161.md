---
title: "Erreur du compilateur C3161 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C3161"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3161"
ms.assetid: 1fe2be85-a343-487b-8476-bf9e257eb29d
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3161
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'interface' : l'imbrication d'une classe, d'une structure, d'une union ou d'une interface dans une interface n'est pas conforme ; l'imbrication d'une interface dans une classe, une structure ou une union n'est pas conforme  
  
 Une [\_\_interface](../../cpp/interface.md) peut seulement apparaître au niveau de la portée globale ou à l'intérieur d'un espace de noms.  Une classe, une structure ou une union ne peuvent pas apparaître dans une interface.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3161 :  
  
```  
// C3161.cpp  
// compile with: /c  
__interface X {  
   __interface Y {};   // C3161 A nested interface  
};  
```