---
title: "Avertissement du compilateur (niveau 4) C4820 | Microsoft Docs"
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
  - "C4820"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4820"
ms.assetid: 17aa29f4-c287-49b8-bc43-8ed82ffed5ea
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 4) C4820
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'octets' octets de remplissage ajoutés après construction 'nom\_membre'  
  
 Le type et l'ordre des éléments ont fait que le compilateur a ajouté un remplissage à la fin d'une structure.  Consultez [align](../../cpp/align-cpp.md) pour plus d'informations sur le remplissage dans une structure.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple suivant génère l'erreur C4820 :  
  
```  
// C4820.cpp  
// compile with: /W4 /c  
#pragma warning(default : 4820)   
  
// Delete the following 4 lines to resolve.  
__declspec(align(2)) struct MyStruct {  
   char a;  
   int i;   // C4820  
};  
  
// OK  
#pragma pack(1)  
__declspec(align(1)) struct MyStruct2 {  
   char a;  
   int i;  
};  
```