---
title: "Erreur du compilateur C2086 | Microsoft Docs"
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
  - "C2086"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2086"
ms.assetid: 4329bf72-90c8-444c-8524-4ef75e6b2139
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2086
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : redéfinition  
  
 L'identificateur est défini plus d'une fois ou bien une déclaration ultérieure est différente d'une précédente.  
  
 L'erreur C2086 peut également être due à une génération incrémentielle pour un assembly C\# référencé.  Régénérez l'assembly C\# pour remédier à cette erreur.  
  
 L'exemple suivant génère l'erreur C2086 :  
  
```  
// C2086.cpp  
main() {  
  int a;  
  int a;   // C2086 not an error in ANSI C  
}  
```