---
title: "Compiler Error C3099 | Microsoft Docs"
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
  - "C3099"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3099"
ms.assetid: b3dded0f-76c9-42c1-991b-532eb8619661
caps.latest.revision: 7
caps.handback.revision: 7
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Compiler Error C3099
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'mot clé' : utilisez \[System::AttributeUsageAttribute\] pour les attributs managés ; utilisez \[Windows::Foundation::Metadata::AttributeUsageAttribute\] pour les attributs WinRT  
  
 Utilisez <xref:System.AttributeUsageAttribute> pour déclarer des attributs **\/clr**.  Utilisez `Windows::Foundation::Metadata::AttributeUsageAttribute` pour déclarer des attributs Windows Runtime.  
  
 Pour plus d'informations sur les attributs \/CLR, consultez [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  Pour les attributs pris en charge dans Windows Runtime, consultez [Windows.Foundation.Metadata, espace de noms](http://msdn.microsoft.com/library/windows/apps/windows.foundation.metadata.aspx)  
  
## Exemple  
 L'exemple suivant génère l'erreur C3099 et montre comment la corriger.  
  
```  
// C3099.cpp  
// compile with: /clr /c  
using namespace System;  
[usage(10)]   // C3099  
// try the following line instead  
// [AttributeUsageAttribute(AttributeTargets::All)]  
ref class A : Attribute {};  
```