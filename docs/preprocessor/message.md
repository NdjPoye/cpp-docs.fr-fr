---
title: "message | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "message_CPP"
  - "vc-pragma.message"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "message (pragma)"
  - "pragmas, message"
ms.assetid: 67414f25-ed47-4079-a5dc-21d9d1a39754
caps.latest.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 7
---
# message
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Envoie un littéral de chaîne à la sortie standard sans mettre fin à la compilation.  
  
## Syntaxe  
  
```  
  
#pragma message( messagestring )  
```  
  
## Notes  
 Le pragma de type **message** est généralement utilisé pour afficher des messages d'information au moment de la compilation.  
  
 Le paramètre *messagestring* peut être une macro qui se développe en littéral de chaîne et vous pouvez concaténer ces macros avec des littéraux de chaîne selon n'importe quelle combinaison.  
  
 Si vous utilisez une macro prédéfinie dans le pragma de type **message**, la macro doit retourner une chaîne, sinon, vous devrez convertir la sortie de la macro en chaîne.  
  
 Le fragment de code suivant utilise le pragma de type **message** pour afficher des messages pendant la compilation :  
  
```  
// pragma_directives_message1.cpp  
// compile with: /LD  
#if _M_IX86 >= 500  
#pragma message("_M_IX86 >= 500")  
#endif  
  
#pragma message("")  
  
#pragma message( "Compiling " __FILE__ )   
#pragma message( "Last modified on " __TIMESTAMP__ )  
  
#pragma message("")  
  
// with line number  
#define STRING2(x) #x  
#define STRING(x) STRING2(x)  
  
#pragma message (__FILE__ "[" STRING(__LINE__) "]: test")  
  
#pragma message("")  
```  
  
## Voir aussi  
 [Directives pragma et mot clé \_Pragma](../preprocessor/pragma-directives-and-the-pragma-keyword.md)