---
title: "Avertissement du compilateur (niveau 1) C4297 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "error-reference"
f1_keywords: 
  - "C4297"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4297"
ms.assetid: ba92fcdc-9f70-4f60-abe6-281f9582ca59
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Avertissement du compilateur (niveau 1) C4297
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fonction' : la fonction lève une exception alors qu'elle est présumée ne pas le faire  
  
 Une déclaration de fonction contient un spécificateur `noexcept` \(éventuellement implicite\), un spécificateur d'exception `throw` vide ou un attribut [\_\_declspec \(nothrow\)](../../cpp/nothrow-cpp.md), et la définition contient une ou plusieurs instructions [throw](../../cpp/try-throw-and-catch-statements-cpp.md).  Pour résoudre l'avertissement C4297, ne tentez pas de lever des exceptions dans les fonctions qui sont déclarées `__declspec(nothrow)`, `noexcept(true)` ou `throw()`.  Vous pouvez également supprimer la spécification `noexcept`, `throw()` ou `__declspec(nothrow)`.  
  
 Par défaut, le compilateur génère des spécificateurs `noexcept(true)` implicites pour les fonctions annulatrices d'allocation et les destructeurs définis par l'utilisateur, ainsi que pour les fonctions membres spéciales générées par le compilateur.  Cela est conforme à la norme ISO C\+\+11.  Pour empêcher la génération des spécificateurs noexcept implicites et rétablir le comportement non standard propre à Visual Studio 2013 du compilateur, utilisez l'option du compilateur **\/Zc:implicitNoexcept\-**.  Pour plus d'informations, consultez [\/Zc:implicitNoexcept \(spécificateurs d'exceptions implicites\)](../../build/reference/zc-implicitnoexcept-implicit-exception-specifiers.md).  
  
 Pour plus d'informations sur les spécifications d'exceptions, consultez [Spécifications d'exception \(throw\)](../../cpp/exception-specifications-throw-cpp.md).  Consultez également [\/EH \(Modèle de gestion des exceptions\)](../../build/reference/eh-exception-handling-model.md) pour obtenir des informations sur la façon de modifier le comportement de gestion des exceptions au moment de la compilation.  
  
 Cet avertissement est également généré pour les fonctions \_\_declspec\([dllexport](../../cpp/dllexport-dllimport.md)\) marquées extern "C", même si ce sont des fonctions C\+\+.  
  
 L'exemple suivant génère l'avertissement C4297 :  
  
```  
// C4297.cpp  
// compile with: /W1 /LD  
void __declspec(nothrow) f1()   // declared nothrow  
// try the following line instead  
// void f1()  
{  
   throw 1;   // C4297  
}  
```