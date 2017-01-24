---
title: "#error, directive (C/C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "#error"
dev_langs: 
  - "C++"
  - "C"
helpviewer_keywords: 
  - "#error (directive)"
  - "directive error (#error)"
  - "préprocesseur, directives"
ms.assetid: d550a802-ff19-4347-9597-688935d23b2b
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# #error, directive (C/C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La directive `#error` émet un message d'erreur spécifié par l'utilisateur au moment de la compilation puis arrête la compilation.  
  
## Syntaxe  
  
```  
#error token-string  
```  
  
## Notes  
 Le message d'erreur que cette directive émet inclut le paramètre *token\-string*.  Le paramètre `token-string` n'est pas soumis à une expansion macro.  Cette directive est très utile pendant le prétraitement pour informer le développeur d'une incohérence du programme ou de la violation d'une contrainte.  L'exemple suivant illustre le traitement d'une erreur pendant le prétraitement :  
  
```  
#if !defined(__cplusplus)  
#error C++ compiler required.  
#endif  
```  
  
## Voir aussi  
 [Directives de préprocesseur](../preprocessor/preprocessor-directives.md)