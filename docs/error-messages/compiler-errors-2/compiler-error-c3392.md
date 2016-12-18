---
title: "Erreur du compilateur C3392 | Microsoft Docs"
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
  - "C3392"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3392"
ms.assetid: e4757596-e2aa-4314-b01e-5c4bfd2110e9
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3392
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'arg\_type' : argument de type non valide pour le paramètre générique 'param' du générique 'type\-générique', doit posséder un constructeur sans paramètre public  
  
 Un type générique a été instancié de manière incorrecte.  Vérifiez la définition du type.  Pour plus d’informations, consultez [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Exemple  
 Dans l’exemple suivant, en C\#, un composant contenant un type générique est créé avec certaines contraintes non prises en charge pendant la création de types génériques dans [!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)]. Pour plus d’informations, consultez [Contraintes sur les paramètres de type](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md)  
  
```  
// C3392.cs // compile with: /target:library // a C# program public class GR<C, V, N> where C : class where V : struct where N : new() {}  
```  
  
## Exemple  
 L’exemple suivant génère l’erreur C3392.  
  
```  
// C3392_b.cpp // compile with: /clr #using <C3392.dll> ref class R { R(int) {} }; ref class N { N() {} }; value class V {}; ref class N2 { public: N2() {} }; ref class R2 { public: R2() {} }; int main () { GR<R^, V, N^>^ gr1;   // C3392 GR<R^, V, N2^>^ gr1a;   // OK GR<R^, N^, N^>^ gr3;   // C3392 GR<R^, V, N2^>^ gr3a;   // OK GR<R^, V, R^>^ gr4;   // C3392 GR<R^, V, R2^>^ gr4a;   // OK }  
```