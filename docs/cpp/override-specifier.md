---
title: "Spécificateur de substitution | Documents Microsoft"
ms.custom: 
ms.date: 11/04/2016
ms.reviewer: 
ms.suite: 
ms.technology: cpp-language
ms.tgt_pltfrm: 
ms.topic: language-reference
dev_langs: C++
helpviewer_keywords: override Identifier
ms.assetid: b286fb46-9374-4ad8-b2e7-4607119b6133
caps.latest.revision: "8"
author: mikeblome
ms.author: mblome
manager: ghogen
ms.workload: cplusplus
ms.openlocfilehash: 677a6a0e0107f3ed0d0dc402f36e9d6dd4505c7f
ms.sourcegitcommit: 8fa8fdf0fbb4f57950f1e8f4f9b81b4d39ec7d7a
ms.translationtype: MT
ms.contentlocale: fr-FR
ms.lasthandoff: 12/21/2017
---
# <a name="override-specifier"></a>Spécificateur de substitution
Vous pouvez utiliser le mot clé `override` pour désigner les fonctions membres qui remplacent une fonction virtuelle dans une classe de base.  
  
## <a name="syntax"></a>Syntaxe  
  
```  
  
function-declaration override;  
```  
  
## <a name="remarks"></a>Notes  
 `override` est contextuel et a une signification spéciale uniquement lorsqu'il est utilisé après une déclaration de fonction membre ; sinon, ce n'est pas un mot clé réservé.  
  
## <a name="example"></a>Exemple  
 Utilisez `override` pour empêcher un comportement d'héritage inopportun dans votre code. L'exemple suivant indique où, sans utiliser `override`, la fonction membre de classe dérivée ne s'est pas forcément comportée comme prévu. Le compilateur n'émet pas d'erreurs pour ce code.  
  
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
  
 Pour spécifier que les fonctions ne peut pas être remplacées et que les classes ne peut pas être héritées, utilisez le [final](../cpp/final-specifier.md) (mot clé).  
  
## <a name="see-also"></a>Voir aussi  
 [Spécificateur final](../cpp/final-specifier.md)   
 [Mots clés](../cpp/keywords-cpp.md)   
 