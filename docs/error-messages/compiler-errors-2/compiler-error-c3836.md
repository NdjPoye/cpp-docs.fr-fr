---
title: "Erreur du compilateur C3836 | Microsoft Docs"
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
  - "C3836"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "C3836"
ms.assetid: 254f851b-7b7d-4c34-a740-fcf72f6a636a
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# Erreur du compilateur C3836
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

un constructeur statique ne peut pas avoir de liste d'initialiseurs de membre  
  
 Une classe managée ne peut pas avoir un constructeur statique qui possède également une liste d'initialiseurs de membre.  Les constructeurs de classe static sont appelés par le Common Language Runtime pour effectuer l'initialisation de la classe, initialisant ainsi les données membres statiques.  
  
 L'exemple suivant génère l'erreur C3836 :  
  
```  
// C3836a.cpp  
// compile with: /clr  
ref class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```  
  
 L'exemple suivant génère l'erreur C3836 :  
  
```  
// C3836b.cpp  
// compile with: /clr:oldSyntax  
#using <mscorlib.dll>  
  
__gc class M  
{  
   static int s_i;  
  
public:  
   static M() :  s_i(1234)   // C3836, delete initializer to resolve  
   {  
   }  
};  
  
int main()  
{  
}  
```