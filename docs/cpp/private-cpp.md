---
title: "private (C++) | Microsoft Docs"
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
  - "private_cpp"
  - "private"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "private (mot clé) (C++)"
ms.assetid: 94e99983-46a5-4e21-800c-28f8a7c6a8ff
caps.latest.revision: 10
caps.handback.revision: 10
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# private (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

## Syntaxe  
  
```  
private:  
   [member-list]  
private base-class  
```  
  
## Notes  
 Lorsqu'il précède une liste de membres de classe, le mot clé `private` indique que ces membres sont accessibles à partir de n'importe quelle fonction et friends de la classe.  Cela s'applique à tous les membres déclarés jusqu'au spécificateur d'accès suivant de la classe.  
  
 En faisant précéder le nom d'une classe de base, le mot clé `private` indique que les membres publics et protégés de la classe de base sont des membres privés de la classe dérivée.  
  
 L'accès par défaut des membres d'une classe est privé.  L'accès par défaut des membres d'une structure ou d'une union est public.  
  
 L'accès par défaut d'une classe de base est privé pour les classes et public pour les structures.  Les unions ne peuvent pas avoir de classes de base.  
  
 Pour obtenir des informations connexes, consultez [friend](../cpp/friend-cpp.md), [public](../cpp/public-cpp.md), [protected](../cpp/protected-cpp.md), et le tableau d'accès aux membres dans [Contrôle de l'accès aux membres de classe](../misc/controlling-access-to-class-members.md).  
  
## Spécifique \/clr  
 Dans les types CLR, les mots clés de spécificateur d'accès C\+\+ \(**public**, `private`, et `protected`\) peuvent affecter la visibilité des types et des méthodes quant aux assemblys.  Pour plus d'informations, consultez [Visibilité de type et de membre](../misc/type-and-member-visibility.md).  
  
> [!NOTE]
>  Les fichiers compilés avec [\/LN](../build/reference/ln-create-msil-module.md) ne sont pas affectés par ce comportement.  Dans ce cas, toutes les classes managées \(public ou privées\) seront visibles.  
  
## Spécifique END \/clr  
  
## Exemple  
  
```  
// keyword_private.cpp  
class BaseClass {  
public:  
   // privMem accessible from member function  
   int pubFunc() { return privMem; }  
private:  
   void privMem;  
};  
  
class DerivedClass : public BaseClass {  
public:  
   void usePrivate( int i )  
      { privMem = i; }   // C2248: privMem not accessible  
                         // from derived class  
};  
  
class DerivedClass2 : private BaseClass {  
public:  
   // pubFunc() accessible from derived class  
   int usePublic() { return pubFunc(); }  
};  
  
int main() {  
   BaseClass aBase;  
   DerivedClass aDerived;  
   DerivedClass2 aDerived2;  
   aBase.privMem = 1;     // C2248: privMem not accessible  
   aDerived.privMem = 1;  // C2248: privMem not accessible  
                          //    in derived class  
   aDerived2.pubFunc();   // C2247: pubFunc() is private in  
                          //    derived class  
}  
```  
  
## Voir aussi  
 [Contrôle de l'accès aux membres de classe](../misc/controlling-access-to-class-members.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)