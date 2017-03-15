---
title: "public (C++) | Microsoft Docs"
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
  - "public"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "public (mot clé) (C++)"
ms.assetid: f3e10a59-39f6-4bcd-827e-3e99f8f89497
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# public (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
public:  
   [member-list]  
public base-class  
```  
  
## Notes  
 Lorsqu'il précède une liste de membres de classe, le mot clé **public** indique que ces membres sont accessibles à partir de n'importe quelle fonction.  Cela s'applique à tous les membres déclarés jusqu'au spécificateur d'accès suivant de la classe.  
  
 Lorsqu'il précède le nom d'une classe de base, le mot clé **public** indique que les membres publics et protégés de la classe de base sont respectivement des membres publics et protégés de la classe dérivée.  
  
 L'accès par défaut des membres d'une classe est privé.  L'accès par défaut des membres d'une structure ou d'une union est public.  
  
 L'accès par défaut d'une classe de base est privé pour les classes et public pour les structures.  Les unions ne peuvent pas avoir de classes de base.  
  
 Pour plus d'informations, consultez [private](../cpp/private-cpp.md), [protected](../cpp/protected-cpp.md), [friend](../cpp/friend-cpp.md) et le tableau d'accès aux membres dans [Contrôle de l'accès aux membres de classe](../misc/controlling-access-to-class-members.md).  
  
## Spécifique \/clr  
 Dans les types CLR, les mots clés de spécificateur d'accès C\+\+ \(**public**, `private`, et `protected`\) peuvent affecter la visibilité des types et des méthodes quant aux assemblys.  Pour plus d'informations, consultez [Visibilité de type et de membre](../misc/type-and-member-visibility.md).  
  
> [!NOTE]
>  Les fichiers compilés avec [\/LN](../build/reference/ln-create-msil-module.md) ne sont pas affectés par ce comportement.  Dans ce cas, toutes les classes managées \(public ou privées\) seront visibles.  
  
## Spécifique END \/clr  
  
## Exemple  
  
```  
// keyword_public.cpp  
class BaseClass {  
public:  
   int pubFunc() { return 0; }  
};  
  
class DerivedClass : public BaseClass {};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   aBase.pubFunc();       // pubFunc() is accessible   
                          //    from any function  
   aDerived.pubFunc();    // pubFunc() is still public in   
                          //    derived class  
}  
```  
  
## Voir aussi  
 [Contrôle de l'accès aux membres de classe](../misc/controlling-access-to-class-members.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)