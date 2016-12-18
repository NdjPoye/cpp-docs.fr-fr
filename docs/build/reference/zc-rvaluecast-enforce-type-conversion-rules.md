---
title: "/Zc:rvalueCast (Appliquer les r&#232;gles de conversion de type) | Microsoft Docs"
ms.custom: ""
ms.date: "12/05/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "article"
f1_keywords: 
  - "rvaluecast"
  - "/Zc:rvalueCast"
  - "VC.Project.VCCLCompilerTool.EnforceTypeConversionRules"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "/Zc (options du compilateur C++)"
  - "Appliquer les règles de conversion de type"
  - "rvaluecast"
  - "Zc (options du compilateur C++)"
  - "-Zc (options du compilateur C++)"
ms.assetid: 7825277d-e565-4c48-b0fb-76ac0b0c6e38
caps.latest.revision: 8
caps.handback.revision: 8
author: "corob-msft"
ms.author: "corob"
manager: "ghogen"
---
# /Zc:rvalueCast (Appliquer les r&#232;gles de conversion de type)
[!INCLUDE[vs2017banner](../../assembler/inline/includes/vs2017banner.md)]

Quand l'option **\/Zc:rvalueCast** est spécifiée, le compilateur identifie correctement un type référence rvalue en tant que résultat d'une opération de cast conformément à la norme C\+\+11.  Quand l'option n'est pas spécifiée, le comportement du compilateur est le même que dans Visual Studio 2012.  Par défaut, **\/Zc:rvalueCast** est désactivé.  Par souci de conformité et pour éliminer les erreurs dans le cadre de l'utilisation des casts, nous vous recommandons d'utiliser **\/Zc:rvalueCast**.  
  
## Syntaxe  
  
```  
/Zc:rvalueCast[-]  
```  
  
## Notes  
 Si **\/Zc:rvalueCast** est spécifié, le compilateur suit la section 5.4 de la norme C\+\+11 et traite uniquement les expressions de cast qui génèrent des types sans référence et les expressions de cast qui génèrent des références rvalue à des types sans fonction en tant que types rvalue.  Par défaut, ou si **\/Zc:rvalueCast\-** est spécifié, le compilateur est non conforme et traite toutes les expressions de cast qui génèrent des références rvalue en tant que valeurs rvalue.  
  
 Utilisez **\/Zc:rvalueCast** si vous passez une expression de cast en tant qu'argument à une fonction qui accepte un type référence rvalue.  Le comportement par défaut entraîne l'erreur de compilateur [C2664](../../error-messages/compiler-errors-2/compiler-error-c2664.md) quand le compilateur détermine de façon erronée le type de l'expression de cast.  Cet exemple illustre une erreur du compilateur dans du code correct quand \/Zc:rvalueCast n'est pas spécifié :  
  
```cpp  
// Test of /Zc:rvalueCast  
// compile by using:  
// cl /c /Zc:rvalueCast- make_thing.cpp  
// cl /c /Zc:rvalueCast make_thing.cpp  
  
#include <utility>  
  
template <typename T>   
struct Thing {  
   // Construct a Thing by using two rvalue reference parameters  
   Thing(T&& t1, T&& t2)  
      : thing1(t1), thing2(t2) {}  
  
   T& thing1;  
   T& thing2;  
};  
  
// Create a Thing, using move semantics if possible  
template <typename T>  
Thing<T> make_thing(T&& t1, T&& t2)  
{  
   return (Thing<T>(std::forward<T>(t1), std::forward<T>(t2)));  
}  
  
struct Test1 {  
   long a;  
   long b;  
  
   Thing<long> test() {   
      // Use identity casts to create rvalues as arguments  
      return make_thing(static_cast<long>(a), static_cast<long>(b));   
   }  
};  
  
```  
  
 Le comportement par défaut du compilateur peut ne pas signaler l'erreur C2102 quand cela est nécessaire.  Dans cet exemple, le compilateur ne signale pas d'erreur si l'adresse d'une rvalue créée par un cast d'identité est acceptée quand **\/Zc:rvalueCast** n'est pas spécifié :  
  
```cpp  
int main() {  
   int a = 1;  
   int *p = &a;   // Okay, take address of lvalue   
                  // Identity cast creates rvalue from lvalue;    
   p = &(int)a;   // problem: should cause C2102: '&' requires l-value  
}  
```  
  
 Pour plus d'informations sur les problèmes de conformité dans Visual C\+\+, consultez [Comportement non standard](../../cpp/nonstandard-behavior.md).  
  
### Pour définir cette option du compilateur dans l'environnement de développement Visual Studio  
  
1.  Ouvrez la boîte de dialogue **Pages de propriété** du projet.  Pour plus d'informations, voir [Utilisation des propriétés de projet](../../ide/working-with-project-properties.md).  
  
2.  Sélectionnez le dossier **C\/C\+\+**.  
  
3.  Sélectionnez la page de propriétés **Ligne de commande**.  
  
4.  Modifiez la propriété **Options supplémentaires** pour inclure **\/Zc:rvalueCast**, puis choisissez **OK**.  
  
## Voir aussi  
 [\/Zc \(Conformité\)](../../build/reference/zc-conformance.md)