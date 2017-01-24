---
title: "Erreur du compilateur C3391 | Microsoft Docs"
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
  - "C3391"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3391"
ms.assetid: c32532b9-7db4-4ccd-84b9-479e5a1a19d1
caps.latest.revision: 6
caps.handback.revision: 6
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3391
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'type\_arg' : argument de type non valide pour le paramètre générique 'param' du générique 'generic\_type', doit être un type valeur non nullable  
  
 Un type générique a été instancié de manière incorrecte.  Vérifiez la définition du type.  Pour plus d’informations, consultez <xref:System.Nullable> et [Generics](../../windows/generics-cpp-component-extensions.md).  
  
## Exemple  
 Dans l’exemple suivant, en C\#, un composant contenant un type générique est créé avec certaines contraintes non prises en charge pendant la création de types génériques dans [!INCLUDE[vcprvclong](../../error-messages/compiler-errors-2/includes/vcprvclong_md.md)]. Pour plus d’informations, consultez [Contraintes sur les paramètres de type](../Topic/Constraints%20on%20Type%20Parameters%20\(C%23%20Programming%20Guide\).md).  
  
```  
// C3391.cs // compile with: /target:library // a C# program public class GR<N> where N : struct {}  
```  
  
## Exemple  
 L’exemple suivant génère l’erreur C3391.  
  
```  
// C3391_b.cpp // compile with: /clr #using <C3391.dll> using namespace System; value class VClass {}; int main() { GR< Nullable<VClass> >^ a = gcnew GR< Nullable<VClass> >();   // C3391 can't be Nullable GR<VClass>^ aa = gcnew GR<VClass>();   // OK }  
```