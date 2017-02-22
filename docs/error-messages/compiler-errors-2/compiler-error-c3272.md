---
title: "Erreur du compilateur C3272 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3272"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3272"
ms.assetid: 7cdf254d-f207-4116-a1bf-7386f3b82a6f
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3272
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : le symbole requiert FieldOffset, car il est membre de 'nom\_type' défini avec StructLayout\(LayoutKind::Explicit\)  
  
 Quand [StructLayout](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic) `Explicit` est activé, les champs doivent être marqués avec [FieldOffset](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic).  
  
 L’exemple suivant génère l’erreur C3272 :  
  
```  
// C3272_2.cpp // compile with: /clr /c using namespace System; using namespace System::Runtime::InteropServices; [StructLayout(LayoutKind::Explicit)] ref struct X { int data_;   // C3272 // try the following line instead // [FieldOffset(0)] int data_; };  
```  
  
 L’exemple suivant génère l’erreur C3272 :  
  
```  
// C3272.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> using namespace System; using namespace System::Runtime::InteropServices; [StructLayout(LayoutKind::Explicit)] __gc struct X { int data_;   // C3272 // try the following line instead // [FieldOffset(0)] int data_; };  
```