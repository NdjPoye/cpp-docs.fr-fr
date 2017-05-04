---
title: "WeakReference::operator= | Microsoft Docs"
ms.custom: ""
ms.date: "12/14/2016"
ms.prod: "windows-client-threshold"
ms.reviewer: ""
ms.suite: ""
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "vccorlib/WeakReference::operator="
ms.assetid: 20b034d1-8f4f-46ae-81f0-73b76599f86b
caps.latest.revision: 2
author: "ghogen"
ms.author: "ghogen"
manager: "ghogen"
---
# WeakReference::operator=
Assigne une valeur à un WeakReference.  
  
## Syntaxe  
  
```cpp  
WeakReference& operator=(decltype(__nullptr));  
  
WeakReference& operator=(const WeakReference& __otherArg);  
  
WeakReference& operator=(WeakReference&& __otherArg);  
  
WeakReference& operator=(const volatile ::Platform::Object^ const __otherArg);  
  
```  
  
## Notes  
 La dernière surcharge de la liste ci\-dessus vous permet d'assigner une classe ref à une variable WeakReference. Dans ce cas, la classe ref est castée en aval en [Platform::Object](../cppcx/platform-object-class.md). Vous restaurez le type d'origine ultérieurement en le spécifiant comme argument pour le paramètre de type dans la fonction membre [WeakReference::Resolve\<T\>](../cppcx/weakreference-resolve-method-platform-namespace.md).  
  
## Configuration requise  
 Windows 8.0 ou une version supérieure  
  
## Voir aussi  
 [Platform::WeakReference, classe](../cppcx/platform-weakreference-class.md)