---
title: "Erreur du compilateur C2825 | Microsoft Docs"
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
  - "C2825"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2825"
ms.assetid: c832f1c1-5184-4fc2-9356-12b21daa7af3
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2825
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'var' : doit être une classe ou un espace de noms lorsqu'il est suivi par '::'  
  
 Échec d'une tentative de former un nom qualifié.  
  
 Assurez\-vous, par exemple, que votre code ne contient pas une déclaration de fonction dont le nom de la fonction commence par ::.  
  
## Exemple  
 L'exemple suivant génère l'erreur C2825 :  
  
```  
// C2825.cpp  
typedef int i;  
int main() {  
   int* p = new int;  
   p->i::i();   // C2825  
   // try the following line instead  
   // p->i::~i();  
}  
```