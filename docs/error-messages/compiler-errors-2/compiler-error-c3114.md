---
title: Erreur du compilateur C3114 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C3114
dev_langs:
- C++
helpviewer_keywords:
- C3114
ms.assetid: b5d2df4f-87d0-4292-9981-25c6a6013c05
caps.latest.revision: 6
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: e4ec82d31e26b33364a73384aae08f6adc48da02
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-error-c3114"></a>Erreur du compilateur C3114
'argument' : argument d’attribut nommé non valide  
  
 Dans l’ordre pour un membre de données de classe attribut soit un argument nommé valide, elle ne doit pas être marquée `static`, `const`, ou `literal`. Si une propriété, la propriété ne doit pas être `static` et doit avoir get et définir des accesseurs.  
  
 Pour plus d’informations, consultez [propriété](../../windows/property-cpp-component-extensions.md) et [les attributs définis par l’utilisateur](../../windows/user-defined-attributes-cpp-component-extensions.md).  
  
## <a name="example"></a>Exemple  
 L’exemple suivant génère C3114.  
  
```  
// C3114.cpp  
// compile with: /clr /c  
public ref class A : System::Attribute {  
public:  
   static property int StaticProp {  
      int get();  
   }  
  
   property int Prop2 {  
      int get();  
      void set(int i);  
   }  
};  
  
[A(StaticProp=123)]   // C3114  
public ref class R {};  
  
[A(Prop2=123)]   // OK  
public ref class S {};  
```
