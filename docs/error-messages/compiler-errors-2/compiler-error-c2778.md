---
title: "Erreur du compilateur C2778 | Microsoft Docs"
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
  - "C2778"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C2778"
ms.assetid: b24cb732-2914-42cc-8928-e2d87b393428
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C2778
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

GUID incorrectement formé dans \_\_declspec\(uuid\(\)\)  
  
 Un GUID incorrect est fourni à l'attribut étendu [uuid](../../cpp/uuid-cpp.md).  
  
 Le GUID doit être une chaîne de nombres hexadécimaux au format :  
  
```  
// C2778a.cpp  
// compile with: /c  
struct __declspec(uuid("00000000-0000-0000-0000-000000000000")) A {};  
struct __declspec(uuid("{00000000-0000-0000-0000-000000000000}")) B{};  
```  
  
 L'attribut étendu `uuid` accepte les chaînes reconnues par [CLSIDFromString](http://msdn.microsoft.com/library/windows/desktop/ms680589), avec ou sans délimiteurs d'accolades.  
  
 L'exemple suivant génère l'erreur C2778 :  
  
```  
// C2778b.cpp  
struct __declspec(uuid(" 00000000-0000-0000-0000-000000000000 ")) C { };   // C2778  
struct __declspec(uuid("00000000000000000000000000000000")) D { };   // C2778  
```