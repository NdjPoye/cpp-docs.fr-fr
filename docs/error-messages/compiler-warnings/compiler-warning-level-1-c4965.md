---
title: "Avertissement du compilateur (niveau 1) C4965 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4965"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4965"
ms.assetid: 47f3f6dc-459b-4a25-9947-f394c8966cb5
caps.latest.revision: 14
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 14
---
# Avertissement du compilateur (niveau 1) C4965
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

conversion boxing implicite de l'entier 0 ; utilisez nullptr ou effectuez un cast explicite  
  
 Visual C\+\+ permet le boxing implicite des types valeur.  Une instruction qui a entraîné une assignation nulle à l'aide des extensions managées pour C\+\+ devient désormais une assignation à un type int converti.  
  
 Pour plus d'informations, consultez [Boxing](../../windows/boxing-cpp-component-extensions.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4965 :  
  
```  
// C4965.cpp  
// compile with: /clr /W1  
int main() {  
   System::Object ^o = 0;   // C4965  
  
   // the previous line is the same as the following line  
   // using Managed Extensions for C++  
   // System::Object *o = __box(0);  
  
   // OK  
   System::Object ^o2 = nullptr;  
   System::Object ^o3 = safe_cast<System::Object^>(0);  
}  
```