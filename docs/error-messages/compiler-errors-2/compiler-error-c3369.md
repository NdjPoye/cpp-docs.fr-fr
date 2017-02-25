---
title: "Erreur du compilateur C3369 | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-csharp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "C3369"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3369"
ms.assetid: c6ceb9cb-3df9-4334-9a5c-d16db351d476
caps.latest.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
caps.handback.revision: 8
---
# Erreur du compilateur C3369
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'module name' : idl\_module déjà défini  
  
 L’utilisation d’[idl\_module](../../windows/idl-module.md) où vous définissez la DLL ne peut se produire qu’une seule fois dans un programme.  
  
 L’exemple suivant génère l’erreur C3369 :  
  
```  
// C3369.cpp // compile with: /c [idl_module(name="name1", dllname="x.dll")]; // C3369 [idl_module(name="name1", dllname="x.dll")];  
```