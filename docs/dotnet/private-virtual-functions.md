---
title: "Fonctions virtuelles priv&#233;es | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "modificateurs d'accès (C++), pour les membres de classe"
  - "classes dérivées, fonctions virtuelles"
  - "accès aux membres (C++), membres virtuels"
  - "fonctions virtuelles, privées"
ms.assetid: 04448086-bf72-44be-9c1f-dfda1744949e
caps.latest.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 10
---
# Fonctions virtuelles priv&#233;es
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La gestion des fonctions virtuelles privées dans les classes dérivées a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 En Extensions managées, le niveau d'accès d'une fonction virtuelle ne limite pas sa capacité à être substituée dans une classe dérivée.  Dans la nouvelle syntaxe, une fonction virtuelle ne peut pas substituer une fonction virtuelle de classe de base à laquelle elle ne peut pas accéder.  Par exemple :  
  
```  
__gc class MyBaseClass {  
   // inaccessible to a derived class   
   virtual void g();  
};  
  
__gc class MyDerivedClass : public MyBaseClass {  
public:  
   // okay in Managed Extensions; g() overrides MyBaseClass::g()  
   // error in new syntax; cannot override: MyBaseClass::g() is inaccessible …  
   void g();  
};  
```  
  
 Il n'existe aucun mappage de ce type dans la nouvelle syntaxe.  Il suffit de rendre accessibles, c'est\-à\-dire non privés, les membres de la classe de base.  Les méthodes héritées ne doivent pas porter le même accès.  Dans cet exemple, la modification la moins importante est de rendre le membre de MyBaseClass `protected`.  Ainsi, l'accès du programme général à la méthode via MyBaseClass est encore interdit.  
  
```  
ref class MyBaseClass {  
protected:  
   virtual void g();  
};  
  
ref class MyDerivedClass : MyBaseClass {  
public:  
   virtual void g() override;  
};  
```  
  
 Notez que l'absence du mot clé explicite `virtual` dans la classe de base, dans la nouvelle syntaxe, génère un message d'avertissement.  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Visibilité de membre](../misc/member-visibility.md)