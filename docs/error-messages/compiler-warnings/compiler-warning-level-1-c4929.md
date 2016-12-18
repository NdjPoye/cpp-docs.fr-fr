---
title: "Avertissement du compilateur (niveau 1) C4929 | Microsoft Docs"
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
  - "C4929"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4929"
ms.assetid: 95f8ab4f-4468-4caa-acd5-8f4592f03b3c
caps.latest.revision: 17
caps.handback.revision: 17
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 1) C4929
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'fichier : typelibrary contient une union ; qualificateur 'embedded\_idl' ignoré  
  
 L'attribut embedded\_idl de [\#import](../../preprocessor/hash-import-directive-cpp.md) ne peut s'appliquer à la bibliothèque de types car une union est présente dans la bibliothèque de types.  Pour résoudre ce problème, n'utilisez pas l'attribut embedded\_idl.  
  
## Exemple  
 L'exemple suivant définit un composant.  
  
```  
// C4929a.cpp  
// compile with: /LD /link /TLBOUT:C4929a.tlb  
#include <objbase.h>  
[module(name="Test")];  
[public, switch_type(short)] typedef union _TD_UNION_TYPE   {  
   [case(24)]  
      float fM;  
   [case(25)]  
      double dMN;  
   [default]  
      int x;  
} TD_UNION_TYPE;  
  
[export, public] typedef struct _TDW_TYPE {  
   [switch_is(sU)] TD_UNION_TYPE w;  
      short sU;  
} TD_TYPE;  
  
[object, uuid("00000000-0000-0000-0000-000000000001")]  
__interface I {  
   HRESULT f(TD_TYPE*);  
};  
  
[coclass, uuid("00000000-0000-0000-0000-000000000002")]  
struct C : I {  
   HRESULT f(TD_TYPE*) { return 0; }  
};  
```  
  
## Exemple  
 L'exemple suivant génère l'erreur C4929 :  
  
```  
// C4929b.cpp  
// compile with: /c /W1  
#import "C4929a.tlb" embedded_idl   // C4929  
```