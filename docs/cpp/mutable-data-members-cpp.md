---
title: "Membres de donn&#233;es mutables (C++) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "mutable_cpp"
  - "mutable"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "mutable (mot clé) (C++)"
ms.assetid: ebe89746-3d36-43a8-8d69-f426af23f551
caps.latest.revision: 7
caps.handback.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Membres de donn&#233;es mutables (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Ce mot clé peut être appliqué uniquement aux données membres non statiques et non constantes d'une classe.  Si une donnée membre est déclarée `mutable`, l'assignation d'une valeur à cette donnée membre à partir d'une fonction membre **const** est autorisée.  
  
## Syntaxe  
  
```  
  
mutable member-variable-declaration;  
```  
  
## Notes  
 Par exemple, le code suivant est compilé sans erreur car `m_accessCount` a été déclaré comme étant `mutable` et peut donc être modifié par `GetFlag` bien que `GetFlag` soit une fonction membre const.  
  
```  
// mutable.cpp  
class X  
{  
public:  
   bool GetFlag() const  
   {  
      m_accessCount++;  
      return m_flag;  
   }  
private:  
   bool m_flag;  
   mutable int m_accessCount;  
};  
  
int main()  
{  
}  
```  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)