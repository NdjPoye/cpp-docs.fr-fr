---
title: "Sceller une fonction virtuelle | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__sealed (mot clé)"
  - "classes dérivées, fonctions virtuelles"
  - "sealed (mot clé C++)"
  - "fonctions virtuelles, sceller"
ms.assetid: 0e9fae03-6425-4512-9a24-8ccb6dc8a0d4
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sceller une fonction virtuelle
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

La syntaxe servant à sceller une fonction virtuelle a été modifiée entre Extensions managées pour C\+\+ et [!INCLUDE[cpp_current_long](../dotnet/includes/cpp_current_long_md.md)].  
  
 Le mot clé `__sealed` sert en Extensions managées à modifier soit un type référence, en refusant ses dérivations suivantes \(voir [Déclaration d'un type de classe managée](../dotnet/declaration-of-a-managed-class-type.md)\), soit une fonction virtuelle, en refusant la substitution suivante de la méthode dans une classe dérivée.  Par exemple :  
  
```  
__gc class base { public: virtual void f(); };  
__gc class derived : public base {  
public:  
   __sealed void f();  
};  
```  
  
 Dans cet exemple, `derived::f()` substitue l'instance de `base::f()` en fonction de la correspondance exacte du prototype de la fonction.  Le mot clé `__sealed` indique qu'une classe suivante héritée de la classe dérivée ne peut pas fournir de substitution de `derived::f()`.  
  
 Dans la nouvelle syntaxe, `sealed` est placé après la signature plutôt que d'être autorisé à apparaître avant le prototype réel de la fonction, comme il le pouvait auparavant.  De plus, l'utilisation de `sealed` requiert également l'utilisation explicite du mot clé `virtual`.  Autrement dit, la traduction correcte de `derived`, ci\-dessus, est la suivante :  
  
```  
ref class derived: public base {  
public:  
   virtual void f() override sealed;  
};  
```  
  
 L'absence du mot clé `virtual` dans cette instance entraîne une erreur.  Dans la nouvelle syntaxe, le mot clé contextuel `abstract` peut être utilisé à la place du `=0` pour indiquer une fonction virtuelle pure.  Cela n'était pas pris en charge dans les Extensions managées.  Par exemple :  
  
```  
__gc class base { public: virtual void f()=0; };  
```  
  
 peut être réécrit sous la forme  
  
```  
ref class base { public: virtual void f() abstract; };  
```  
  
## Voir aussi  
 [Déclarations de membre dans une classe ou interface \(C\+\+\/CLI\)](../dotnet/member-declarations-within-a-class-or-interface-cpp-cli.md)   
 [sealed](../windows/sealed-cpp-component-extensions.md)