---
title: "Substitution explicite d&#39;un membre d&#39;interface | Microsoft Docs"
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
  - "substitution explicite de fonction virtuelle"
  - "fonctions (C++), substituer"
  - "membres d'interface, substitutions explicites"
  - "substituer des fonctions"
  - "fonctions virtuelles, substitutions explicites"
ms.assetid: 46f1f536-bf43-4311-9a17-ff2282e528a9
caps.latest.revision: 9
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 9
---
# Substitution explicite d&#39;un membre d&#39;interface
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La syntaxe servant à déclarer une substitution explicite d'un membre d'interface dans une classe a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Vous voudrez fréquemment fournir deux instances d'un membre d'interface dans une classe qui implémente cette interface \- une qui sert lorsque les objets de la classe sont manipulés via un handle d'interface, et une autre qui sert lorsque les objets de la classe sont utilisés via l'interface de classe.  Par exemple :  
  
```  
public __gc class R : public ICloneable {  
   // to be used through ICloneable  
   Object* ICloneable::Clone();  
  
   // to be used through an R  
   R* Clone();  
};  
```  
  
 En Extensions managées, cela se fait en fournissant une déclaration explicite de la méthode d'interface avec le nom de la méthode qualifié par le nom de l'interface.  L'instance spécifique à la classe est non qualifiée.  Cela supprime la nécessité d'un cast aval de la valeur de retour de `Clone`, dans cet exemple, lorsqu'elle est explicitement appelée via une instance de `R`.  
  
 Dans la nouvelle syntaxe, un mécanisme général de substitution a été introduit pour remplacer la syntaxe d'Extensions managées.  Notre exemple sera donc réécrit comme suit :  
  
```  
public ref class R : public ICloneable {  
public:  
   // to be used through ICloneable  
   virtual Object^ InterfaceClone() = ICloneable::Clone;  
  
   // to be used through an R  
   virtual R^ Clone();  
};  
```  
  
 Cette révision exige que le membre d'interface explicitement substitué reçoive un nom unique dans la classe.  Ici, j'ai fourni le nom encombrant de `InterfaceClone`.  Le comportement reste le même : un appel via l'interface `ICloneable` appelle l'`InterfaceClone,` renommé tandis qu'un appel via un objet de type `R` appelle la deuxième instance de `Clone`.  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [Explicit Overrides](../windows/explicit-overrides-cpp-component-extensions.md)