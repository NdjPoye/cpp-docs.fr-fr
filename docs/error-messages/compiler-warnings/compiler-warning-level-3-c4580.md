---
title: Compilateur avertissement (niveau 3) C4580 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords: C4580
dev_langs: C++
helpviewer_keywords: C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: "8"
author: corob-msft
ms.author: corob
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: ed0391a1a31b4ab64efa01fc15622831de890489
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="compiler-warning-level-3-c4580"></a>Avertissement du compilateur (niveau 3) C4580
[attribute] est déconseillé ; spécifiez System::Attribute ou Platform::Metadata comme classe de base à la place  
  
[[attribut](../../windows/attribute.md)] n’est plus la syntaxe par défaut pour la création d’attributs définis par l’utilisateur. Pour plus d'informations, consultez [User-Defined Attributes](../../windows/user-defined-attributes-cpp-component-extensions.md). Pour le code CLR, dérivez les attributs à partir de `System::Attribute`. Pour le code Windows Runtime, dérivez les attributs à partir de `Platform::Metadata`.  
  
## <a name="example"></a>Exemple  
L'exemple suivant génère l'erreur C3454 et montre comment la corriger.  
  
```cpp  
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