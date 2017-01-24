---
title: "Erreur du compilateur C3381 | Microsoft Docs"
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
  - "C3381"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3381"
ms.assetid: d276c89f-8377-4cb6-a8d4-7770885f06c4
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3381
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'assembly' : les spécificateurs d'accès à l'assembly ne sont disponibles que dans le code compilé à l'aide de l'option \/clr  
  
 Les types natifs peuvent être visibles à l'extérieur de l'assembly, mais vous ne pouvez spécifier un accès à l'assembly que pour les types natifs contenus dans une compilation **\/clr**.  
  
 Pour plus d'informations, consultez [Visibilité du type](../../dotnet/how-to-define-and-consume-classes-and-structs-cpp-cli.md#BKMK_Type_visibility) et [\/clr \(Compilation pour le Common Language Runtime\)](../../build/reference/clr-common-language-runtime-compilation.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C3381 :  
  
```  
// C3381.cpp  
// compile with: /c  
public class A {};   // C3381  
```