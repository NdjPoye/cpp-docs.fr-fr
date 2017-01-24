---
title: "Avertissement du compilateur (niveau 1) C4397 | Microsoft Docs"
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
  - "C4397"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4397"
ms.assetid: 6346fdc2-dbbf-4fba-803a-32b0d0a707be
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4397
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

DefaultCharSetAttribute est ignoré  
  
 <xref:System.Runtime.InteropServices.DefaultCharSetAttribute> est ignoré par le compilateur Visual C\+\+.  Pour spécifier un jeu de caractères pour la DLL, utilisez l'option CharSet de DllImport.  Pour plus d'informations, consultez [Utilisation de l'interopérabilité C\+\+ \(PInvoke implicite\)](../../dotnet/using-cpp-interop-implicit-pinvoke.md).  
  
## Exemple  
 L'exemple suivant génère l'erreur C4397 :  
  
```  
// C4397.cpp  
// compile with: /W1 /c /clr  
using namespace System;  
using namespace System::Runtime::InteropServices;  
  
[module:DefaultCharSetAttribute(CharSet::Unicode)];   // C4397  
  
[DllImport("kernel32", EntryPoint="CloseHandle", CharSet=CharSet::Unicode)]   // OK  
extern "C" bool ImportDefault(IntPtr hObject);  
  
public ref class MySettingVC {  
public:  
   void method() {  
      ImportDefault(IntPtr::Zero);  
   }  
};  
  
[StructLayout(LayoutKind::Explicit)]  
public ref struct StructDefault1{};  
  
public ref class ClassDefault1{};  
```