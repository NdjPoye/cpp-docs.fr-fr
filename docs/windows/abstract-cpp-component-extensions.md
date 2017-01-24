---
title: "abstract  (C++ Component Extensions) | Microsoft Docs"
ms.custom: ""
ms.date: "12/16/2016"
ms.prod: "visual-studio-dev14"
ms.reviewer: ""
ms.suite: ""
ms.technology: 
  - "devlang-cpp"
ms.tgt_pltfrm: ""
ms.topic: "language-reference"
f1_keywords: 
  - "abstract"
  - "abstract_cpp"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "abstract keyword [C++]"
ms.assetid: cbae3408-0378-4ac8-b70d-c016b381a6d5
caps.latest.revision: 21
caps.handback.revision: 21
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# abstract  (C++ Component Extensions)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

Le mot clé `abstract` déclare :  
  
-   Un type peut être utilisé comme type de base, mais le type lui\-même ne peut pas être instancié.  
  
-   Une fonction membre de type peut être définie uniquement dans un type dérivé.  
  
## Toutes les plateformes  
 **Syntaxe**  
  
```  
  
class-declaration class-identifier abstract {}  
virtual return-type member-function-identifier() abstract ;  
  
```  
  
 **Notes**  
  
 Le premier exemple de syntaxe déclare une classe comme étant abstraite.  Le composant de *déclaration de classe* peut être une déclaration C\+\+ native \(`class` ou `struct`\) ou une déclaration d'extension C\+\+ \(`ref class` ou `ref struct`\) si l'option du compilateur **\/ZW** ou **\/clr** est spécifiée.  
  
 Le deuxième exemple de syntaxe déclare une fonction membre virtuelle comme étant abstraite.  La déclaration d'une fonction comme étant abstraite revient à déclarer qu'il s'agit d'une fonction virtuelle pure.  La déclaration d'une fonction membre comme étant abstraite entraîne également la déclaration de la classe englobante comme étant abstraite.  
  
 Le mot clé `abstract` est pris en charge dans le code natif et spécifique à la plateforme ; autrement dit, il peut être compilé avec ou sans l'option du compilateur **\/ZW** ou **\/clr**.  
  
 Vous pouvez détecter, au moment de la compilation, si un type est abstrait avec le trait de type `__is_abstract(``type``)`.  Pour plus d'informations, voir [Compiler Support for Type Traits](../windows/compiler-support-for-type-traits-cpp-component-extensions.md).  
  
 Le mot clé `abstract` est un spécificateur de substitution contextuel.  Pour plus d'informations sur les mots clés contextuels, consultez [Mots clés contextuels](../windows/context-sensitive-keywords-cpp-component-extensions.md).  Pour plus d'informations sur les spécificateurs de substitution, consultez [Comment : déclarer des spécificateurs de substitution dans les compilations natives](../dotnet/how-to-declare-override-specifiers-in-native-compilations-cpp-cli.md).  
  
## [!INCLUDE[wrt](../atl/reference/includes/wrt_md.md)]  
 Pour plus d'informations, consultez [Classes et structs de référence](http://msdn.microsoft.com/library/windows/apps/hh699870.aspx).  
  
### Spécifications  
 Option du compilateur : **\/ZW**  
  
## [!INCLUDE[clr_for_headings](../dotnet/includes/clr_for_headings_md.md)]  
  
### Spécifications  
 Option du compilateur : **\/clr**  
  
### Exemples  
 **Exemple**  
  
 L'exemple de code suivant génère une erreur car la classe `X` est marquée comme `abstract`.  
  
```  
// abstract_keyword.cpp  
// compile with: /clr  
ref class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X ^ MyX = gcnew X;   // C3622  
}  
```  
  
 **Exemple**  
  
 L'exemple de code suivant génère une erreur car il instancie une classe native marquée comme `abstract`.  Cette erreur se produit avec ou sans l'option du compilateur **\/clr**.  
  
```  
// abstract_keyword_2.cpp  
class X abstract {  
public:  
   virtual void f() {}  
};  
  
int main() {  
   X * MyX = new X; // C3622: 'X': a class declared as 'abstract'  
                    // cannot be instantiated. See declaration of 'X'}  
  
```  
  
 **Exemple**  
  
 L'exemple de code suivant génère une erreur car la fonction `f` inclut une définition, mais elle est marquée comme `abstract`.  La dernière instruction de l'exemple montre que la déclaration d'une fonction virtuelle abstraite équivaut à la déclaration d'une fonction virtuelle pure.  
  
```  
// abstract_keyword_3.cpp  
// compile with: /clr  
ref class X {  
public:  
   virtual void f() abstract {}   // C3634  
   virtual void g() = 0 {}   // C3634  
};  
```  
  
## Voir aussi  
 [Component Extensions for Runtime Platforms](../windows/component-extensions-for-runtime-platforms.md)