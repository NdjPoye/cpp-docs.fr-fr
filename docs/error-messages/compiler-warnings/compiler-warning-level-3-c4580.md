---
title: "Avertissement du compilateur (niveau 3) C4580 | Microsoft Docs"
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
  - "C4580"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4580"
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur (niveau 3) C4580
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

\[attribute\] est déconseillé ; spécifiez System::Attribute ou Platform::Metadata comme classe de base à la place  
  
 [attribute](../../windows/attribute.md) n'est plus la syntaxe préférentielle pour la création d'attributs définis par l'utilisateur.  Pour plus d'informations, voir [User\-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md).  Pour le code CLR, dérivez les attributs à partir de [System::Attribute](assetId:///System::Attribute?qualifyHint=False&autoUpgrade=True).  Pour le code Windows Runtime, dérivez les attributs à partir de `Platform::Metadata`.  
  
## Exemple  
 L'exemple suivant génère l'erreur C3454 et montre comment la corriger.  
  
```  
// C4580.cpp  
// compile with: /W3 /c /clr  
[attribute]   // C4580  
public ref class Attr {  
public:  
   int m_t;  
};  
  
public ref class Attr2 : System::Attribute {  
public:  
   int m_t;  
};  
```