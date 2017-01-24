---
title: "Erreur du compilateur C3846 | Microsoft Docs"
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
  - "C3846"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3846"
ms.assetid: c470f8a5-106b-4efb-b8dc-e1319e04130f
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3846
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'symbole' : impossible d'importer le symbole de 'assembly2', car 'symbol' a déjà été importé d'un autre assembly 'assembly1'  
  
 Un symbole n'a pas pu être importé d'un assembly référencé car il a été importé précédemment d'un assembly référencé.  
  
 L'exemple suivant génère l'erreur C3846 :  
  
```  
// C3846a.cpp  
// compile with: /LD /clr  
public ref struct G  
{  
};  
```  
  
 Enfin, compilez le code suivant :  
  
```  
// C3846b.cpp  
// compile with: /clr  
#using "c3846a.dll"  
#using "c3846a.obj"   // C3846  
  
int main()  
{  
}  
```  
  
 L'exemple suivant génère l'erreur C3846 :  
  
```  
// C3846c.cpp  
// compile with: /LD /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
  
public __gc struct G  
{  
};  
```  
  
 Enfin, compilez le code suivant :  
  
```  
// C3846d.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
using namespace System;  
#using "c3846c.dll"  
#using "c3846c.obj"   // C3846  
  
int main()  
{  
}  
```