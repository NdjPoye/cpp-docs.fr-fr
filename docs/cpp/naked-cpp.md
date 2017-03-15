---
title: "naked (C++) | Microsoft Docs"
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
  - "naked_cpp"
  - "naked"
dev_langs: 
  - "C++"
helpviewer_keywords: 
  - "__declspec, naked avec mot clé [C++]"
  - "naked __declspec (mot clé)"
ms.assetid: 69723241-05e1-439b-868e-20a83a16ab6d
caps.latest.revision: 12
caps.handback.revision: 12
author: "mikeblome"
ms.author: "mblome"
manager: "ghogen"
---
# naked (C++)
[!INCLUDE[vs2017banner](../assembler/inline/includes/vs2017banner.md)]

**Spécifique à Microsoft**  
  
 Pour les fonctions déclarées avec l'attribut `naked`, le compilateur génère un code sans code de prologue et d'épilogue.  Utilisez cette fonctionnalité pour écrire vos propres séquences de code de prologue\/épilogue utilisant du code assembleur inline.  Les fonctions naked sont particulièrement utiles pour l'écritures de pilotes de périphériques virtuels.  Notez que l'attribut `naked` est uniquement valide sur x86 et ARM, et pas disponible sur [!INCLUDE[vcprx64](../assembler/inline/includes/vcprx64_md.md)].  
  
## Syntaxe  
  
```  
__declspec(naked) declarator  
```  
  
## Notes  
 Comme l'attribut `naked` est uniquement approprié à la définition d'une fonction et pas d'un modificateur de type, les fonctions naked doivent utiliser la syntaxe d'attribut étendu et le mot clé [\_\_declspec](../cpp/declspec.md).  
  
 Le compilateur ne peut pas générer une fonction inline pour une fonction marquée avec l'attribut naked, même si la fonction est également identifiée avec le mot clé [\_\_forceinline](../misc/inline-inline-forceinline.md).  
  
 Le compilateur émet une erreur si l'attribut `naked` est appliqué à une valeur autre que la définition d'une méthode non\-membre.  
  
## Exemples  
 Ce code définit une fonction avec l'attribut `naked` :  
  
```  
__declspec( naked ) int func( formal_parameters ) {}  
```  
  
 Sinon, aussi :  
  
```  
#define Naked __declspec( naked )  
Naked int func( formal_parameters ) {}  
```  
  
 L'attribut `naked` affecte uniquement la nature de la génération de code du compilateur pour les séquences de prologues et d'épilogue de la fonction.  Il n'affecte pas le code généré pour appeler de telles fonctions.  Ainsi, l'attribut `naked` n'est pas considéré comme faisant partie du type de la fonction, et les pointeurs fonction ne peuvent pas avoir l'attribut `naked`.  En outre, l'attribut `naked` ne peut pas être appliqué à une définition de données.  Par exemple, l'exemple de code suivant génère une erreur :  
  
```  
__declspec( naked ) int i;       // Error--naked attribute not  
                                 // permitted on data declarations.  
```  
  
 L'attribut `naked` est pertinent uniquement à la définition de la fonction et ne peut pas être spécifié dans le prototype de fonction.  Par exemple, cette déclaration génère une erreur de compilation :  
  
```  
__declspec( naked ) int func();  // Error--naked attribute not   
                                 // permitted on function declarations  
```  
  
 **END Spécifique à Microsoft**  
  
## Voir aussi  
 [\_\_declspec](../cpp/declspec.md)   
 [Mots clés C\+\+](../cpp/keywords-cpp.md)   
 [Appels de fonction naked](../cpp/naked-function-calls.md)