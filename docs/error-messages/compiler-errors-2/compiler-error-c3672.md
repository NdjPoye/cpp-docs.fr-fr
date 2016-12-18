---
title: "Erreur du compilateur C3672 | Microsoft Docs"
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
  - "C3672"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3672"
ms.assetid: da971041-1766-467a-aecf-1d8655c6cb7a
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3672
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

l'expression pseudo\-destructeur ne peut être utilisée que dans le cadre d'un appel de fonction  
  
 Un destructeur a été appelé de façon incorrecte.  Pour plus d'informations, consultez [Destructeurs](../../cpp/destructors-cpp.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3672 :  
  
```  
// C3672.cpp  
template<typename T>  
void f(T* pT) {  
   &pT->T::~T;   // C3672  
   pT->T::~T();   // OK  
};  
  
int main() {  
   int i;  
   f(&i);  
}  
```