---
title: "Sp&#233;cificateur de substitution | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "substituer l'identificateur"
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
caps.latest.revision: 8
caps.handback.revision: 8
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# Sp&#233;cificateur de substitution
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Vous pouvez utiliser le mot clé `override` pour désigner les fonctions membres qui remplacent une fonction virtuelle dans une classe de base.  
  
## Syntaxe  
  
```  
  
function-declaration override;  
```  
  
## Notes  
 `override` est contextuel et a une signification spéciale uniquement lorsqu'il est utilisé après une déclaration de fonction membre ; sinon, ce n'est pas un mot clé réservé.  
  
## Exemple  
 Utilisez `override` pour empêcher un comportement d'héritage inopportun dans votre code.  L'exemple suivant indique où, sans utiliser `override`, la fonction membre de classe dérivée ne s'est pas forcément comportée comme prévu.  Le compilateur n'émet pas d'erreurs pour ce code.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA(); // ok, works as intended  
  
    virtual void funcB(); // DerivedClass::funcB() is non-const, so it does not  
                          // override BaseClass::funcB() const and it is a new member function  
  
    virtual void funcC(double = 0.0); // DerivedClass::funcC(double) has a different  
                                      // parameter type than BaseClass::funcC(int), so  
                                      // DerivedClass::funcC(double) is a new member function  
  
};  
  
```  
  
 Lorsque vous utilisez `override`, le compilateur génère des erreurs au lieu de créer automatiquement les nouvelles fonctions membres.  
  
```cpp  
class BaseClass  
{  
    virtual void funcA();  
    virtual void funcB() const;  
    virtual void funcC(int = 0);  
    void funcD();  
};  
  
class DerivedClass: public BaseClass  
{  
    virtual void funcA() override; // ok  
  
    virtual void funcB() override; // compiler error: DerivedClass::funcB() does not   
                                   // override BaseClass::funcB() const  
  
    virtual void funcC( double = 0.0 ) override; // compiler error:   
                                                 // DerivedClass::funcC(double) does not   
                                                 // override BaseClass::funcC(int)  
  
    void funcD() override; // compiler error: DerivedClass::funcD() does not   
                           // override the non-virtual BaseClass::funcD()  
};  
  
```  
  
 Pour spécifier que les fonctions ne peuvent pas être substituées et que les classes ne peuvent pas être héritées, utilisez le mot clé [final](../cpp/final-specifier.md).  
  
## Voir aussi  
 [Spécificateur final](../cpp/final-specifier.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [\(NOTINBUILD\) C\+\+ Type Names](http://msdn.microsoft.com/fr-fr/b53ba470-e583-4e5c-b634-6018f6110674)