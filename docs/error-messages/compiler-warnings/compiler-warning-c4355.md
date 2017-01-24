---
title: "Avertissement du compilateur C4355 | Microsoft Docs"
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
  - "C4355"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C4355"
ms.assetid: b819ecab-8a07-42d7-8fa4-1180d51626c0
caps.latest.revision: 9
caps.handback.revision: 9
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Avertissement du compilateur C4355
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

'this' : utilisé dans la liste des initialiseurs membre de base  
  
 Le pointeur **this** n'est valide qu'à l'intérieur de fonctions membres non statiques.  Il ne peut pas être utilisé sur la liste d'initialiseurs d'une classe de base.  
  
 Les constructeurs de classe de base et de membre de classe sont appelés avec le constructeur **this**.  En fait, vous avez passé à un autre constructeur un pointeur vers un objet non construit.  Si ces autres constructeurs accèdent aux membres ou appellent des fonctions membres, le résultat sera indéfini.  Vous ne devriez utiliser le pointeur **this** qu'après la fin de la construction.  
  
 Cet avertissement est désactivé par défaut.  Pour plus d'informations, consultez [Avertissements du compilateur désactivés par défaut](../../preprocessor/compiler-warnings-that-are-off-by-default.md).  
  
 L'exemple suivant génère l'erreur C4355 :  
  
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