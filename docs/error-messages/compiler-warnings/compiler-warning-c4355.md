---
title: Avertissement du compilateur C4355 | Documents Microsoft
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology:
- cpp-tools
ms.tgt_pltfrm: 
ms.topic: error-reference
f1_keywords:
- C4355
dev_langs:
- C++
helpviewer_keywords:
- C4355
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: 9
author: corob-msft
ms.author: corob
manager: ghogen
ms.translationtype: MT
ms.sourcegitcommit: 35b46e23aeb5f4dbfd2a0dd44b906389dd5bfc88
ms.openlocfilehash: 061ad3df17cf9c86fbc5ac98048932aff8b0b25b
ms.contentlocale: fr-fr
ms.lasthandoff: 10/10/2017

---
# <a name="compiler-warning-c4355"></a>Avertissement du compilateur C4355
'this' : utilisé dans la liste des initialiseurs membre de base  
  
 Le **cela** pointeur est valide uniquement dans les fonctions membres non statiques. Il ne peut pas être utilisé dans la liste d’initialiseurs d’une classe de base.  
  
 Les constructeurs de classe de base et de membre de classe sont appelés avant **cela** constructeur. En effet, vous avez passé un pointeur vers un objet construit à un autre constructeur. Si ces autres constructeurs accéder aux membres ou appellent des fonctions membres cela, le résultat sera non défini. Vous ne devez pas utiliser le **cela** pointeur jusqu'à la fin de la construction.  
  
 Cet avertissement est désactivé par défaut. Consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md) pour plus d'informations.  
  
 L’exemple suivant génère C4355 :  
  
```  
// C4355.cpp  
// compile with: /w14355 /c  
#include <tchar.h>  
  
class CDerived;  
class CBase {  
public:  
   CBase(CDerived *derived): m_pDerived(derived) {};  
   ~CBase();  
   virtual void function() = 0;  
  
   CDerived * m_pDerived;  
};  
  
class CDerived : public CBase {  
public:  
   CDerived() : CBase(this) {};   // C4355 "this" used in derived c'tor  
   virtual void function() {};  
};  
  
CBase::~CBase() {  
   m_pDerived -> function();  
}  
  
int main() {  
   CDerived myDerived;  
}  
```
