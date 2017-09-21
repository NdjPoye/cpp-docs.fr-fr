---
title: "code_seg (__declspec) | Microsoft Docs"
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
  - "code_seg_cpp"
  - "code_seg"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "code_seg __declspec (mot clé)"
ms.assetid: ad3c1105-15d3-4e08-b7b9-e4bd9d7b6aa0
caps.latest.revision: 11
caps.handback.revision: 11
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# code_seg (__declspec)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Section spécifique à Microsoft**  
  
 L'attribut de déclaration `code_seg` nomme un segment de texte exécutable du fichier .obj dans lequel le code objet de la fonction ou les fonctions membres de la classe seront stockés.  
  
## Syntaxe  
  
```  
__declspec(code_seg("segname")) declarator  
```  
  
## Notes  
 L'attribut `__declspec(code_seg(...))` permet de placer le code dans des blocs nommés distincts qui peuvent être paginés ou verrouillés individuellement en mémoire.  Vous pouvez utiliser cet attribut pour contrôler l'emplacement des modèles instanciés et du code généré par le compilateur.  
  
 Un *segment* correspond à un bloc nommé de données contenues dans un fichier .obj, qui sont chargées en mémoire comme un ensemble.  Un *segment de texte* est un segment qui contient du code exécutable.  Le terme *section* est souvent utilisé à la place du terme "segment".  
  
 Le code objet qui est généré lorsque `declarator` est défini est placé dans le segment de texte spécifié par `segname`, qui est un littéral de chaîne étroite.  Le nom `segname` n'a pas à être spécifié dans un pragma [section](../preprocessor/section.md) avant de pouvoir être utilisé dans une déclaration.  Par défaut, lorsqu'aucun `code_seg` n'est spécifié, le code objet est placé dans un segment nommé ".text".  L'attribut `code_seg` remplace toutes les directives [\#pragma code\_seg](../preprocessor/code-seg.md) existantes.  Un attribut `code_seg` appliqué à une fonction membre remplace tout attribut `code_seg` appliqué à la classe englobante.  
  
 Si une entité a un attribut `code_seg`, toutes les déclarations et définitions de la même entité doivent avoir des attributs `code_seg` identiques.  Si une classe de base a un attribut `code_seg`, les classes dérivées doivent avoir le même attribut.  
  
 Lorsqu'un attribut `code_seg` est appliqué à une fonction portée espace de noms ou à une fonction membre, le code objet de cette fonction est placé dans le segment de texte spécifié.  Si cet attribut est appliqué à une classe, toutes les fonctions membres de la classe et des classes imbriquées \(y compris les fonctions membres spéciales générées par le compilateur\) sont placées dans le segment spécifié.  Les classes définies localement, telles que les classes définies dans le corps d'une fonction membre, n'héritent pas de l'attribut `code_seg` de la portée englobante.  
  
 Lorsqu'un attribut `code_seg` est appliqué à une classe de modèle ou à une fonction de modèle, toutes les spécialisations implicites du modèle sont placées dans le segment spécifié.  Les spécialisations explicites ou partielles n'héritent pas de l'attribut `code_seg` du modèle principal.  Vous pouvez spécifier le même attribut `code_seg` ou un attribut différent pour la spécialisation.  Un attribut `code_seg` ne peut pas être appliqué à une instanciation explicite de modèle.  
  
 Par défaut, le code généré par le compilateur, tel qu'une fonction membre spéciale, est placé dans le segment ".text".  La directive `#pragma code_seg` ne remplace pas cette valeur par défaut.  Utilisez l'attribut `code_seg` dans la classe, le modèle de classe ou le modèle de fonction pour contrôler l'emplacement du code généré par le compilateur.  
  
 Les expressions lambda héritent des attributs `code_seg` de la portée qui les englobe.  Afin de spécifier un segment pour une expression lambda, appliquez un attribut `code_seg` après la clause de déclaration de paramètres et avant toute spécification "mutable" ou d'exception, avant toute spécification de type de retour de fin, et avant le corps de l'expression lambda.  Pour plus d'informations, consultez [Syntaxe d'expression lambda](../cpp/lambda-expression-syntax.md).  Cet exemple définit une expression lambda dans un segment nommé PagedMem :  
  
```cpp  
auto Sqr = [](int t) __declspec(code_seg("PagedMem")) -> int { return t*t; };  
```  
  
 Faites attention lorsque vous placez des fonctions membres dans plusieurs segments, en particulier les fonctions membres virtuelles.  Si vous définissez une fonction virtuelle dans une classe dérivée qui se trouve dans un segment paginé lorsque la méthode de la classe de base se trouve dans un segment non paginé, les autres méthodes de la classe de base ou le code utilisateur peuvent supposer que l'appel de la méthode virtuelle ne génèrera pas de défaut de page.  
  
## Exemple  
 Cet exemple montre comment un attribut `code_seg` contrôle l'emplacement des segments lorsqu'une spécialisation implicite et explicite du modèle est utilisée :  
  
```  
// code_seg.cpp  
// Compile: cl /EHsc /W4 code_seg.cpp  
  
// Base template places object code in Segment_1 segment  
template<class T>  
class __declspec(code_seg("Segment_1")) Example  
{  
public:  
   virtual void VirtualMemberFunction(T /*arg*/) {}  
};  
  
// bool specialization places code in default .text segment  
template<>  
class Example<bool>   
{  
public:  
   virtual void VirtualMemberFunction(bool /*arg*/) {}  
};  
  
// int specialization places code in Segment_2 segment  
template<>  
class __declspec(code_seg("Segment_2")) Example<int>   
{  
public:  
   virtual void VirtualMemberFunction(int /*arg*/) {}  
};  
  
// Compiler warns and ignores __declspec(code_seg("Segment_3"))  
// in this explicit specialization  
__declspec(code_seg("Segment_3")) Example<short>; // C4071  
  
int main()  
{  
   // implicit double specialization uses base template's  
   // __declspec(code_seg("Segment_1")) to place object code  
   Example<double> doubleExample{};  
   doubleExample.VirtualMemberFunction(3.14L);  
  
   // bool specialization places object code in default .text segment  
   Example<bool> boolExample{};  
   boolExample.VirtualMemberFunction(true);  
  
   // int specialization uses __declspec(code_seg("Segment_2"))  
   // to place object code  
   Example<int> intExample{};  
   intExample.VirtualMemberFunction(42);  
}  
```  
  
 **FIN de la section spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)