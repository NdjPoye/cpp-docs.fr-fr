---
title: "Avertissement du compilateur (niveau 1) C4042 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4042"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4042"
ms.assetid: e4bd861b-1194-426b-bf79-68c5b021eb0a
caps.latest.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 6
---
# Avertissement du compilateur (niveau 1) C4042
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'identificateur' : classe de stockage incorrecte  
  
 La classe de stockage spécifiée ne peut être utilisée avec cet identificateur dans ce contexte.  Le compilateur utilise plutôt la classe de stockage par défaut :  
  
-   `extern`, si *identificateur* est une fonction.  
  
-   **auto**, si *identificateur* est un paramètre formel ou une variable locale.  
  
-   Pas de classe de stockage, si *identificateur* est une variable globale.  
  
 Cet avertissement peut être provoqué par la spécification d'une classe de stockage autre que **register** dans une déclaration de paramètre.  
  
 L'exemple suivant génère l'avertissement C4042 :  
  
```  
// C4042.cpp  
// compile with: /W1 /LD  
int func2( __declspec( thread ) int tls_i )    // C4042  
// try the following line instead  
// int func2( int tls_i )  
{  
   return tls_i;  
}  
```