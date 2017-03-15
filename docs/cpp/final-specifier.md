---
title: "Sp&#233;cificateur final | Microsoft Docs"
ms.custom: ""
ms.date: "11/04/2016"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "final"
  - "final_CPP"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "identificateur final"
ms.assetid: 649866d0-79d4-449f-ab74-f84b911b79a3
caps.latest.revision: 7
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
caps.handback.revision: 7
---
# Sp&#233;cificateur final
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser le mot clé `final` pour désigner les fonctions virtuelles qui ne peuvent pas être remplacées dans une classe dérivée.  Vous pouvez également l'utiliser pour désigner les classes qui ne peuvent pas être héritées.  
  
## Syntaxe  
  
```  
  
function-declaration final;  
```  
  
```  
  
class class-name final base-classes  
```  
  
## Notes  
 `final` est contextuel et a une signification spéciale uniquement lorsqu'il est utilisé après une déclaration de fonction ou un nom de classe ; sinon, ce n'est pas un mot clé réservé.  
  
 Lorsque `final` est utilisé dans les déclarations de classes, `base-classes` est une partie facultative de la déclaration.  
  
## Exemple  
 L'exemple suivant utilise le mot clé `final` pour spécifier qu'une fonction virtuelle ne peut pas être remplacée.  
  
```cpp  
class BaseClass  
{  
    virtual void func() final;  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void func(); // compiler error: attempting to   
                         // override a final function  
};  
```  
  
 Pour plus d'informations sur la spécification des fonctions membres afin qu'elles puissent être remplacées, consultez [Spécificateur de substitution](../cpp/override-specifier.md).  
  
 L'exemple suivant utilise le mot clé `final` pour spécifier qu'une classe ne peut pas être héritée.  
  
```cpp  
class BaseClass final   
{  
};  
  
class DerivedClass: public BaseClass // compiler error: BaseClass is   
                                     // marked as non-inheritable  
{  
};  
```  
  
## Voir aussi  
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) C\+\+ Type Names](http://msdn.microsoft.com/fr-fr/b53ba470-e583-4e5c-b634-6018f6110674)   
 [Spécificateur de substitution](../cpp/override-specifier.md)