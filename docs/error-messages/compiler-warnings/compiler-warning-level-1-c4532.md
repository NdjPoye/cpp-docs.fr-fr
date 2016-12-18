---
title: "Avertissement du compilateur (niveau 1) C4532 | Microsoft Docs"
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
  - "C4532"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4532"
ms.assetid: 4e2a286a-d233-4106-9f65-29be1a94ca02
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4532
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'continue' : le saut hors du bloc \_\_finally\/finally a un comportement indéfini lors de la gestion du bloc de fin  
  
 Le compilateur a rencontré un des mots clés suivants :  
  
-   [continue](../../cpp/continue-statement-cpp.md)  
  
-   [break](../../cpp/break-statement-cpp.md)  
  
-   [goto](../../cpp/goto-statement-cpp.md)  
  
 ce qui a causé un saut en dehors d'un bloc [\_\_finally](../../cpp/try-finally-statement.md) ou [finally](../../dotnet/finally.md) lors d'un arrêt anormal.  
  
 Si une exception survient, et tant que la pile n'est pas vidée lors de l'exécution des gestionnaires de terminaisons \(les blocs `__finally` ou finally\), si votre code effectue un saut en dehors d'un bloc `__finally` avant la fin de ce bloc `__finally`, le comportement n'est pas défini.  Le contrôle peut ne jamais revenir au code de vidage, donc l'exception peut ne pas être gérée correctement.  
  
 Si vous devez utiliser un saut en dehors d'un bloc **\_\_finally** , contrôlez d'abord un arrêt anormal.  
  
 L'exemple ci\-dessous génère C4532 ; il suffit de mettre en commentaire les instructions de saut pour résoudre les avertissements.  
  
```  
// C4532.cpp  
// compile with: /W1  
// C4532 expected  
int main() {  
   int i;  
   for (i = 0; i < 10; i++) {  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         continue;  
      }  
  
      __try {  
      } __finally {  
         // Delete the following line to resolve.  
         break;  
      }  
   }  
}  
```