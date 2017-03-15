---
title: "Avertissement du compilateur (niveau 1) C4715 | Microsoft Docs"
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
  - "C4715"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4715"
ms.assetid: 1c819bf7-0d8b-4f5e-b338-9cc292870439
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4715
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : les chemins de contrôle ne retournent pas tous une valeur  
  
 La fonction spécifiée risque de ne pas retourner de valeur.  
  
## Exemple  
  
```  
// C4715a.cpp  
// compile with: /W1 /LD  
int func1( int i )  
{  
   if( i )  
   return 3;  // C4715 warning, nothing returned if i == 0  
}  
```  
  
 Pour éviter cet avertissement, modifiez le code de manière à ce que tous les chemins d'accès assignent une valeur de retour à la fonction :  
  
```  
// C4715b.cpp  
// compile with: /LD  
int func1( int i )  
{  
   if( i ) return 3;  
   else return 0;     // OK, always returns a value  
}  
```  
  
 Votre code contient peut\-être un appel à une fonction qui ne donne jamais lieu à un retour, comme dans l'exemple suivant :  
  
```  
// C4715c.cpp  
// compile with: /W1 /LD  
void fatal()  
{  
}  
int glue()  
{  
   if(0)  
      return 1;  
   else if(0)  
      return 0;  
   else  
      fatal();   // C4715  
}  
```  
  
 Ce code génère également un avertissement car le compilateur ne sait pas que `fatal` n'est jamais retourné.  Pour éviter que ce code ne génère un message d'erreur, déclarez `fatal` en utilisant [\_\_declspec\(noreturn\)](../../cpp/noreturn.md).