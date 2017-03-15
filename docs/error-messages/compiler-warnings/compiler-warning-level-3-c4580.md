---
title: Avertissement (niveau 3) du compilateur C4580 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- devlang-cpp
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4580
dev_langs:
- C++
helpviewer_keywords:
- C4580
ms.assetid: fef6e8e0-0d6a-44fa-b22a-2fe7ba2ef379
caps.latest.revision: 8
author: corob-msft
ms.author: corob
manager: ghogen
translation.priority.ht:
- cs-cz
- de-de
- es-es
- fr-fr
- it-it
- ja-jp
- ko-kr
- pl-pl
- pt-br
- ru-ru
- tr-tr
- zh-cn
- zh-tw
translationtype: Machine Translation
ms.sourcegitcommit: b551b1a7e0ae03a7de5108a1d114155786972847
ms.openlocfilehash: c8cebbda1d3472a2efda43f816e7a13f2f460408
ms.lasthandoff: 02/24/2017

---
# <a name="compiler-warning-level-3-c4580"></a>Avertissement du compilateur (niveau 3) C4580
[attribute] est déconseillé ; spécifiez System::Attribute ou Platform::Metadata comme classe de base à la place  
  
[[attribut](../../windows/attribute.md)] n’est plus la syntaxe par défaut pour la création d’attributs définis par l’utilisateur. Pour plus d’informations, consultez [les attributs définis par l’utilisateur](../../windows/user-defined-attributes-cpp-component-extensions.md). Pour le code CLR, dérivez les attributs à partir de `System::Attribute`. Pour le code Windows Runtime, dérivez les attributs à partir de `Platform::Metadata`.  
  
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
