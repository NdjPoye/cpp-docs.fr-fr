---
title: "Erreur du compilateur C3095 | Microsoft Docs"
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
  - "C3095"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3095"
ms.assetid: cde725be-0936-40f6-9e57-e1d7d0710f83
caps.latest.revision: 5
caps.handback.revision: 5
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3095
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'attribute' : impossible de répéter l’attribut  
  
 Certains attributs sont déclarés de sorte que plusieurs occurrences d’eux mêmes ne peuvent pas être appliquées à une cible.  
  
 Pour plus d'informations, consultez [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## Exemple  
 L’exemple suivant génère l’erreur C3095.  
  
```  
// C3095.cpp // compile with: /clr /c using namespace System; [AttributeUsage(AttributeTargets::All, AllowMultiple=false)] public ref class Attr : public Attribute { public: Attr(int t) : m_t(t) {} const int m_t; }; [AttributeUsage(AttributeTargets::All, AllowMultiple=true)] public ref class Attr2 : public Attribute { public: Attr2(int t) : m_t(t) {} const int m_t; }; [Attr(10)]   // C3095 [Attr(11)] ref class A {}; [Attr2(10)]   // OK [Attr2(11)] ref class B {};  
```