---
title: "Avertissement du compilateur (niveau 4) C4242 | Microsoft Docs"
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
  - "C4242"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4242"
ms.assetid: 8df742e1-fbf1-42f3-8e93-c0e1c222dc7e
caps.latest.revision: 10
caps.handback.revision: 10
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4242
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : conversion de 'type1' en 'type2', perte possible de données  
  
 Les types sont différents.  La conversion de type peut entraîner une perte de données.  Le compilateur effectue la conversion de type.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 Pour plus d'informations sur l'avertissement C4242, consultez [Erreurs de compilateur communes](http://msdn.microsoft.com/library/windows/desktop/aa384160).  
  
 L'exemple suivant génère l'erreur C4242 :  
  
```  
// C4242.cpp  
// compile with: /W4  
#pragma warning(4:4242)  
int func() {  
   return 0;  
}  
  
int main() {  
   char a;  
   a = func();   // C4242, return type and variable type do not match  
}  
```