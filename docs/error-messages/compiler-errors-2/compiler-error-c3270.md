---
title: "Erreur du compilateur C3270 | Microsoft Docs"
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
  - "C3270"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3270"
ms.assetid: 70e6e76b-7415-48f5-a61e-2ed50caf08e4
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3270
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'field' : l’attribut FieldOffset peut seulement être utilisé dans le contexte de StructLayout\(Explicit\), auquel cas il est obligatoire  
  
 Un champ a été marqué avec [FieldOffset](frlrfSystemRuntimeInteropServicesFieldOffsetAttributeClassTopic), ce qui est autorisé uniquement si [StructLayout](frlrfSystemRuntimeInteropServicesStructLayoutAttributeClassTopic) Explicit est en vigueur.  
  
 L’exemple suivant génère l’erreur C3270 :  
  
```  
// C3270_2.cpp // compile with: /clr /c using namespace System::Runtime::InteropServices; [ StructLayout(LayoutKind::Sequential) ] // try the following line instead // [ StructLayout(LayoutKind::Explicit) ] public value struct MYUNION { [FieldOffset(0)] int a;   // C3270 // ... };  
```  
  
 L’exemple suivant génère l’erreur C3270 :  
  
```  
// C3270.cpp // compile with: /clr:oldSyntax /LD #using <mscorlib.dll> using namespace System::Runtime::InteropServices; [ StructLayout(LayoutKind::Sequential) ] // try the following line instead // [ StructLayout(LayoutKind::Explicit) ] public __value struct MYUNION { [FieldOffset(0)] int a;   // C3270 // ... };  
```