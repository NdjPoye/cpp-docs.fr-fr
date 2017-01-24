---
title: "Avertissement du compilateur (niveau&#160;1) C4674 | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C4674"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4674"
ms.assetid: 638dae0b-b82c-4865-9599-72630827ca09
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau&#160;1) C4674
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'method' doit être déclaré 'static' et avoir un seul paramètre  
  
 La signature d’un opérateur de conversion n’était pas correcte. La méthode n’est pas considérée comme une conversion définie par l’utilisateur.  
  
 Si vous utilisez la nouvelle syntaxe \(**\/clr**\), consultez [Opérateurs définis par l'utilisateur](../../dotnet/user-defined-operators-cpp-cli.md) et [Conversions définies par l'utilisateur](../../dotnet/user-defined-conversions-cpp-cli.md) pour plus d’informations sur la définition des opérateurs.  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4674.  
  
```  
// C4674.cpp // compile with: /clr /WX /W1 /LD ref class G { int op_Implicit(int i) {   // C4674 return 0; } };  
```  
  
## Exemple  
 L’exemple suivant génère l’avertissement C4674.  
  
```  
// C4674_b.cpp // compile with: /clr:oldSyntax /W1 /LD __gc class G { int op_Implicit(int i) {   // C4674 // try the following line instead // static int op_Implicit(int i) { return 0; } };  
```